---
title: .NET Core csproj biçimine eklemeler
description: Varolan ve .NET Core csproj dosyalarına arasındaki farklar hakkında bilgi edinin
author: blackdwarf
ms.date: 09/22/2017
ms.openlocfilehash: 8b44c445fbfd3d15cc8e6c53e640a8ae5e284d27
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836221"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a>.NET Core csproj biçimine eklemeler

Bu belge proje dosyaları taşımak bir parçası olarak eklenmiş olan değişiklikler özetlenmektedir *project.json* için *csproj* ve [MSBuild](https://github.com/Microsoft/MSBuild). Genel proje dosyasının söz dizimi ve başvurusu hakkında daha fazla bilgi için bkz: [MSBuild proje dosyası](/visualstudio/msbuild/msbuild-project-file-schema-reference) belgeleri.  

## <a name="implicit-package-references"></a>Örtük paket başvuruları
Meta paketler dolaylı olarak başvurulan belirtilen hedef çerçeveleri göre `<TargetFramework>` veya `<TargetFrameworks>` proje dosyanızın özelliği. `<TargetFrameworks>` yoksayılır `<TargetFramework>` olduğu belirtildiğinde, sipariş bağımsızdır.

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a>Öneriler
Bu yana `Microsoft.NETCore.App` veya `NetStandard.Library` meta paketler dolaylı olarak başvurulan, önerilen en iyi yöntemlerimizi aşağıda verilmiştir:

* .NET Core veya .NET Standard hedeflenirken açık bir başvuru hiçbir zaman sahip `Microsoft.NETCore.App` veya `NetStandard.Library` meta paketler aracılığıyla bir `<PackageReference>` proje dosyanızda öğesi.
* .NET Core'u hedefleyen, belirli bir çalışma zamanı sürümünü gerekiyorsa kullanmalısınız `<RuntimeFrameworkVersion>` projenizdeki özelliği (örneğin, `1.0.4`) metapackage başvuran yerine.
    * Kullanıyorsanız gerçekleşebilir [müstakil dağıtımları](../deploying/index.md#self-contained-deployments-scd) 1.0.0 belirli bir düzeltme eki sürümü ihtiyacınız ve örneğin LTS çalışma zamanı.
* Belirli bir sürümünü gerekiyorsa `NetStandard.Library` kullanabileceğiniz .NET Standard hedeflenirken metapackage `<NetStandardImplicitPackageVersion>` özelliği ve kümesi sürümü ihtiyacınız.
* Açıkça eklemeyin veya güncelleştirme ya da başvuruları `Microsoft.NETCore.App` veya `NetStandard.Library` metapackage .NET Framework projelerindeki. Herhangi bir sürümünü `NetStandard.Library` NuGet bir .NET Standard tabanlı NuGet paketini otomatik olarak kullanarak bu sürümü yüklendiğinde gereklidir.

## <a name="default-compilation-includes-in-net-core-projects"></a>.NET Core projelerinde varsayılan derleme içerir
Git ile *csproj* biçimi en son SDK sürümlerinde, varsayılan içerir ve derleme öğeleri ve SDK'sı özellikleri dosyalarının gömülü kaynaklar için dışlar Taşındık. Bu, artık bu öğeler, proje dosyanızda belirtmek gerektiği anlamına gelir. 

Bunu yapmak için ana nedeni, proje dosyanızda dağınıklık azaltmaktır. Oluşturduğunuz her projede tekrarlamanız gerekmez. Bu nedenle en yaygın kullanım örnekleri, SDK'da bulunan Varsayılanları kapsamalıdır. Bu, gerekirse yanı sıra anlamak, el ile düzenlemek çok daha kolay olan daha küçük proje dosyaları için yol açar. 

Aşağıdaki tablo, hangi öğe ve hangi gösterir [eğik çizgi genelleştirmeler](https://en.wikipedia.org/wiki/Glob_(programming)) her ikisi de dahil ve hariç SDK'yı: 

| Öğe           | Glob içerir                              | Glob Dışla                                                  | Glob Kaldır                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| Derleme           | \*\*/\*.cs (veya diğer dil uzantıları) | \*\*/\*.user;  \*\*/\*.\* Proj;  \* \* / \*.sln;  \* \* / \*.vssscc  | Yok                        |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | Yok                        |
| Hiçbiri              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | - \*\*/\*.cs; \* \* / \*.resx |

Projenizde eğik çizgi genelleştirmeler sahip ve en son SDK'sını kullanarak oluşturmaya çalışırsanız, aşağıdaki hatayı alırsınız:

> Yinelenen Derleme öğeleri dahil. .NET SDK'sı varsayılan olarak, proje dizinine derleme öğeleri içerir. Bu öğeler proje dosyanızdan kaldırın ya da proje dosyanızda bunları açıkça eklemek istiyorsanız 'EnableDefaultCompileItems' özelliği 'false' ayarlayın. 

Bu hataya almak için ya da açık kaldırabilirsiniz `Compile` olanlarla eşleşmesi öğeleri önceki tabloda listelenen veya ayarlayabilirsiniz `<EnableDefaultCompileItems>` özelliğini `false`, şöyle:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
Bu özelliği ayarlamak `false` burada b varsayılan eğik çizgi genelleştirmeler projenizde belirlemek için önceki SDK'ları davranışını geri dönülüyor örtük ekleme, devre dışı bırakır.

Bu değişiklik, ana değiştirmez, diğer mekanizması içerir. Örneğin, uygulamanız ile yayımlanan için bazı dosyaları belirtmek istiyorsanız ancak içinde bilinen mekanizmaları kullanmaya devam edebilirsiniz *csproj* söz konusu (örneğin, `<Content>` öğesi).

`<EnableDefaultCompileItems>` yalnızca devre dışı bırakır `Compile` eğik çizgi genelleştirmeler diğer eğik çizgi genelleştirmeler, örtük gibi etkilemez ancak `None` için de geçerli glob \*.cs öğeleri. Nedeniyle **Çözüm Gezgini** show devam edecek \*.cs öğeleri dahil, bir projenin parçası olarak `None` öğeleri. Benzer şekilde, kullandığınız `<EnableDefaultNoneItems>` örtük devre dışı bırakmak için `None` glob.

Devre dışı bırakmak için **tüm örtük eğik çizgi genelleştirmeler**, ayarlayabileceğiniz `<EnableDefaultItems>` özelliğini `false` aşağıdaki örnekteki gibi:
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a>MSBuild gördüğünde gibi tüm proje görme

Csproj değişiklikleri proje dosyaları büyük ölçüde basitleştirme olsa da, SDK ve hedeflerine dahil olduğunda gördüğünde MSBuild gibi tam olarak genişletilmiş proje görmek isteyebilirsiniz. Projeyle önişle [ `/pp` geçiş](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) , [ `dotnet msbuild` ](dotnet-msbuild.md) komutunu Katkıları derleme için hangi dosyaların içeri aktarılan hangi gösterir ve kaynakları gerçekten Proje oluşturma:

`dotnet msbuild -pp:fullproject.xml`

Birden çok hedef çerçeve proje varsa komutun sonuçlarını yalnızca bunlardan birine bir MSBuild özellik olarak belirterek odaklanmış olur:

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a>Eklemeleri

### <a name="sdk-attribute"></a>SDK'sı özniteliği 
Kök `<Project>` öğesinin *.csproj* dosya adlı yeni bir öznitelik sahip `Sdk`. `Sdk` SDK'sı olacağı belirtir proje tarafından kullanılan. SDK'sı olarak [katmanlama belge](cli-msbuild-architecture.md) açıklar, MSBuild kümesidir [görevleri](/visualstudio/msbuild/msbuild-tasks) ve [hedefleri](/visualstudio/msbuild/msbuild-targets) .NET Core kod oluşturabilirsiniz. Biz, .NET Core araçları ile üç ana SDK'ları gönderin:

1. .NET Core SDK kimliği `Microsoft.NET.Sdk`
2. .NET Core web SDK kimliği `Microsoft.NET.Sdk.Web`
3. SDK kimliği ile .NET Core Razor sınıf kitaplığı, `Microsoft.NET.Sdk.Razor`

İhtiyacınız `Sdk` öznitelik kümesi bu kimlikler birine üzerinde `<Project>` .NET Core araçları kullanın ve kodu derleyebilmeniz için öğesi. 

### <a name="packagereference"></a>PackageReference
A `<PackageReference>` öğesi öğeyi belirten bir [projedeki NuGet bağımlılık](/nuget/consume-packages/package-references-in-project-files). `Include` Özniteliği paket kimliğini belirtir 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a>Sürüm
Gerekli `Version` özniteliği geri yüklemek için paket sürümünü belirtir. Öznitelik kurallarına uyar [NuGet sürüm](/nuget/reference/package-versioning#version-ranges-and-wildcards) düzeni. Bir tam sürüm eşleşiyorsa varsayılan davranıştır. Örneğin, belirten `Version="1.2.3"` NuGet gösterimine eşdeğerdir `[1.2.3]` tam 1.2.3-Beta için Paket sürümü.

#### <a name="includeassets-excludeassets-and-privateassets"></a>IncludeAssets ve ExcludeAssets PrivateAssets
`IncludeAssets` öznitelik belirtir ait hangi varlıklar tarafından paket belirtilen `<PackageReference>` kullanılması. Varsayılan olarak, tüm paket varlıklar dahil edilir.

`ExcludeAssets` öznitelik belirtir ait hangi varlıklar tarafından paket belirtilen `<PackageReference>` değil kullanılması.

`PrivateAssets` öznitelik belirtir ait hangi varlıklar tarafından paket belirtilen `<PackageReference>` kullanılması ancak sonraki projeye akış değil. `Analyzers`, `Build` Ve `ContentFiles` bu özniteliği mevcut olmadığında varlıkları varsayılan olarak özel.

> [!NOTE]
> `PrivateAssets` eşdeğerdir *project.json*/*xproj* `SuppressParent` öğesi.

Bu öznitelik, bir veya daha fazla noktalı virgülle ayrılmış aşağıdaki öğeleri içerebilir `;` listeleniyorsa, birden fazla karakter:

* `Compile` -lib klasörünün içeriğini karşı derleme kullanılabilir.
* `Runtime` – çalışma zamanı klasörünün içeriğini dağıtılır.
* `ContentFiles` – içeriği *contentfiles* klasörü kullanılır.
* `Build` – derleme klasörü özellikler/hedeflerin kullanılır.
* `Native` – içeriği yerel varlıklar, çalışma zamanı için çıktı klasörüne kopyalanır.
* `Analyzers` – Çözümleyicileri kullanılır.

Alternatif olarak, öznitelik içerebilir:

* `None` – varlıkları hiçbiri kullanılır.
* `All` – tüm varlıkları kullanılır.

### <a name="dotnetclitoolreference"></a>DotNetCliToolReference
A `<DotNetCliToolReference>` öğesi öğesi, kullanıcının proje bağlamında geri yüklemek için istediği CLI aracı belirtir. Bir ardılı olan `tools` düğümünde *project.json*. 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a>Sürüm
`Version` geri yüklemek için paket sürümünü belirtir. Öznitelik kurallarına uyar [NuGet sürüm](/nuget/create-packages/dependency-versions#version-ranges) düzeni. Bir tam sürüm eşleşiyorsa varsayılan davranıştır. Örneğin, belirten `Version="1.2.3"` NuGet gösterimine eşdeğerdir `[1.2.3]` tam 1.2.3-Beta için Paket sürümü.

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers
`<RuntimeIdentifiers>` Özellik öğesi noktalı virgülle ayrılmış bir listesini belirtmenize olanak tanır [çalışma zamanı tanımlayıcılarının (RID'ler)](../rid-catalog.md) projesi için. RID yayımlama müstakil dağıtımları etkinleştirin. 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a>RuntimeIdentifier
`<RuntimeIdentifier>` Özellik öğesi yalnızca bir belirtmenize olanak verir [çalışma zamanı tanımlayıcı (RID)](../rid-catalog.md) projesi için. RID kendi içinde bir dağıtım yayımlama sağlar.

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

Kullanım `<RuntimeIdentifiers>` (çoğul) bunun yerine birden çok çalışma zamanlarını yayımlamak gerekiyorsa. `<RuntimeIdentifier>` tek bir çalışma zamanı gerektiğinde daha hızlı derlemeler sağlar.

### <a name="packagetargetfallback"></a>PackageTargetFallback 
`<PackageTargetFallback>` Özellik öğesi, bir dizi paketler geri yüklenirken kullanılacak uyumlu hedefleri belirtmenize olanak sağlar. Dotnet kullanan paketleri izin vermek için tasarlanmış [TxM (x hedef ad)](/nuget/schema/target-frameworks) bir dotnet TxM bildirmeyin paketlerle çalışılacak. Projenizin kullandığı dotnet TxM sonra eklediğiniz sürece bir dotnet TxM, duruma göre değişir üzerinde gerekir ayrıca tüm paketlere sahip `<PackageTargetFallback>` dotnet ile uyumlu olacak şekilde dotnet olmayan platformlar için projenize. 

Aşağıdaki örnek, projenizdeki tüm hedefleri için geri dönüşler sağlar: 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

Aşağıdaki örnek, geri dönüşler yalnızca belirtir `netcoreapp2.1` hedef:

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a>NuGet meta veri özelliklerini
MSBuild için taşıma ile NuGet paketinden paketleme sırasında kullanılan giriş meta verileri geçtiğimizi *project.json* için *.csproj* dosyaları. Kullanıcılarınızın içinde gitmek zorunda MSBuild özellikleri girişleri bir `<PropertyGroup>` grubu. Paketleme işleminin girdi olarak kullanılırken kullanılacak özellikleri listesi aşağıdadır `dotnet pack` komutu veya `Pack` MSBuild hedef diğer bir deyişle SDK'ın bir parçası. 

### <a name="ispackable"></a>IsPackable
Proje paketlenmiş olup olmadığını belirten bir Boole değeri. Varsayılan değer `true` şeklindedir. 

### <a name="packageversion"></a>PackageVersion
Sonuç paketine sahip olacak sürümünü belirtir. NuGet sürüm dizesinin tüm forms kabul eder. Varsayılan değer değeri `$(Version)`, diğer bir deyişle, özelliğin `Version` projedeki. 

### <a name="packageid"></a>PackageId
Sonuçta elde edilen paket adını belirtir. Belirtilmezse, `pack` işlemi için kullanılacak varsayılan `AssemblyName` veya dizin adı olarak paketin adı. 

### <a name="title"></a>Başlık
Nuget.org ve Visual Studio'da Paket Yöneticisi UI görünümlerde genellikle kullanılan paket bir insan dostu başlığı. Belirtilmezse, paket kimliği yerine kullanılır.

### <a name="authors"></a>Yazarlar
Nuget.org profil adları eşleşen paketleri yazar, noktalı virgülle ayrılmış listesi. Bunlar nuget.org NuGet galerisinde görüntülenir ve paketleri çapraz başvuru için aynı yazarları tarafından kullanılır.

### <a name="packagedescription"></a>PackageDescription

Kullanıcı Arabirimi ekranı için paketinin uzun açıklaması.

### <a name="description"></a>Açıklama
Derleme için uzun açıklaması. Varsa `PackageDescription` bu özellik paketi açıklama olarak da kullanılır belirtilmedi.

### <a name="copyright"></a>Telif Hakkı
Paketi için telif hakkı ayrıntıları.

### <a name="packagerequirelicenseacceptance"></a>PackageRequireLicenseAcceptance
İstemci paketi yüklemeden önce paket lisansını kabul etmek için tüketici sor olup olmadığını belirten bir Boole değeri. Varsayılan, `false` değeridir.

### <a name="packagelicenseexpression"></a>PackageLicenseExpression

Bir [SPDX lisans tanımlayıcısı](https://spdx.org/licenses/) veya ifade. Örneğin: `Apache-2.0`

Tam listesi sunulmaktadır [SPDX lisans tanımlayıcıları](https://spdx.org/licenses/). NuGet.org yalnızca OSI kabul eder veya kullanırken onaylanan FSF lisans türü ifadesi lisansı.

Bir lisans ifadenin tam sözdizimi aşağıda açıklanan [ABNF](https://tools.ietf.org/html/rfc5234).
```cli
license-id            = <short form license identifier from https://spdx.org/spdx-specification-21-web-version#h.luq9dgcle9mo>

license-exception-id  = <short form license exception identifier from https://spdx.org/spdx-specification-21-web-version#h.ruv3yl8g6czd>

simple-expression = license-id / license-id”+”

compound-expression =  1*1(simple-expression /
                simple-expression "WITH" license-exception-id /
                compound-expression "AND" compound-expression /
                compound-expression "OR" compound-expression ) /                
                "(" compound-expression ")" )

license-expression =  1*1(simple-expression / compound-expression / UNLICENSED)
```

> [!NOTE]
> Yalnızca biri `PackageLicenseExpression`, `PackageLicenseFile` ve `PackageLicenseUrl` teker teker belirtilebilir.

### <a name="packagelicensefile"></a>PackageLicenseFile

SPDX tanımlayıcı atanmamış lisans kullandığınız ya da özel bir lisanstır paket içindeki bir lisans dosyası yolu (Aksi takdirde `PackageLicenseExpression` VPN'ye olan)

Değiştirir `PackageLicenseUrl`, ile birleştirilemez `PackageLicenseExpression` ve Visual Studio 15.9.4, .NET SDK'sı 2.1.502 veya 2.2.101, gerektirir ya da daha yeni.

Lisans dosyası, proje için örnek kullanım açıkça ekleyerek iyileştirmesiyle doludur emin olmak ihtiyacınız olacak:
```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a>PackageLicenseUrl

Bir paket için uygun olan lisans URL'si. (_Visual Studio 15.9.4, .NET SDK'sı 2.1.502 ve 2.2.101 beri kullanım dışı_)


### <a name="packageiconurl"></a>PackageIconUrl
Kullanıcı Arabirimi ekranı pakette için simge olarak kullanılacak bir URL saydam arka plana sahip 64 x 64 görüntüsü.

### <a name="packagereleasenotes"></a>PackageReleaseNotes
Paket için sürüm notları.

### <a name="packagetags"></a>PackageTags
Etiketleri noktalı virgülle ayrılmış bir listesini, paketi belirler.

### <a name="packageoutputpath"></a>PackageOutputPath
Paketlenmiş paket bırakılır çıkış yolu belirler. Varsayılan değer `$(OutputPath)`. 

### <a name="includesymbols"></a>IncludeSymbols
Proje dolu olduğunda paketi bir ek sembol paketi oluşturmak bu Boolean değerini gösterir. Bu paket olacaktır bir *. symbols.nupkg* uzantısı ve PDB dosyaları DLL ile birlikte ve diğer çıktı dosyalarını kopyalar.

### <a name="includesource"></a>IncludeSource
Paketi işlemi bir kaynak paketi oluşturmanız gerekir, bu Boolean değeri gösterir. Kaynak Paketi kitaplığın kaynak kodunun yanı sıra PDB dosyaları içerir. Kaynak dosyaları altında isimlerine `src/ProjectName` elde edilen paket dosyasındaki dizin. 

### <a name="istool"></a>IsTool
Tüm çıkış dosyalarını kopyalanıp kopyalanmayacağını belirtir *Araçları* klasörü yerine *LIB* klasör. Bu farklı olduğunu unutmayın bir `DotNetCliTool` , belirtilen ayarlayarak `PackageType` içinde *.csproj* dosya.

### <a name="repositoryurl"></a>RepositoryUrl
Depo URL'si, paket için kaynak kodu bulunduğu yerde ve/veya hangi, oluşturulmakta olduğunu belirtir. 

### <a name="repositorytype"></a>RepositoryType
Depo türünü belirtir. "Git" varsayılandır. 

### <a name="nopackageanalysis"></a>NoPackageAnalysis
Paketi paket analiz paketini oluşturduktan sonra çalışmaması gerektiğini belirtir.

### <a name="minclientversion"></a>MinClientVersion
Nuget.exe ve Visual Studio Paket Yöneticisi tarafından zorlanan, bu paketi yüklemek NuGet istemci en düşük sürümünü belirtir.

### <a name="includebuildoutput"></a>IncludeBuildOutput
Bu Boolean değerleri belirten derleme çıktı derlemeleri halinde paketlenmiş olup olmadığını *.nupkg* dosya ya da değil.

### <a name="includecontentinpack"></a>IncludeContentInPack
Bu Boolean değerini tüm öğeleri, bir türü sahip olup olmadığını belirtir `Content` sonuç paketine otomatik olarak dahil edilir. Varsayılan, `true` değeridir. 

### <a name="buildoutputtargetfolder"></a>BuildOutputTargetFolder
Klasörü çıkış derlemelerin yerleştirileceği yeri belirtir. Çıkış bütünleştirilmiş kodları (ve diğer çıktı dosyalarının) ilgili framework klasörlerine kopyalanır.

### <a name="contenttargetfolders"></a>ContentTargetFolders
Bu özellik tüm içerik dosyalarını, nereye varsayılan konumu belirtir `PackagePath` kendileri için belirtilmedi. Varsayılan değer: "içerik; contentFiles".

### <a name="nuspecfile"></a>NuspecFile
Göreli veya mutlak yolunu *.nuspec* paketleme için kullanılan dosya. 

> [!NOTE]
> Varsa *.nuspec* dosya belirtilir, kullanıldığı **özel** için bilgi ve herhangi bir bilgi projelerindeki paketleme kullanılmaz. 

### <a name="nuspecbasepath"></a>NuspecBasePath
Temel yolunu *.nuspec* dosya.

### <a name="nuspecproperties"></a>NuspecProperties
Noktalı virgülle ayrılmış listesi anahtar = değer çiftleri.

## <a name="assemblyinfo-properties"></a>AssemblyInfo özellikleri
[Derleme özniteliklerinin](../../framework/app-domains/set-assembly-attributes.md) , genellikle mevcut bir *AssemblyInfo* dosya artık otomatik olarak üretilen özellikleri.

### <a name="properties-per-attribute"></a>Öznitelik başına özellikleri

Her öznitelik içeriği ve başka neslini aşağıdaki tabloda gösterildiği gibi devre dışı bırakmak için denetleyen bir özelliğe sahiptir:

| Öznitelik                                                      | Özellik               | Özelliği devre dışı bırakmak için                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

Notlar:

* `AssemblyVersion` ve `FileVersion` değerini almak için varsayılandır `$(Version)` soneki olmadan. Örneğin, varsa `$(Version)` olduğu `1.2.3-beta.4`, değer sonra `1.2.3`.
* `InformationalVersion` değerini varsayılan olarak `$(Version)`.
* `InformationalVersion` sahip `$(SourceRevisionId)` özelliği varsa eklenir. Bunu kullanarak devre dışı bırakılabilir `IncludeSourceRevisionInInformationalVersion`.
* `Copyright` ve `Description` özellikleri NuGet meta veriler için de kullanılır.
* `Configuration` tüm yapı işlemi ile paylaşılır ve aracılığıyla ayarlanan `--configuration` parametresinin `dotnet` komutları.

### <a name="generateassemblyinfo"></a>GenerateAssemblyInfo 
Etkinleştirme veya tüm AssemblyInfo oluşturma devre dışı bırakan bir Boole değeri. Varsayılan değer `true` şeklindedir. 

### <a name="generatedassemblyinfofile"></a>GeneratedAssemblyInfoFile 
Oluşturulan derleme bilgileri dosyasının yolu. Varsayılan bir dosyaya `$(IntermediateOutputPath)` (obj) dizini.
