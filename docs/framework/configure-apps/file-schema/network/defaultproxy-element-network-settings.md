---
title: <defaultProxy> Öğesi (ağ ayarları)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: ce08dadb0fb7b986c0573b1514f9ecbbe2961c3a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228353"
---
# <a name="defaultproxy-element-network-settings"></a>\<defaultProxy > öğesi (ağ ayarları)
Köprü Metni Aktarım Protokolü (HTTP) proxy sunucusunu yapılandırır.  
  
 \<Yapılandırma >  
\<system.net>  
\<defaultProxy >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|**Öğe**|**Açıklama**|  
|-----------------|---------------------|  
|`enabled`|Bir web proxy kullanılıp kullanılmayacağını belirtir. Varsayılan değer `true` şeklindedir.|  
|`useDefaultCredentials`|Bu ana bilgisayarın varsayılan kimlik bilgileri web proxy sunucusuna erişmek için kullanılıp kullanılmayacağını belirtir. Varsayılan değer `false` şeklindedir.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|**Öğe**|**Açıklama**|  
|-----------------|---------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Proxy kullanmayın adresleri açıklayan normal bir ifade kümesi sağlar.|  
|[modül](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|Yeni proxy modülü uygulamayı ekler.|  
|[proxy](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|Bir proxy sunucusu tanımlar.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|**Öğe**|**Açıklama**|  
|-----------------|---------------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|.NET Framework ağa nasıl bağlandığını belirten ayarları içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 DefaultProxy öğesi boş ise, Internet Explorer proxy ayarları kullanılacaktır. Bu davranış, .NET Framework'ün 1.1 sürümünden farklıdır.  
  
 Bir özel durum [Modülü](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) öğeyi belirten bir ortak olmayan tür, türün öğesinden türetme değil <xref:System.Net.IWebProxy> sınıfı, bu nesnenin varsayılan oluşturucu adresinden bir özel durum oluştu veya bir özel durum oluştu sırada Sistem tarafından belirlenen varsayılan ara sunucu alınıyor. <xref:System.Exception.InnerException%2A> Özel durum özelliği, hatanın kök nedeni hakkında daha fazla bilgi olması gerekir.  
  
## <a name="configuration-files"></a>Yapılandırma Dosyaları  
 Bu öğe, uygulama yapılandırma dosyası veya makine yapılandırma dosyası (Machine.config) kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, Internet Explorer proxy varsayılanlarından kullanır, proxy adresi belirtir ve yerel erişim ve contoso.com için proxy atlar.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Ağ Ayarları Şeması](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
