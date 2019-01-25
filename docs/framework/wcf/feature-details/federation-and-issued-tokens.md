---
title: Federasyon ve Verilen Belirteçler
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: 513d68f49e4182979b492fa67e65860aee96e09a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699421"
---
# <a name="federation-and-issued-tokens"></a>Federasyon ve Verilen Belirteçler
Windows Communication Foundation (WCF) ile WS-Federation ve WS-Trust belirtimleri uygulama hizmetleri ile güvenli bir şekilde iletişim kuran istemcileri oluşturabilirsiniz. Belirtimleri, farklı güven bölgelerinde etkinleştirmek, kimlik doğrulama ve yetkilendirme mekanizmaları sağlamak için XML SOAP ve Web Hizmetleri Açıklama Dili (WSDL) kullanın.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Federasyon](../../../../docs/framework/wcf/feature-details/federation.md)  
 Federasyon için genel bir bakış sağlar.  
  
 [Federasyon ve Güven](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 Ne zaman oluşturma hizmetleri veya istemcilerin Federasyon dikkat etmeniz tasarım konuları listeler.  
  
 [Nasıl yapılır: Federe istemci oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 WCF ile federe istemci oluşturma hakkındaki temel bilgileri açıklar.  
  
 [Nasıl yapılır: Federe bir hizmette kimlik bilgilerini yapılandırma](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 Bir Federasyon Hizmeti oluşturma adımlarını açıklar.  
  
 [Nasıl yapılır: WSFederationHttpBinding oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 İstemcileri yapılandırma açıklar ve hizmetleri kullanan `WSFederationHttpBinding`.  
  
 [Nasıl yapılır: Bir güvenlik belirteci hizmeti oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 Güvenlik belirteci hizmeti oluşturma adımlarını açıklar.  
  
 [Güvenlik Onaylama İşlemi İşaretleme Dili (SAML) Belirteçleri ve Talepleri](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 Genişletilebilir olan güvenlik onaylama işaretleme dili (SAML) belirteçleri ve zengin oluşturmanızı talep türleri etkinleştirme açıklanmaktadır.  
  
 [Nasıl yapılır: Yerel yayımlayan yapılandırma](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 Yerel bir veren güvenlik belirteçlerinin nasıl oluşturulacağını açıklar.  
  
 [Nasıl yapılır: WSFederationHttpBinding güvenli oturumlarını devre dışı bırak](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Güvenli oturumlar devre dışı bırakmanız açıklar bir `WSFederationHttpBinding`. Her istemci için bir oturum gerektiren bir Web grubu oluştururken güvenli oturumlarını devre dışı bırakılması gereklidir.  
  
## <a name="reference"></a>Başvuru  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Yetkilendirme](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)
- [Özel Belirteçler](../../../../docs/framework/wcf/extending/custom-tokens.md)
- [Windows Server AppFabric için güvenlik modeli](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
