---
title: <requestCaching> Öğesi (Ağ Ayarları)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: 2a3d0b182acad2351ed095934ca97c6194d344fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659128"
---
# <a name="requestcaching-element-network-settings"></a>\<requestCaching > öğesi (ağ ayarları)
Ağ istekleri için önbelleğe alma mekanizmasını denetler.  
  
 \<Yapılandırma >  
\<system.net>  
\<requestCaching >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`isPrivateCache`|Önbelleğin, farklı kullanıcıların bilgileri arasında yalıtım verip içermediğini belirtir. Varsayılan değer `true` şeklindedir. Bu değer, orta `false` katman uygulamalar için olmalıdır.|  
|`disableAllCaching`|Tüm Web yanıtları için önbelleğe almanın devre dışı bırakıldığını belirtir ve program aracılığıyla geçersiz kılınamaz.|  
|`defaultPolicyLevel`|<xref:System.Net.Cache.RequestCacheLevel> Numaralandırmadaki değerlerden biri. Varsayılan değer `BypassCache` şeklindedir.|  
|`unspecifiedMaximumAge`|İçeriğin süresi dolduğunda, varsayılan süreyi belirtir.|  
  
## <a name="policylevel-attribute"></a>policyLevel özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`Default`|Kaynak yeni ise, içerik uzunluğu doğru, süre sonu, değişiklik ve içerik uzunluğu öznitelikleri varsa önbelleğe alınmış kaynağı döndürür.|  
|`BypassCache`|Sunucudan kaynağı döndürür.|  
|`CacheOnly`|İçerik uzunluğu varsa ve giriş boyutuyla eşleşiyorsa, önbelleğe alınmış kaynağı döndürür.|  
|`CacheIfAvailable`|İçerik uzunluğu sağlanmışsa ve giriş boyutuyla eşleşiyorsa, önbelleğe alınmış kaynağı döndürür; Aksi takdirde, kaynak sunucudan indirilir ve çağırana döndürülür.|  
|`Revalidate`|Önbelleğe alınan kaynağın zaman damgası sunucudaki kaynağın zaman damgasıyla aynıysa, önbelleğe alınmış kaynağı döndürür; Aksi takdirde, kaynak sunucudan yüklenir, önbellekte depolanır ve çağırana döndürülür.|  
|`Reload`|Kaynağı sunucudan indirir, önbellekte depolar ve kaynak arayana döndürür.|  
|`NoCacheNoStore`|Önbelleğe alınmış bir kaynak varsa, silinir. Kaynak sunucudan indirilir ve çağırana döndürülür.|  
|`Revalidate`|Zaman damgası sunucudaki kaynağın zaman damgasıyla aynıysa, kaynağın önbelleğe alınmış kopyasını kullanarak bir isteği karşılar; Aksi takdirde, kaynak, çağırana sunulan sunucudan indirilir ve önbellekte depolanır.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[defaultHttpCachePolicy](defaulthttpcachepolicy-element-network-settings.md)|İsteğe bağlı öğe.<br /><br /> HTTP önbelleğe almanın etkin olup olmadığını ve varsayılan önbelleğe alma ilkesini açıklar.|  
|[\<defaultFtpCachePolicy > öğesi (ağ ayarları)](defaultftpcachepolicy-element-network-settings.md)|İsteğe bağlı öğe.<br /><br /> FTP önbelleğe almanın etkin olup olmadığını ve varsayılan önbelleğe alma ilkesini açıklar.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[system.net](system-net-element-network-settings.md)|.NET Framework ağa nasıl bağlanacağını belirten ayarları içerir.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, tüm önbelleğe almanın nasıl devre dışı bırakılacağını gösterir.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [Ağ Ayarları Şeması](index.md)
