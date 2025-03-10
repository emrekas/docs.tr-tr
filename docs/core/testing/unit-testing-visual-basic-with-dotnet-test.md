---
title: DotNet test ve xUnit ile .NET Core 'da birim testi Visual Basic
description: .NET Core 'da, DotNet test ve xUnit kullanarak örnek Visual Basic çözüm adım adım oluşturma adlı etkileşimli bir deneyim aracılığıyla birim testi kavramlarını öğrenin.
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.custom: seodec18
ms.openlocfilehash: 63898f23f7c70a96409c6de9029fb0c067223016
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373875"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a>DotNet test ve xUnit kullanarak .NET Core kitaplıkları Visual Basic birim testi

Bu öğreticide, birim testi kavramlarını öğrenmek için bir örnek çözüm oluşturma adım adım yönergeler sunarak etkileşimli bir deneyim sağlanır. Önceden oluşturulmuş bir çözüm kullanarak öğreticiyi izlemeyi tercih ediyorsanız, başlamadan önce [örnek kodu görüntüleyin veya indirin](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-dotnet-test) . İndirme yönergeleri için bkz. [örnekler ve öğreticiler](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a>Kaynak proje oluşturma

Bir kabuk penceresi açın. Çözümü tutmak için *birim-test-vb-using-DotNet-test* adlı bir dizin oluşturun.
Yeni bir çözüm oluşturmak için bu [`dotnet new sln`](../tools/dotnet-new.md) yeni dizinin içinde öğesini çalıştırın. Bu uygulama, hem sınıf kitaplığını hem de birim testi projesini yönetmeyi kolaylaştırır.
Çözüm dizini içinde bir *Primeservice* dizini oluşturun. Şu ana kadar Şu dizin ve dosya yapısına sahipsiniz:

```console
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

Kaynak projeyi oluşturmak için *primeservice* 'i geçerli [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) Dizin yapın ve çalıştırın. *Class1. vb* ' i *primeservice. vb*olarak yeniden adlandırın. `PrimeService` Sınıfın başarısız bir uygulamasını oluşturursunuz:

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

Dizini *birim-test-vb-using-DotNet-test* dizini olarak yeniden değiştirin. Çözüme [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) Sınıf Kitaplığı projesini eklemek için ' i çalıştırın.

## <a name="creating-the-test-project"></a>Test projesi oluşturma

Ardından, *Primeservice. Tests* dizinini oluşturun. Aşağıdaki ana hat dizin yapısını gösterir:

```console
/unit-testing-vb-using-dotnet-test
    unit-testing-vb-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

*Primeservice. test* dizinini geçerli dizini yapın ve kullanarak [`dotnet new xunit -lang VB`](../tools/dotnet-new.md)yeni bir proje oluşturun. Bu komut, test kitaplığı olarak xUnit kullanan bir test projesi oluşturur. Oluşturulan şablon, *Primeservicetests. vbproj*içindeki Test Çalıştırıcısı 'nı yapılandırır:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

Test projesi, birim testlerini oluşturmak ve çalıştırmak için diğer paketlerin kullanılmasını gerektirir. `dotnet new`önceki adımda xUnit ve xUnit Çalıştırıcısı eklenmiştir. Şimdi, `PrimeService` sınıf kitaplığını projeye başka bir bağımlılık olarak ekleyin. [`dotnet add reference`](../tools/dotnet-add-reference.md) Şu komutu kullanın:

```console
dotnet add reference ../PrimeService/PrimeService.vbproj
```

GitHub 'daki [örnekler deposunda](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj) dosyanın tamamını görebilirsiniz.

Aşağıdaki son klasör düzenine sahipsiniz:

```console
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

[`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) *Birim-test-vb-using-DotNet-test* dizininde yürütün. 

## <a name="creating-the-first-test"></a>İlk test oluşturma

Başarısız bir test yazdığınızda, geçişi yapıp işlemi tekrarlayabilirsiniz. *UnitTest1. vb* 'Yi *primeservice. Tests* dizininden KALDıRıN ve *PrimeService_IsPrimeShould. vb*adlı yeni bir Visual Basic dosya oluşturun. Aşağıdaki kodu ekleyin:

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Fact>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

`<Fact>` Öznitelik, Test Çalıştırıcısı tarafından çalıştırılan bir test yöntemini gösterir. *Birim-test--DotNet-test*' i [`dotnet test`](../tools/dotnet-test.md) kullanarak testleri ve sınıf kitaplığını oluşturup testleri çalıştırın. XUnit Test Çalıştırıcısı, testlerinizi çalıştırmak için program giriş noktasını içerir. `dotnet test`oluşturduğunuz birim test projesini kullanarak Test Çalıştırıcısı başlatır.

Testiniz başarısız oluyor. Uygulamayı henüz oluşturmadınız. Bu test geçişini, çalıştıran `PrimeService` sınıfa en basit kodu yazarak yapın:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

*Birim-test-vb-using-DotNet-test* dizininde yeniden çalıştırın `dotnet test` . Komutu, `PrimeService` proje için bir yapı ve ardından projeiçinçalışır.`PrimeService.Tests` `dotnet test` Her iki proje de oluşturulduktan sonra bu tek testi çalıştırır. Geçirir.

## <a name="adding-more-features"></a>Daha fazla özellik ekleme

Artık bir test geçişi yapmış olduğunuza göre daha fazla yazma zamanı vardır. Asal sayıların diğer birkaç basit durumu vardır: 0,-1. Bu servis taleplerini `<Fact>` özniteliğiyle yeni testler olarak ekleyebilirsiniz, ancak bu, hızlı bir şekilde sıkıcı hale gelir. Benzer testlerin bir paketini yazmanızı sağlayan başka xUnit öznitelikleri vardır.  `<Theory>` Öznitelik, aynı kodu çalıştıran ancak farklı giriş bağımsız değişkenlerine sahip olan bir test paketini temsil eder. Bu girişlerin değerlerini belirtmek `<InlineData>` için özniteliğini kullanabilirsiniz.

Yeni test oluşturmak yerine, tek bir teorisi oluşturmak için bu iki özniteliği uygulayın. Teorisi, en düşük asal sayı olan iki değerden küçük birkaç değeri sınayan bir yöntemdir:

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

Çalıştır `dotnet test`ve bu testlerin ikisi de başarısız olur. Tüm testlerin geçişini yapmak için yönteminin başındaki `if` yan tümceyi değiştirin:

```vb
if candidate < 2
```

Ana kitaplıkta daha fazla test, daha fazla yer ve daha fazla kod ekleyerek yinelemek için devam edin. [Testlerin tamamlanmış sürümüne](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) ve [kitaplığın tüm uygulamasına](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb)sahipsiniz.

Bu kitaplık için küçük bir kitaplık ve birim testleri kümesi oluşturdunuz. Çözümü, yeni paket ve test eklemek normal iş akışının bir parçası olacak şekilde öğrendiniz. Uygulamanın hedeflerini çözme konusunda zaman ve çaba harcamanızı en iyi şekilde gördünüz.
