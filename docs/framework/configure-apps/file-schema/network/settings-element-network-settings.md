---
title: <settings> Öğesi (ağ ayarları)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: a1733803d1f5a5bf64aeb69d0360cef3de3b3a69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096933"
---
# <a name="settings-element-network-settings"></a>\<Ayarlar > öğesi (ağ ayarları)
Temel ağ seçeneklerini yapılandırır <xref:System.Net?displayProperty=nameWithType> ad alanı.  
  
 \<Yapılandırma >  
\<system.net>  
\<Ayarlar >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[HttpListener](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|Tarafından kullanılan parametreler özelleştirir <xref:System.Net.HttpListener> sınıfı.|  
|[httpWebRequest](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|Web isteği parametreleri özelleştirir.|  
|[IPv6](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|Internet Protokolü sürüm 6 (IPv6) sağlayan destekler.|  
|[\<performanceCounter > öğesi (ağ ayarları)](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|Ağ performans sayaçları sağlar.|  
|[servicePointManager](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|Ağ kaynaklarına bağlantılarını yapılandırır.|  
|[yuva](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|Yuva işlemleri tamamlama bağlantı noktalarını kullanıp kullanmadığını belirtir.|  
|[\<webProxyScript > öğesi (ağ ayarları)](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|Web proxy'leri bulmak için kullanılan komut dosyası özelliklerini yapılandırır.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|.NET Framework ağa nasıl bağlandığını belirten ayarları içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="configuration-files"></a>Yapılandırma Dosyaları  
 Bu öğe, uygulama yapılandırma dosyası veya makine yapılandırma dosyası (Machine.config) kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Net?displayProperty=nameWithType>
- [Ağ Ayarları Şeması](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
