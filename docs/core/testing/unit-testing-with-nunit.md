---
title: NUnit C# ve .NET Core ile birim testi
description: DotNet test ve NUnit C# kullanarak bir örnek çözüm oluşturma adlı etkileşimli bir deneyim aracılığıyla ve .NET Core 'daki birim testi kavramlarını öğrenin.
author: rprouse
ms.date: 08/31/2018
ms.custom: seodec18
ms.openlocfilehash: 22475fcbd9e971f4c544c020d9198fadee4548b1
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168134"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a>NUnit C# ve .NET Core ile birim testi

Bu öğreticide, birim testi kavramlarını öğrenmek için bir örnek çözüm oluşturma adım adım yönergeler sunarak etkileşimli bir deneyim sağlanır. Önceden oluşturulmuş bir çözüm kullanarak öğreticiyi izlemeyi tercih ediyorsanız, başlamadan önce [örnek kodu görüntüleyin veya indirin](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) . İndirme yönergeleri için bkz. [örnekler ve öğreticiler](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Önkoşullar

- [.NET Core 2,1 SDK](https://www.microsoft.com/net/download) veya sonraki sürümleri.
- Seçtiğiniz bir metin düzenleyici veya kod Düzenleyicisi.

## <a name="creating-the-source-project"></a>Kaynak proje oluşturma

Bir kabuk penceresi açın. Çözümü tutmak için *birim-test-using-NUnit* adlı bir dizin oluşturun. Bu yeni dizin içinde, sınıf kitaplığı ve test projesi için yeni bir çözüm dosyası oluşturmak üzere aşağıdaki komutu çalıştırın:

```console
dotnet new sln
```
 
Ardından, bir *Primeservice* dizini oluşturun. Aşağıdaki ana hat şu ana kadar dizin ve dosya yapısını gösterir:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

Kaynak projeyi oluşturmak için *Primeservice* 'i geçerli dizin yapın ve şu komutu çalıştırın:

```console
dotnet new classlib
```

*Class1.cs* olarak yenidenadlandırın. `PrimeService` Sınıfın başarısız bir uygulamasını oluşturursunuz:

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first.");
        }
    }
}
```

Dizini *birim-test-NUnit* dizinine geri doğru değiştirin. Çözüme Sınıf Kitaplığı projesini eklemek için aşağıdaki komutu çalıştırın:

```console
dotnet sln add PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a>Test projesi oluşturma

Ardından, *Primeservice. Tests* dizinini oluşturun. Aşağıdaki ana hat dizin yapısını gösterir:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

*Primeservice. test* dizinini geçerli dizini yapın ve aşağıdaki komutu kullanarak yeni bir proje oluşturun:

```console
dotnet new nunit
```

[DotNet New](../tools/dotnet-new.md) komutu, test kitaplığı olarak NUnit kullanan bir test projesi oluşturur. Oluşturulan şablon, *Primeservice. Tests. csproj* dosyasındaki Test Çalıştırıcısı 'nı yapılandırır:

[!code-xml[Packages](~/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj#Packages)]

Test projesi, birim testlerini oluşturmak ve çalıştırmak için diğer paketlerin kullanılmasını gerektirir. `dotnet new`önceki adımda Microsoft Test SDK 'sını, NUnit test çerçevesini ve NUnit test bağdaştırıcısını ekledik. Şimdi, `PrimeService` sınıf kitaplığını projeye başka bir bağımlılık olarak ekleyin. [`dotnet add reference`](../tools/dotnet-add-reference.md) Şu komutu kullanın:

```console
dotnet add reference ../PrimeService/PrimeService.csproj
```

GitHub 'daki [örnekler deposunda](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) dosyanın tamamını görebilirsiniz.

Aşağıdaki ana hat, son çözüm yerleşimini göstermektedir:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.csproj
```

*Birim-test-NUnit* dizininde aşağıdaki komutu yürütün:

```console
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a>İlk test oluşturma

Başarısız bir test yazdığınızda, geçişi yapıp işlemi tekrarlayabilirsiniz. *Primeservice. Tests* dizininde, *UnitTest1.cs* dosyasını *PrimeService_IsPrimeShould. cs* olarak yeniden adlandırın ve tüm içeriğini aşağıdaki kodla değiştirin:

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        [Test]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            PrimeService primeService = CreatePrimeService();
            var result = primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
        
        /*
        More tests
        */
        
        private PrimeService CreatePrimeService()
        {
             return new PrimeService();
        }
    }
}
```

Öznitelik `[TestFixture]` , birim testlerini içeren bir sınıfı gösterir. `[Test]` Özniteliği bir yöntemin test yöntemi olduğunu gösterir.

Testleri ve sınıf kitaplığını derlemek [`dotnet test`](../tools/dotnet-test.md) ve ardından testleri çalıştırmak için bu dosyayı kaydedin ve yürütün. NUnit Test Çalıştırıcısı, testlerinizi çalıştırmak için program giriş noktasını içerir. `dotnet test`oluşturduğunuz birim test projesini kullanarak Test Çalıştırıcısı başlatır.

Testiniz başarısız oluyor. Uygulamayı henüz oluşturmadınız. Bu test geçişini, çalıştıran `PrimeService` sınıfa en basit kodu yazarak yapın:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first.");
}
```

*Birim-test-using-NUnit* dizininde yeniden çalıştırın `dotnet test` . Komutu, `PrimeService` proje için bir yapı ve ardından projeiçinçalışır.`PrimeService.Tests` `dotnet test` Her iki proje de oluşturulduktan sonra bu tek testi çalıştırır. Geçirir.

## <a name="adding-more-features"></a>Daha fazla özellik ekleme

Artık bir test geçişi yapmış olduğunuza göre daha fazla yazma zamanı vardır. Asal sayıların diğer birkaç basit durumu vardır: 0,-1. `[Test]` Özniteliğiyle yeni testler ekleyebilirsiniz, ancak bu hızlı bir şekilde sıkıcı olur. Benzer testlerin bir paketini yazmanızı sağlayan başka NUnit öznitelikleri vardır.  `[TestCase]` Özniteliği, aynı kodu çalıştıran ancak farklı giriş bağımsız değişkenlerine sahip olan testlerin bir paketini oluşturmak için kullanılır. Bu girişlerin değerlerini belirtmek `[TestCase]` için özniteliğini kullanabilirsiniz.

Yeni test oluşturmak yerine, tek bir veri temelli test oluşturmak için bu özniteliği uygulayın. Veri temelli test, en düşük asal sayı olan iki değerden küçük birkaç değeri sınayan bir yöntemdir:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Çalıştır `dotnet test`ve bu testlerin ikisi de başarısız olur. Tüm testlerin geçişini yapmak için `if` *PrimeService.cs* dosyasındaki `Main` yönteminin başındaki yan tümceyi değiştirin:

```csharp
if (candidate < 2)
```

Ana kitaplıkta daha fazla test, daha fazla yer ve daha fazla kod ekleyerek yinelemek için devam edin. [Testlerin tamamlanmış sürümüne](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) ve [kitaplığın tüm uygulamasına](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs)sahipsiniz.

Bu kitaplık için küçük bir kitaplık ve birim testleri kümesi oluşturdunuz. Çözümü, yeni paket ve test eklemek normal iş akışının bir parçası olacak şekilde öğrendiniz. Uygulamanın hedeflerini çözme konusunda zaman ve çaba harcamanızı en iyi şekilde gördünüz.
