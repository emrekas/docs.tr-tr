---
title: <runtime> için <assemblyBinding> Öğesi
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 515261fe39676292ce50858f71b7da92287945d1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252807"
---
# <a name="assemblybinding-element-for-runtime"></a>\<çalışma zamanı için \<assemblyBinding > öğesi >
Derleme sürümü yeniden yönlendirmesi ve derlemelerin konumları hakkında bilgi içerir.  
  
[ **\<Yapılandırma >** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<çalışma zamanı >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<assemblyBinding >**  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**özniteliði**|Gerekli öznitelik.<br /><br /> Derleme bağlaması için gereken XML ad alanını belirtir. Değer olarak "urn: schemas-microsoft-com: asm. v1" dizesini kullanın.|  
|**appliesTo**|.NET Framework derleme yeniden yönlendirmenin uygulandığı çalışma zamanı sürümünü belirtir. Bu isteğe bağlı öznitelik, hangi sürümün uygulanacağını göstermek için .NET Framework bir sürüm numarası kullanır. Hiçbir **AppliesTo** özniteliği belirtilmemişse,  **\<assemblyBinding >** öğesi .NET Framework tüm sürümleri için geçerlidir. **AppliesTo** özniteliği .NET Framework sürüm 1,1 ' de tanıtılmıştı; .NET Framework 1,0 sürümü tarafından yok sayılır. Bu, bir **AppliesTo** özniteliği belirtilmiş olsa bile, .NET Framework sürüm 1,0 kullanılırken tüm  **\<assemblyBinding >** öğelerinin uygulandığı anlamına gelir.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<dependentAssembly >](dependentassembly-element.md)|Derleme için bağlama ilkesini ve derleme konumunu kapsüller. Her derleme için bir  **\<dependentAssembly >** etiketi kullanın.|  
|[\<yoklama >](probing-element.md)|Derlemeler yüklenirken ortak dil çalışma zamanı aramalarının alt dizinlerini belirtir.|  
|[\<publisherPolicy >](publisherpolicy-element.md)|Çalışma zamanının yayımcı ilkesi uygulanıp uygulanmadığını belirtir.|  
|[\<qualifyAssembly >](qualifyassembly-element.md)|Kısmi bir ad kullanıldığında dinamik olarak yüklenmesi gereken derlemenin tam adını belirtir.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|  
|`runtime`|Derleme bağlama ve atık toplama hakkında bilgi içerir.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir derleme sürümünün diğerine nasıl yeniden yönlendirileceğini ve bir kod temeli nasıl sağlayabileceğinizi gösterir.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Aşağıdaki örnek, bir .NET Framework derlemesinin bağlamasını yeniden yönlendirmek için **AppliesTo** özniteliğini nasıl kullanacağınızı gösterir.  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Çalışma Zamanı Ayarları Şeması](index.md)
- [Yapılandırma Dosyası Şeması](../index.md)
- [Bütünleştirilmiş Kod Sürümlerini Yönlendirme](../../redirect-assembly-versions.md)
