---
title: Dotnet testi ve xUnit ile .NET Core Visual Basic test birimi
description: Adım adım örnek Visual Basic çözüm oluşturma etkileşimli bir deneyim .NET Core birim testi kavramları öğrenin dotnet testi ve xUnit kullanma.
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
dev_langs:
- vb
ms.custom: seodec18
ms.openlocfilehash: 193746e8efda5d7bc9e086bb0abf934cfeb1741a
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748602"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a><span data-ttu-id="35e5b-103">Birim testi dotnet testi ve xUnit kullanarak Visual Basic .NET Core kitaplıkları</span><span class="sxs-lookup"><span data-stu-id="35e5b-103">Unit testing Visual Basic .NET Core libraries using dotnet test and xUnit</span></span>

<span data-ttu-id="35e5b-104">Bu öğretici örnek bir çözüm birim testi kavramlarını öğrenmek için adım adım oluşturmaya etkileşimli deneyim gösterir.</span><span class="sxs-lookup"><span data-stu-id="35e5b-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="35e5b-105">Önceden oluşturulmuş bir çözümü kullanarak öğreticiyi uygulamak isterseniz [görüntülemek veya örnek kodu indirdikten](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-dotnet-test) başlamadan önce.</span><span class="sxs-lookup"><span data-stu-id="35e5b-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-dotnet-test) before you begin.</span></span> <span data-ttu-id="35e5b-106">Yükleme yönergeleri için bkz: [örnekler ve öğreticiler](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="35e5b-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="35e5b-107">Kaynak proje oluşturma</span><span class="sxs-lookup"><span data-stu-id="35e5b-107">Creating the source project</span></span>

<span data-ttu-id="35e5b-108">Shell penceresini açın.</span><span class="sxs-lookup"><span data-stu-id="35e5b-108">Open a shell window.</span></span> <span data-ttu-id="35e5b-109">Adlı bir dizin oluşturun *unit-testing-vb-using-dotnet-test* çözüm tutacak.</span><span class="sxs-lookup"><span data-stu-id="35e5b-109">Create a directory called *unit-testing-vb-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="35e5b-110">Bu yeni dizin içinde çalıştırma [ `dotnet new sln` ](../tools/dotnet-new.md) yeni bir çözüm oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="35e5b-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="35e5b-111">Bu yöntem, sınıf kitaplığı hem birim test projesi yönetmenizi kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="35e5b-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="35e5b-112">Çözüm dizini içinde bir *PrimeService* dizin.</span><span class="sxs-lookup"><span data-stu-id="35e5b-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="35e5b-113">Aşağıdaki dizin ve dosya yapısı şimdiye kadarki vardır:</span><span class="sxs-lookup"><span data-stu-id="35e5b-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="35e5b-114">Olun *PrimeService* geçerli dizin ve çalışma [ `dotnet new classlib -lang VB` ](../tools/dotnet-new.md) kaynak proje oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="35e5b-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="35e5b-115">Yeniden adlandırma *Class1.VB* için *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="35e5b-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="35e5b-116">Bir başarısız uygulamasını oluşturun `PrimeService` sınıfı:</span><span class="sxs-lookup"><span data-stu-id="35e5b-116">You create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="35e5b-117">Dizine dön değişiklik *unit-testing-vb-using-dotnet-test* dizin.</span><span class="sxs-lookup"><span data-stu-id="35e5b-117">Change the directory back to the *unit-testing-vb-using-dotnet-test* directory.</span></span> <span data-ttu-id="35e5b-118">Çalıştırma [ `dotnet sln add .\PrimeService\PrimeService.vbproj` ](../tools/dotnet-sln.md) sınıf kitaplığı projesi çözüme eklemek için.</span><span class="sxs-lookup"><span data-stu-id="35e5b-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="35e5b-119">Test projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="35e5b-119">Creating the test project</span></span>

<span data-ttu-id="35e5b-120">Ardından, oluşturma *PrimeService.Tests* dizin.</span><span class="sxs-lookup"><span data-stu-id="35e5b-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="35e5b-121">Ana hat aşağıdaki dizin yapısını gösterir:</span><span class="sxs-lookup"><span data-stu-id="35e5b-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-using-dotnet-test
    unit-testing-vb-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="35e5b-122">Olun *PrimeService.Tests* dizini geçerli dizin ve kullanarak yeni bir proje oluşturma [ `dotnet new xunit -lang VB` ](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="35e5b-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="35e5b-123">Bu komut, xUnit test kitaplık olarak kullanan bir test projesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="35e5b-123">This command creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="35e5b-124">Test Çalıştırıcısı'nda oluşturulan şablon yapılandırır *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="35e5b-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="35e5b-125">Test projesi oluşturma ve birim testlerini çalıştırmak için diğer paketleri gerektirir.</span><span class="sxs-lookup"><span data-stu-id="35e5b-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="35e5b-126">`dotnet new` Önceki adımda, xUnit ve xUnit Çalıştırıcısı eklendi.</span><span class="sxs-lookup"><span data-stu-id="35e5b-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="35e5b-127">Şimdi ekleyin `PrimeService` sınıf kitaplığı projesine başka bir bağımlılık olarak.</span><span class="sxs-lookup"><span data-stu-id="35e5b-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="35e5b-128">Kullanım [ `dotnet add reference` ](../tools/dotnet-add-reference.md) komutu:</span><span class="sxs-lookup"><span data-stu-id="35e5b-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="35e5b-129">Dosyanın tamamını görebilirsiniz [örnekleri depomuzdan](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj) GitHub üzerinde.</span><span class="sxs-lookup"><span data-stu-id="35e5b-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="35e5b-130">Aşağıdaki son klasör düzeni vardır:</span><span class="sxs-lookup"><span data-stu-id="35e5b-130">You have the following final folder layout:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="35e5b-131">Yürütme [ `dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj` ](../tools/dotnet-sln.md) içinde *unit-testing-vb-using-dotnet-test* dizin.</span><span class="sxs-lookup"><span data-stu-id="35e5b-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="35e5b-132">İlk testi oluşturma</span><span class="sxs-lookup"><span data-stu-id="35e5b-132">Creating the first test</span></span>

<span data-ttu-id="35e5b-133">Bir yazma, test başarısız kolaylaştırır geçişi, sonra işlemi yineleyin.</span><span class="sxs-lookup"><span data-stu-id="35e5b-133">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="35e5b-134">Kaldırma *UnitTest1.vb* gelen *PrimeService.Tests* dizin adlı yeni bir Visual Basic dosyası oluşturup *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="35e5b-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="35e5b-135">Aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="35e5b-135">Add the following code:</span></span>

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Fact>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="35e5b-136">`<Fact>` Test Çalıştırıcısı tarafından yürütülen bir test metodu özniteliği gösterir.</span><span class="sxs-lookup"><span data-stu-id="35e5b-136">The `<Fact>` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="35e5b-137">Gelen *birim testi-kullanarak-dotnet-test*, yürütme [ `dotnet test` ](../tools/dotnet-test.md) testler ve sınıf kitaplığı oluşturun ve ardından testleri çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="35e5b-137">From the *unit-testing-using-dotnet-test*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="35e5b-138">XUnit test Çalıştırıcısı, testlerinizi çalıştırmak için programın giriş noktası içerir.</span><span class="sxs-lookup"><span data-stu-id="35e5b-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="35e5b-139">`dotnet test` oluşturduğunuz birim test projesi kullanarak test Çalıştırıcısı'nı başlatır.</span><span class="sxs-lookup"><span data-stu-id="35e5b-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="35e5b-140">Test başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="35e5b-140">Your test fails.</span></span> <span data-ttu-id="35e5b-141">Uygulama henüz oluşturmadınız.</span><span class="sxs-lookup"><span data-stu-id="35e5b-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="35e5b-142">En basit kod yazarak bu testin geçmesini `PrimeService` çalışır sınıfı:</span><span class="sxs-lookup"><span data-stu-id="35e5b-142">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="35e5b-143">İçinde *unit-testing-vb-using-dotnet-test* çalışması dizini `dotnet test` yeniden.</span><span class="sxs-lookup"><span data-stu-id="35e5b-143">In the *unit-testing-vb-using-dotnet-test* directory, run `dotnet test` again.</span></span> <span data-ttu-id="35e5b-144">`dotnet test` Komut çalıştıran bir derleme için `PrimeService` proje ve ardından `PrimeService.Tests` proje.</span><span class="sxs-lookup"><span data-stu-id="35e5b-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="35e5b-145">Her iki proje oluşturduktan sonra bu tek bir test çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="35e5b-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="35e5b-146">Bu geçirir.</span><span class="sxs-lookup"><span data-stu-id="35e5b-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="35e5b-147">Daha fazla özellik ekleme</span><span class="sxs-lookup"><span data-stu-id="35e5b-147">Adding more features</span></span>

<span data-ttu-id="35e5b-148">Bir test geçirmek yaptığınız, daha fazla yazmak için zaman var.</span><span class="sxs-lookup"><span data-stu-id="35e5b-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="35e5b-149">Birkaç basit durumlardaysa asal sayıları için vardır: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="35e5b-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="35e5b-150">Bu gibi durumlarda, yeni testleriyle olarak ekleyebilirsiniz `<Fact>` özniteliği ancak hızla olur yorucu bir süreç.</span><span class="sxs-lookup"><span data-stu-id="35e5b-150">You could add those cases as new tests with the `<Fact>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="35e5b-151">Benzer testleri paketi yazmanızı sağlayan diğer xUnit öznitelikleri vardır.</span><span class="sxs-lookup"><span data-stu-id="35e5b-151">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="35e5b-152">A `<Theory>` öznitelik aynı kod yürütün, ancak farklı giriş bağımsız değişkenleri olan testleri paketi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="35e5b-152">A `<Theory>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="35e5b-153">Kullanabileceğiniz `<InlineData>` bu girişleri değerlerini belirtmek için özniteliği.</span><span class="sxs-lookup"><span data-stu-id="35e5b-153">You can use the `<InlineData>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="35e5b-154">Yeni testler oluşturmak yerine, tek bir kuramsal oluşturmak için bu iki öznitelikler uygulanır.</span><span class="sxs-lookup"><span data-stu-id="35e5b-154">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="35e5b-155">Teorik asal numarası en düşük olan değerlerden küçüktür iki test yöntemi verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="35e5b-155">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="35e5b-156">Çalıştırma `dotnet test`, ve bunlardan ikisi başarısız test eder.</span><span class="sxs-lookup"><span data-stu-id="35e5b-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="35e5b-157">Tüm testler başarılı hale getirmek için değiştirme `if` yöntemin başında yan tümcesi:</span><span class="sxs-lookup"><span data-stu-id="35e5b-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="35e5b-158">Ana Kitaplığı'nda daha fazla test, daha fazla Teoriler ve daha fazla kod ekleyerek yinelemek devam edin.</span><span class="sxs-lookup"><span data-stu-id="35e5b-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="35e5b-159">Sahip olduğunuz [testlerinin tamamlanmış bir sürümünü](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) ve [Kitaplığı'nın tam bir uygulamaya](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="35e5b-159">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="35e5b-160">Küçük bir kitaplık ve bu kitaplık için birim testleri bir dizi oluşturdunuz.</span><span class="sxs-lookup"><span data-stu-id="35e5b-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="35e5b-161">Böylece yeni paketler ekleme çözüm yapılandırılmış ve testleri normal iş akışı bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="35e5b-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="35e5b-162">Zaman ve çaba çözme hedeflerinden biri, uygulama üzerinde en yoğun.</span><span class="sxs-lookup"><span data-stu-id="35e5b-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
