---
title: Hedef çerçeveler
description: .NET Core Uygulamaları ve kitaplıkları için hedef çerçeveler hakkında bilgi edinin.
author: richlander
ms.author: mairaw
ms.date: 04/02/2019
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: 20b13bb590a63a807c1894bf08051053f90c0fc4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666516"
---
# <a name="target-frameworks"></a>Hedef çerçeveler

Bir uygulamayı veya kitaplığı içinde bir çerçeveyi hedeflediğinizde, uygulama veya kitaplık için kullanılabilir hale getirmek istediğiniz API kümesini belirtirsiniz. Hedef Framework 'ü hedef Framework takma adları 'nı (TFMs) kullanarak proje dosyanızda belirtirsiniz.

Bir uygulama veya kitaplık [.NET Standard](net-standard.md)bir sürümünü hedefleyebilir. .NET Standard sürümler tüm .NET uygulamalarında standartlaştırılmış API kümelerini temsil eder. Örneğin, bir kitaplık .NET Standard 1,6 ' i hedefleyebilir ve aynı kod tabanını kullanarak .NET Core ve .NET Framework üzerinde çalışır olan API 'lere erişim elde edebilir.

Uygulama veya kitaplık, uygulamaya özel API 'lere erişim kazanmak için belirli bir .NET uygulamasını da hedefleyebilir. Örneğin, Xamarin. iOS 'u hedefleyen bir uygulama (örneğin, `Xamarin.iOS10`) iOS 10 için Xamarin tarafından sağlanmış iOS API sarmalayıcılarını veya Evrensel Windows platformu (UWP, `uap10.0`) kullanan bir uygulamanın, çalıştıran cihazlar için derleme yapan API 'lere erişimi vardır. Windows 10.

Bazı hedef çerçeveler için (örneğin, .NET Framework), API 'Ler Framework 'ün bir sisteme yüklediği derlemeler tarafından tanımlanır ve uygulama çerçevesi API 'Lerini (örneğin, ASP.NET) içerebilir.

Paket tabanlı hedef çerçeveler için (örneğin, .NET Standard ve .NET Core), API 'Ler uygulamaya veya kitaplığa dahil edilen paketler tarafından tanımlanır. *Metapackage* , kendi içeriğine sahip olmayan ancak bağımlılıklar (diğer paketler) listesi olan bir NuGet paketidir. NuGet paket tabanlı bir hedef çerçeve, bir arada çerçeveyi oluşturan tüm paketlere başvuran bir metapackage öğesini örtülü olarak belirler.

## <a name="latest-target-framework-versions"></a>En son hedef Framework sürümleri

Aşağıdaki tablo, en yaygın hedef çerçeveleri, nasıl başvurulduğunu ve [.NET Standard](net-standard.md) hangi sürümünün uygulandığını tanımlar. Bu hedef Framework sürümleri, en son kararlı sürümleridir. Yayın öncesi sürümler gösterilmez. Hedef çerçeve bilinen adı (tfd), bir .NET uygulaması veya kitaplığının hedef çerçevesini belirtmek için standartlaştırılmış bir belirteç biçimidir.

| Hedef Çerçeve      | En son <br/> Kararlı sürüm | Hedef çerçeve bilinen adı (tfd) | Uygulanan <br/> .NET Standard sürümü |
| :-------------------: | :-------------------------: | :----------------------------: | :-------------------------------------: |
| .NET Standard         | 2,0                         | Netstandard 2.0                 | Yok                                     |
| .NET Core             | 2.2                         | netcoreapp 2.2                  | 2,0                                     |
| .NET Framework        | 4.8                         | net48                          | 2,0                                     |

## <a name="supported-target-framework-versions"></a>Desteklenen hedef Framework sürümleri

Bir hedef çerçeveye genellikle tfd tarafından başvurulur. Aşağıdaki tabloda .NET Core SDK ve NuGet istemcisi tarafından desteklenen hedef çerçeveler gösterilmektedir. Eşdeğerleri köşeli ayraç içinde gösterilir. Örneğin, `win81` ile `netcore451`eşdeğer bir TFI vardır.

| Hedef Çerçeve           | TFM |
| -------------------------- | --- |
| .NET Standard              | Netstandard 1.0<br>Netstandard 1.1<br>Netstandard 1.2<br>Netstandard 1.3<br>Netstandard 1.4<br>Netstandard 1.5<br>Netstandard 1.6<br>Netstandard 2.0 |
| .NET Core                  | netcoreapp 1.0<br>netcoreapp 1.1<br>netcoreapp 2.0<br>netcoreapp 2.1<br>netcoreapp 2.2 |
| .NET Framework             | net11<br>net20<br>net35<br>net40<br>net403<br>net45<br>net451<br>net452<br>net46<br>net461<br>net462<br>net47<br>net471<br>net472<br>net48 |
| Windows Mağazası              | netcore [netcore45]<br>netcore45 [Win] [Win8]<br>netcore451 [win81] |
| .NET mikro Framework       | netmf |
| Silverlight                | sl4<br>sl5 |
| Windows Phone              | WP [WP7]<br>wp7<br>wp75<br>WP8<br>wp81<br>wpa81 |
| Evrensel Windows Platformu | UAP [UAP 10.0]<br>UAP 10.0 [win10] [netcore50] |

## <a name="how-to-specify-target-frameworks"></a>Hedef çerçeveleri belirtme

Hedef çerçeveler, proje dosyanızda belirtilir. Tek bir hedef çerçeve belirtildiğinde, **TargetFramework** öğesini kullanın. Aşağıdaki konsol uygulaması proje dosyası, .NET Core 2,2 ' nin nasıl hedefleyeceğinizi göstermektedir:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>
  </PropertyGroup>

</Project>
```

Birden çok hedef çerçeve belirttiğinizde, her bir hedef çerçeve için derlemelere koşullu başvuru yapabilirsiniz. Kodunuzda, *if-then-else* mantığıyla önişlemci sembolleri kullanarak bu derlemelerde koşullu olarak derleyebilirsiniz.

Aşağıdaki kitaplık proje dosyası, .NET Framework (`netstandard1.4``net40` ve `net45`) .NET Standard () API 'lerini ve API 'leri hedefler. Birden çok hedef çerçeve ile çoğul **Targetçerçeveler** öğesini kullanın. Kitaplık iki .NET Framework `Condition` tfms için derlendikten sonra, özniteliklere uygulamaya özgü paketleri nasıl dahil edileceğini aklınızda edin:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

Kitaplığınızın veya uygulamanızın içinde her bir hedef çerçeve için derlemek üzere koşullu kod yazarsınız:

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45  
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

Yapı sistemi, [desteklenen hedef Framework sürümleri](#supported-target-framework-versions) tablosunda gösterilen hedef çerçeveleri temsil eden Önişlemci simgelerinin farkındadır. .NET Standard veya .NET Core tfd 'yi temsil eden bir sembol kullanırken, noktayı alt çizgiyle değiştirin ve küçük harfleri büyük harfe değiştirin (örneğin, sembolü `netstandard1.4` `NETSTANDARD1_4`).

.NET Core hedef çerçeveleri için Önişlemci simgelerinin tüm listesi şunlardır:

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a>Kullanım dışı hedef çerçeveler

Aşağıdaki hedef çerçeveler kullanım dışıdır. Bu hedef çerçeveleri hedefleyen paketlerin belirtilen değişikliklere geçirilmesi gerekir.

| Kullanımdan kaldırılan TFA                                                                             | Başka |
| ------------------------------------------------------------------------------------------ | ----------- |
| aspnet50<br>aspnetcore50<br>adlar<br>DNX<br>dnx45<br>dnx451<br>dnx452                  | netcoreapp  |
| dotnet<br>dotnet50<br>dotnet51<br>dotnet52<br>dotnet53<br>dotnet54<br>dotnet55<br>dotnet56 | Netstandard |
| netcore50                                                                                  | UAP 10.0     |
| kazanırsınız                                                                                        | netcore45   |
| Win8                                                                                       | netcore45   |
| win81                                                                                      | netcore451  |
| win10                                                                                      | UAP 10.0     |
| wınrt                                                                                      | netcore45   |

## <a name="see-also"></a>Ayrıca bkz.

- [Paketler, Meta Paketler ve Çerçeveler](../core/packages.md)
- [Platformlar Arası Araçlarla Kitaplık Geliştirme](../core/tutorials/libraries.md)
- [.NET Standard](net-standard.md)
- [.NET Core sürümü oluşturma](../core/versions/index.md)
- [DotNet/standart GitHub deposu](https://github.com/dotnet/standard)
- [NuGet araçları GitHub deposu](https://github.com/joelverhagen/NuGetTools)
- [.NET 'teki Framework profilleri](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)
