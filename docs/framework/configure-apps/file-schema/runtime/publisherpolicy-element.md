---
title: <publisherPolicy> Öğesi
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc206e584440778858e61fc0bab51fc8ffa2009a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252376"
---
# <a name="publisherpolicy-element"></a>\<publisherPolicy > öğesi
Çalışma zamanının yayımcı ilkesi uygulanıp uygulanmadığını belirtir.  
  
[ **\<Yapılandırma >** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<çalışma zamanı >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<publisherPolicy >**  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`apply`|Yayımcı ilkesinin uygulanıp uygulanmayacağını belirtir.|  
  
## <a name="apply-attribute"></a>Özniteliği Uygula  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`yes`|Yayımcı ilkesini uygular. Varsayılan ayar budur.|  
|`no`|Yayımcı ilkesi uygulamaz.|  
  
### <a name="child-elements"></a>Alt Öğeler  

Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`assemblyBinding`|Derleme sürümü yeniden yönlendirmesi ve derlemelerin konumları hakkında bilgi içerir.|  
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|  
|`dependentAssembly`|Her bir derleme için bağlama ilkesi ve derleme konumunu saklar. Her derleme `<dependentAssembly>` için bir öğe kullanın.|  
|`runtime`|Derleme bağlama ve atık toplama hakkında bilgi içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir bileşen satıcısı bir derlemenin yeni bir sürümünü yayımlarsa, satıcı bir yayımcı ilkesi içerebilir, bu nedenle eski sürümü kullanan uygulamalar artık yeni sürümü kullanır. Belirli bir derleme için yayımcı ilkesinin uygulanıp uygulanmayacağını belirtmek için,  **\<publisherPolicy >** öğesini  **\<dependentAssembly >** öğesine koyun.  
  
 **Apply** özniteliği için varsayılan ayar **Evet**' tir. **Apply** özniteliğini **Hayır** olarak ayarlamak, bir derleme için önceki tüm **Evet** ayarlarını geçersiz kılar.  
  
 Uygulamanın, uygulama yapılandırma dosyasında [ \<publisherPolicy apply = "No"/>](publisherpolicy-element.md) öğesini kullanarak yayımcı ilkesini açıkça yoksayması için izin gerekir. ' De <xref:System.Security.Permissions.SecurityPermissionFlag> bayrak ayarlanarak izin verilir. <xref:System.Security.Permissions.SecurityPermission> Daha fazla bilgi için bkz. [derleme bağlama yeniden yönlendirme güvenlik izni](../../assembly-binding-redirection-security-permission.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, derleme `myAssembly`için yayımcı ilkesini devre dışı bırakır.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Çalışma Zamanı Ayarları Şeması](index.md)
- [Yapılandırma Dosyası Şeması](../index.md)
- [Çalışma Zamanının Bütünleştirilmiş Kodların Konumunu Bulması](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Bütünleştirilmiş Kod Sürümlerini Yönlendirme](../../redirect-assembly-versions.md)
