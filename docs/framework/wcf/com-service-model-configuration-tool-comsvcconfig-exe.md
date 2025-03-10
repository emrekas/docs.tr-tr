---
title: COM+ Hizmet Modeli Yapılandırma Aracı (ComSvcConfig.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
ms.openlocfilehash: 89462d05b9da7fc63bda58955517bfa9f0c50ab9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964197"
---
# <a name="com-service-model-configuration-tool-comsvcconfigexe"></a>COM+ Hizmet Modeli Yapılandırma Aracı (ComSvcConfig.exe)
COM+ hizmet modeli yapılandırma komut satırı aracı (ComSvcConfig. exe), COM+ arabirimlerini Web Hizmetleri olarak kullanıma sunulacak şekilde yapılandırmanızı sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
> ComSvcConfig. exe ' yi kullanmak için yerel bilgisayarda bir yönetici olmanız gerekir.  
  
 Araç aşağıdaki konumda bulunabilir  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation \  
  
 ComSvcConfig. exe hakkında daha fazla bilgi için bkz [. nasıl yapılır: COM+ hizmet modeli yapılandırma aracını](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)kullanın.  
  
 Aşağıdaki tabloda ComSvcConfig. exe ile kullanılabilen modlar açıklanmaktadır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|`install`|Hizmet modeli tümleştirmesi için bir COM+ arabirimi yapılandırması kurar.<br /><br /> Kısa biçim `/i`.|  
|`uninstall`|Bir COM+ arabiriminin yapılandırmasını hizmet modeli tümleştirmesinden kaldırır.<br /><br /> Kısa biçim `/u`.|  
|`list`|Hizmet modeli tümleştirmesi için yapılandırılmış arabirimlerin bulunduğu COM+ uygulamaları ve bileşenleriyle ilgili bilgileri listeler.<br /><br /> Kısa biçim `/l`.|  
  
 Aşağıdaki tabloda ComSvcConfig. exe ile kullanılabilen bayraklar açıklanmaktadır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|`/application:`ApplicationId *ApplicationName* \< &#124;\>|Yapılandırılacak COM+ uygulamasını belirtir.<br /><br /> Kısa biçim `/a`.|  
|`/contract:`&#124; &#124; &#124; ClassID ProgID&#124; *, InterfaceID* InterfaceName \< \*    \*\>|Hizmet için sözleşme olarak yapılandırılacak COM+ bileşenini ve arabirimini belirtir.<br /><br /> Kısa biçim `/c`.<br /><br /> Bileşen ve arabirim adlarını belirttiğinizde\*joker karakteri () kullanılabilir olsa da, istemediğiniz arabirimleri kullanıma sunabileceğiniz için bunu kullanmanızı öneririz.|  
|`/hosting:`&#124; ComPlus \<idi  \>|COM+ barındırma modunun mi yoksa Web barındırma modunun mi kullanılacağını belirtir.<br /><br /> Kısa biçim `/h`.<br /><br /> COM+ barındırma modu ' nu kullanmak, COM+ uygulamasının açık etkinleştirilmesini gerektirir. Web barındırma modunun kullanılması, COM+ uygulamasının gerektiği şekilde otomatik olarak etkinleştirilmesini sağlar. COM+ uygulaması bir kitaplık uygulaması ise, Internet Information Services (IIS) işleminde çalışır. COM+ uygulaması bir sunucu uygulaması ise, Dllhost. exe işleminde çalışır.|  
|`/webSite:`*Web SiteName* değeri \<\>|Web barındırma modu kullanıldığında, barındırma için Web sitesini belirtir ( `/hosting` bayrağa bakın).<br /><br /> Kısa biçim `/w`.<br /><br /> Hiçbir Web sitesi belirtilmemişse, varsayılan Web sitesi kullanılır.|  
|`/webDirectory:`\< *WebDirectoryName*\>|Web barındırma kullanıldığında, barındırma için sanal dizini belirtir ( `/hosting` bayrağa bakın).<br /><br /> Kısa biçim `/d`.|  
|`/mex`|Hizmetten bir sözleşme tanımı almak isteyen istemcileri desteklemek için varsayılan hizmet yapılandırmasına bir meta veri değişimi (MEX) hizmet uç noktası ekler.<br /><br /> Kısa biçim `/x`.|  
|`/id`|Uygulama, bileşen ve arabirim bilgilerini kimlik olarak görüntüler.<br /><br /> Kısa biçim `/k`.|  
|`/nologo`|ComSvcConfig. exe ' nin logoyu görüntülemesini önler.<br /><br /> Kısa biçim `/n`.|  
|`/verbose`|Karşılaşılan hatalara ek olarak tüm uyarıları veya bilgilendirici metinleri çıkışlar.<br /><br /> Kısa biçim `/v`.|  
|`/help`|Kullanım iletisini görüntüler.<br /><br /> Kısa biçim `/?`.|  
|`/partial`|Belirtilen arabirim gösterilebilir bir veya daha fazla yöntem imzası içerdiğinde bir hizmet yapılandırması oluşturur. Hizmet başlatma sırasında, uyumlu yöntemler hizmet sözleşmesinde işlem olarak görünür ve uyumlu olmayan yöntemler, hizmet sözleşmesinde yok sayılır ve yok sayılır.<br /><br /> Bu bayrak eksikse, belirtilen arabirim bir veya daha fazla uyumsuz yöntem içerdiğinde araç bir hizmet yapılandırması oluşturmaz.|  
  
## <a name="examples"></a>Örnekler  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, `IFinances` `ItemOrders.IFinancial` bileşen arabirimini (onlinesbir com+ uygulamasından) com+ barındırma modu kullanılarak Web Hizmetleri olarak gösterilen arabirimler kümesine ekler. Karşılaşılan hatalara ek olarak tüm uyarılar çıktı olacaktır.  
  
### <a name="code"></a>Kod  
  
```  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, `IStockLevels` `ItemInventory.Warehouse` bileşen arabirimini (OnlineWarehouse com+ uygulamasından) Web barındırma modu kullanılarak Web Hizmetleri olarak gösterilen arabirimler kümesine ekler. Web hizmeti, IIS 'nin OnlineWarehouse sanal dizininde barındırılır.  
  
### <a name="code"></a>Kod  
  
```  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek `IFinances` `ItemOrders.Financial` bileşen arabirimini (onlinesbir com+ uygulamasından) Web Hizmetleri olarak kullanıma sunulan arabirimlerin kümesinden kaldırır.  
  
### <a name="code"></a>Kod  
  
```  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, yerel makinedeki Onlinescompactcom+ uygulaması için ilgili adres ve bağlama ayrıntılarının yanı sıra, şu anda sunulan COM+ barındırılan arabirimlerini listelemektedir.  
  
### <a name="code"></a>Kod  
  
```  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: COM+ hizmet modeli yapılandırma aracını kullanma](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
