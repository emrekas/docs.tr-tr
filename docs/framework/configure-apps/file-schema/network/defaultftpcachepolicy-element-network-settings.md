---
title: <defaultFtpCachePolicy> Öğesi (Ağ Ayarları)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 7ff44f0251936d51b4e396c37c53322efa110227
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659416"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a>\<defaultFtpCachePolicy > öğesi (ağ ayarları)
FTP önbelleğe almanın etkin olup olmadığını ve varsayılan önbelleğe alma ilkesini açıklar.  
  
 \<Yapılandırma >  
\<system.net>  
\<requestCaching >  
\<defaultFtpCachePolicy >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`policyLevel`|FTP önbelleğe alma ilkesini belirtir. Varsayılan değer `Default` şeklindedir.|  
  
## <a name="policylevel-attribute"></a>policyLevel özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`Default`|Kaynak yeni ise, içerik uzunluğu doğru, süre sonu, değişiklik ve içerik uzunluğu öznitelikleri varsa önbelleğe alınmış kaynağı döndürür.|  
|`BypassCache`|Sunucudan kaynağı döndürür.|  
|`CacheOnly`|İçerik uzunluğu varsa ve giriş boyutuyla eşleşiyorsa, önbelleğe alınmış kaynağı döndürür.|  
|`CacheIfAvailable`|İçerik uzunluğu sağlanmışsa ve giriş boyutuyla eşleşiyorsa, önbelleğe alınmış kaynağı döndürür; Aksi takdirde, kaynak sunucudan indirilir ve çağırana döndürülür.|  
|`Revalidate`|Önbelleğe alınan kaynağın zaman damgası sunucudaki kaynağın zaman damgasıyla aynıysa, önbelleğe alınmış kaynağı döndürür; Aksi takdirde, kaynak sunucudan indirilir, önbellekte depolanır ve çağırana döndürülür.|  
|`Reload`|Kaynağı sunucudan indirir, önbellekte depolar ve kaynak arayana döndürür.|  
|`NoCacheNoStore`|Önbelleğe alınmış bir kaynak varsa, silinir. Kaynak sunucudan indirilir ve çağırana döndürülür.|  
|`Revalidate`|Zaman damgası sunucudaki kaynağın zaman damgasıyla aynıysa, kaynağın önbelleğe alınmış kopyasını kullanarak bir isteği karşılar; Aksi takdirde, kaynak, çağırana sunulan ve önbellekte depolanan sunucudan indirilir.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[requestCaching](requestcaching-element-network-settings.md)|Ağ istekleri için önbelleğe alma mekanizmasını denetler.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, ' nin `NoCacheNoStore`bir FTP önbelleğe alma ilkesinin nasıl ekleneceğini gösterir.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Ağ Ayarları Şeması](index.md)
