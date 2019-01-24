---
title: '&lt;custom&gt;'
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 5180b8866d8b0155a8683ab9cb6135c26f696929
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734993"
---
# <a name="ltcustomgt"></a>&lt;custom&gt;
Özel eş Çözücü hizmetinin ayarlarını belirtir.  
  
\<system.serviceModel>  
\<bağlamaları >  
\<netPeerBinding>  
\<bağlama >  
\<Çözümleyici >  
\<Özel >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`address`|Özel eş çözümleyici hizmetini barındıran eş düğümün uç nokta adresini belirten bir URI.|  
|`resolverType`|Özel eş Çözücü hizmetinin türünü belirten bir dize.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<Kimliği >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Bu öğe ile yapılandırılmış özel eş çözücüler kimliğini belirtir. Bu öğe türünde <xref:System.ServiceModel.Configuration.IdentityElement>.|  
|[\<üstbilgiler >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Özel eş çözümleyici tarafından işlenen SOAP iletileri için kullanılan adres üstbilgisi koleksiyonu.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<Çözümleyici >](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|Bir eş çözümlemek için kullanılan bir eş çözümleyici ağ Kimliğini ağ içinde katılan çeşitli düğümleri temsil eden bir eş düğüm adresleri kümesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu öğe, hizmet ve herhangi bir özel bağlayıcı ayarları barındıran eş uç nokta adresini de dahil olmak üzere bir özel eş Çözücü hizmetinin temel ayarlarını tanımlar. Bir özel Çözücü oluşturma hakkında daha fazla bilgi için bkz. [PeerChannel'a uygulamaya özel Çözücü ekleme](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [Eş Çözücüler](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- [Bir özel Çözücü PeerChannel'a uygulamaya ekleme](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
