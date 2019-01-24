---
title: Meta Veri Biçimleri
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: 44ea084287561e13a8db217e49212ee878a26bb7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513535"
---
# <a name="metadata-formats"></a>Meta Veri Biçimleri
Windows Communication Foundation (WCF) aşağıdaki tabloda meta veri biçimleri destekler.  
  
## <a name="metadata-specifications-and-usage"></a>Meta veri özellikleri ve kullanım  
  
|Protokol|Belirtimi ve kullanım|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Hizmetleri Açıklama Dili (WSDL) 1.1](https://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF Web Hizmetleri Açıklama Dili (WSDL) hizmetleri tanımlamak için kullanır.|  
|XML Şeması|[XML şema bölümü 2: Veri türleri İkinci Sürüm](https://go.microsoft.com/fwlink/?LinkId=94861) ve [XML Şeması Kısım 1: Yapıları ikinci sürüm](https://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> WCF iletilerde kullanılan veri türlerini tanımlamak için XML şeması kullanır.|  
|WS İlkesi|[Web Hizmetleri ilkesi 1.2 - Framework (WS-Policy)](https://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Web Hizmetleri ilkesi 1.5 - Framework](https://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> WCF hizmet gereksinimlerini ve özelliklerini tanımlamak için etki alanına özgü onaylama ile WS-Policy 1.2 veya 1,5 belirtimleri kullanır.|  
|WS ilke ekler|[Web Hizmetleri ilkesi 1.2 - ek (WS-PolicyAttachment)](https://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> WCF WSDL çeşitli kapsamlarda ilke ifadeleri eklemek için WS-Policy ekleri uygular.|  
|WS-Metadata Exchange|[Web Hizmetleri meta veri değişimi (WS-MetadataExchange) sürüm 1.1](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF XML Şeması, WSDL ve WS-Policy almak için WS-MetadataExchange uygular.|  
|WS bağlama için WSDL adresleme|[Web Hizmetleri adresleme 1.0 - WSDL bağlama](https://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> WS-Addressing bağlama WSDL adresleme bilgileri eklemek WSDL için WCF uygular.|  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Sistem Tarafından Sağlanan Birlikte Kullanılabilirlik Bağlamaları ile Desteklenen Web Hizmeti Protokolleri](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL ve İlke](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
