---
title: bypasslist için <add> Öğesi (Ağ Ayarları)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 904c8e23f7a09a975a6f3b9322ed6bc4148d9ba4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674674"
---
# <a name="add-element-for-bypasslist-network-settings"></a>\<Ekle > bypasslist (ağ ayarları) için
Bir IP adresi veya DNS adı için proxy atlama listesi ekler.  
  
 \<Yapılandırma >  
\<system.net>  
\<defaultProxy >  
\<bypasslist>  
\<Ekle >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|**Öznitelik**|**Açıklama**|  
|-------------------|---------------------|  
|**Adresi**|Bir IP adresi veya DNS adını tanımlayan bir normal ifade.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|**Öğe**|**Açıklama**|  
|-----------------|---------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Bir proxy sunucu kullanmaması adresleri açıklayan normal bir ifade kümesi sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `add` IP adresleri veya DNS sunucu adları için proxy sunucusunu atla adreslerinin listesini açıklayan normal ifadeler öğe ekler.  
  
 Değerini `address` öznitelik, bir dizi IP adresi veya ana bilgisayar adları açıklayan bir normal ifade olmalıdır.  
  
 Bu öğe için normal bir ifade belirtirken dikkatli olmanız gerekir. Normal ifade "[a-z] +\\.contoso\\.com" eşleşme barındıran tüm contoso.com etki alanı, ancak bunu ayrıca contoso.com.cpandl.com etki alanındaki herhangi bir ana bilgisayara eşleşen. Contoso.com etki alanındaki bir konak eşleştirmek için bir yer işareti ("$") kullanın: "[a-z] +\\.contoso\\.com$".  
  
 Normal ifadeler hakkında daha fazla bilgi için bkz. [.NET framework normal ifadelerinde](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Yapılandırma Dosyaları  
 Bu öğe, uygulama yapılandırma dosyası veya makine yapılandırma dosyası (Machine.config) kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek iki adres atlama listesine ekler. İlk contoso.com etki alanındaki tüm sunucular için proxy atlar; İkinci proxy 192.168 tüm sunucularıyla başlar, IP adresi için atlar.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Ağ Ayarları Şeması](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
