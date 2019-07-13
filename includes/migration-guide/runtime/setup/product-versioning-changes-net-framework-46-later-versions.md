---
ms.openlocfilehash: fca31a98c2dd3427501b3c6bfe4f52fcec086709
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858452"
---
### <a name="product-versioning-changes-in-the-net-framework-46-and-later-versions"></a>.NET Framework 4.6 ve sonraki sürümlerde ürün sürümü oluşturma değişiklikleri

|   |   |
|---|---|
|Ayrıntılar|Ürün sürümü oluşturma, .NET Framework'ün önceki sürümlerden ve özellikle de .NET Framework 4, 4.5, 4.5.1, değişmiş ve ayrıntılı değişiklikleri 4.5.2.The şunlardır:<ul><li>Değerini <code>Version</code> girişi <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full</code> anahtarı değişen <code>4.6.xxxxx</code> .NET Framework 4.6 ve onun nokta sürümleri ve için <code>4.7.xxxxx</code> .NET Framework 4.7 ve 4.7.1. İsteğe bağlı olarak .NET Framework 4.5, 4.5.1 ve 4.5.2'yi, formatına sahip <code>4.5.xxxxx</code>.</li><li>.NET Framework dosyalar için dosya ve ürün sürümü oluşturma 4.0.30319.x önceki sürüm oluşturma düzeni 4.6.X.0 .NET Framework 4.6 ve onun nokta sürümleri ve 4.7.X.0 için .NET Framework 4.7 ve 4.7.1 değişti. Bir dosya sağ tıklattıktan sonra dosyanın özelliklerini görüntülerken, bu yeni değerleri görebilirsiniz.</li><li><xref:System.Reflection.AssemblyFileVersionAttribute> Ve <xref:System.Reflection.AssemblyInformationalVersionAttribute> Yönetilen derlemeler biçiminde sürümü değerlerine sahip öznitelikler için .NET Framework 4.6 ve onun nokta sürümleri ve .NET Framework 4.7 ve 4.7.1 4.7.X.0 4.6.X.0.</li><li>.NET Framework 4.6, 4.6.1, 4.6.2, 4.7 ve 4.7.1, <xref:System.Environment.Version?displayProperty=nameWithType> özellik sabit sürüm dizesi döndürür <code>4.0.30319.42000</code>. İsteğe bağlı olarak .NET Framework 4, 4.5, 4.5.1 ve 4.5.2'yi, sürüm dizeleri biçimde döndürür <code>4.0.30319.xxxxx</code> (örneğin, &quot;4.0.30319.18010&quot;). Uygulama kodu herhangi bir yeni bağımlılık Environment.Version özelliği alma önermiyoruz unutmayın.</li></ul>Daha fazla bilgi için [nasıl yapılır: Hangi .NET Framework sürümlerinin yüklü olduğunu belirleme](~/docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).|
|Öneri|Genel olarak, uygulamaların çalışma zamanı sürümü, .NET Framework ve yükleme dizini gibi şeyler saptamak için önerilen teknikleri bağımlı:<ul><li>.NET Framework'ün çalışma zamanı sürümü algılamak için bkz: [nasıl yapılır: Hangi .NET Framework sürümlerinin yüklü olduğunu belirleme](~/docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</li><li>.NET Framework yükleme yolunu belirlemek için değerini kullanın. <code>InstallPath</code> girişi <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full</code> anahtarı.</li></ul> <blockquote> [!IMPORTANT] Alt anahtar adı <code>NET Framework Setup</code>değil <code>.NET Framework Setup</code>.</blockquote> <ul><li>.NET Framework ortak dil çalışma zamanı dizin yolu belirlemek için çağrı <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory?displayProperty=nameWithType> yöntemi.</li><li>CLR sürümünü almak için arama <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion?displayProperty=nameWithType> yöntemi. .NET Framework 4 ve onun nokta sürümleri (.NET Framework 4.5, 4.5.1, 4.5.2 ve .NET Framework 4.6, 4.6.1, 4.6.2, 4.7 ve 4.7.1), dize v4.0.30319 döndürür.</li></ul>|
|`Scope`|Küçük|
|Version|4.6|
|Type|Çalışma zamanı|

