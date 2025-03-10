---
title: Yeniden oluşturulmuş bağlama yeniden yönlendirmelerini etkinleştir veya devre dışı bırak
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: 178d5070dd7018bbc0fce474cdd0b31ba3d17f77
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913040"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>Nasıl yapılır: Otomatik Bağlama Yönlendirmesini Etkinleştirme veya Devre Dışı Bırakma

Visual Studio 'da .NET Framework 4.5.1 ve sonraki sürümleri hedefleyen uygulamalar derlerken, bağlama yeniden yönlendirmeleri, derleme birleşme işlemini geçersiz kılmak için uygulama yapılandırma dosyasına otomatik olarak eklenebilir. Uygulamanız veya bileşenleri, aynı derlemenin birden çok sürümüne başvurursa, uygulamanızın yapılandırma dosyasında bağlama yeniden yönlendirmelerini el ile belirtseniz de, bağlama yeniden yönlendirmeleri eklenir. Otomatik bağlama yeniden yönlendirme özelliği, bir Web uygulaması için davranış biraz farklı olsa da, .NET Framework 4.5.1 veya sonraki bir sürümü hedefleyen masaüstü uygulamalarını ve Web uygulamalarını etkiler. .NET Framework önceki sürümlerini hedefleyen mevcut uygulamalarınız varsa otomatik bağlama yeniden yönlendirmesini etkinleştirebilir veya bağlama yeniden yönlendirmelerini el ile yazmak istiyorsanız bu özelliği devre dışı bırakabilirsiniz.

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a>Masaüstü uygulamalarında otomatik bağlama yeniden yönlendirmelerini devre dışı bırak

Otomatik bağlama yeniden yönlendirmeleri, .NET Framework 4.5.1 ve sonraki sürümleri hedefleyen Windows Masaüstü uygulamaları için varsayılan olarak etkindir. Bağlama yeniden yönlendirmeleri, uygulama derlendikten sonra çıkış yapılandırması (**app. config**) dosyasına eklenir ve başka bir şekilde gerçekleşmekte olan derleme birleşme işlemini geçersiz kılar. Kaynak **app. config** dosyası değiştirilmez. Uygulama için proje dosyasını değiştirerek veya Visual Studio 'daki proje özelliklerinde bir onay kutusunun seçimini kaldırarak bu özelliği devre dışı bırakabilirsiniz.

### <a name="disable-through-project-properties"></a>Proje özellikleri aracılığıyla devre dışı bırak

Visual Studio 2017 sürüm 15,7 veya sonraki bir sürümü varsa, projenin özellik sayfalarındaki otomatik olarak oluşturulan bağlamayı kolayca devre dışı bırakabilirsiniz.

1. Projeye sağ **Çözüm Gezgini** seçip **özellikleri**.

2. **Uygulama** sayfasında **bağlama yeniden yönlendirmeleri otomatik oluştur** seçeneğinin işaretini kaldırın.

3. Değişikliği kaydetmek için **CTRL**+**S** tuşuna basın.

### <a name="disable-manually-in-the-project-file"></a>Proje dosyasında el ile devre dışı bırak

1. Aşağıdaki yöntemlerden birini kullanarak, proje dosyasını düzenlenmek üzere açın:

   - Visual Studio 'da **Çözüm Gezgini**' de projeyi seçin ve sonra kısayol menüsünden **klasörü dosya Gezgini 'nde aç** ' ı seçin. Dosya Gezgini 'nde, proje (. csproj veya. vbproj) dosyasını bulun ve Not defteri 'nde açın.
   - Visual Studio 'da, **Çözüm Gezgini**, projeye sağ tıklayın ve **Projeyi Kaldır**' ı seçin. Kaldırılmış projeyi yeniden sağ tıklatın ve ardından **Düzenle [ProjectName. csproj]** öğesini seçin.

2. Proje dosyasında aşağıdaki özellik girdisini bulun:

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. Şu `true` şekilde`false`değiştirin:

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a>Otomatik bağlama yeniden yönlendirmelerini el ile etkinleştir

.NET Framework eski sürümlerini hedefleyen mevcut uygulamalarda veya yeniden yönlendirme eklemeniz için otomatik olarak sorulmayan durumlarda otomatik bağlama yeniden yönlendirmelerini etkinleştirebilirsiniz. Framework 'ün daha yeni bir sürümünü hedefliyorsanız, ancak otomatik olarak yeniden yönlendirme eklemek isteyip istemediğiniz sorulduğunda, derlemeleri yeniden eşlemek için büyük olasılıkla derleme çıkışı alacaksınız.

1. Aşağıdaki yöntemlerden birini kullanarak, proje dosyasını düzenlenmek üzere açın:

   - Visual Studio 'da **Çözüm Gezgini**' de projeyi seçin ve sonra kısayol menüsünden **klasörü dosya Gezgini 'nde aç** ' ı seçin. Dosya Gezgini 'nde, proje (. csproj veya. vbproj) dosyasını bulun ve Not defteri 'nde açın.
   - Visual Studio 'da, **Çözüm Gezgini**, projeye sağ tıklayın ve **Projeyi Kaldır**' ı seçin. Kaldırılmış projeyi yeniden sağ tıklatın ve ardından **Düzenle [ProjectName. csproj]** öğesini seçin.

2. Aşağıdaki öğeyi ilk yapılandırma özellik grubuna ekleyin ( \<PropertyGroup > etiketinin altında):

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   Aşağıda, ekli öğe içeren örnek bir proje dosyası gösterilmektedir:

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
     <PropertyGroup>
       <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
       <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
       <ProjectGuid>{123334}</ProjectGuid>
       ...
       <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
     </PropertyGroup>
     ...
   </Project>
   ```

3. Uygulamalarınızı derleyin.

## <a name="enable-automatic-binding-redirects-in-web-apps"></a>Web uygulamalarında otomatik bağlama yeniden yönlendirmelerini etkinleştirme

Otomatik bağlama yeniden yönlendirmeleri, web uygulamaları için farklı şekilde uygulanır. Kaynak yapılandırma (**Web. config**) dosyasının Web uygulamaları için değiştirilmesi gerektiğinden, bağlama yeniden yönlendirmeleri yapılandırma dosyasına otomatik olarak eklenmez. Ancak Visual Studio, bağlama çakışmalarını size bildirir ve çakışmaları çözümlemek için bağlama yeniden yönlendirmeleri ekleyebilirsiniz. Her zaman bağlama yeniden yönlendirmeleri eklemeniz istentiğinden, bir Web uygulaması için bu özelliği açıkça devre dışı bırakmanız gerekmez.

Bir **Web. config** dosyasına bağlama yeniden yönlendirmeleri eklemek için:

1. Visual Studio'da uygulamayı derleyin ve yapı uyarılarını denetleyin.

   ![Derleme başvurusu çakışmaları Için derleme uyarısı](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")

2. Derleme bağlama çakışmaları varsa bir uyarı görüntülenir. Uyarıya çift tıklayın veya uyarıyı seçin ve **ENTER**tuşuna basın.

   Kaynak **Web. config** dosyasına gerekli bağlama yeniden yönlendirmelerini otomatik olarak eklemenize olanak sağlayan bir iletişim kutusu görüntülenir.

   ![Bağlama yeniden yönlendirme izni iletişim kutusu](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")

## <a name="see-also"></a>Ayrıca bkz.

- [\<bindingRedirect > öğesi](./file-schema/runtime/bindingredirect-element.md)
- [Bütünleştirilmiş Kod Sürümlerini Yönlendirme](redirect-assembly-versions.md)
