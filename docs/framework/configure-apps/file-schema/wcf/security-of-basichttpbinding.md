---
title: '&lt;basicHttpBinding&gt; &lt;güvenliği&gt;'
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 9e6a0e864dcb83a529a5ac457e2fcffe0435376f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701176"
---
# <a name="ltsecuritygt-of-ltbasichttpbindinggt"></a>&lt;basicHttpBinding&gt; &lt;güvenliği&gt;
Güvenlik yeteneklerini tanımlar [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
 \<system.ServiceModel>  
\<bağlamaları >  
\<basicHttpBinding >  
\<bağlama >  
\<Güvenlik >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|mod|İsteğe bağlı. Kullanılan güvenlik türünü belirtir. Varsayılan, `None` değeridir. Bu öznitelik türünde <xref:System.ServiceModel.BasicHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>mod özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|Hiçbiri|-Sıradaki iletiler, aktarım sırasında sağlanmaz.|  
|Taşıma|HTTPS aktarımı kullanarak güvenliği sağlanır. SOAP iletilerini HTTPS kullanılarak güvenli hale getirilir. Hizmet, hizmetin X.509 sertifikası kullanarak istemci kimlik doğrulaması yapılır. İstemci tarafından sağlanan ClientCredentialType kullanarak kimlik doğrulaması yapılır. Bkz: [ \<aktarım >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).|  
|İleti|SOAP ileti güveliği kullanarak güvenliği sağlanır. Varsayılan olarak, gövde imzalı ve şifrelenir. Bu bağlama için sistem sunucu sertifikası istemciyi bant dışından sağlanmasını gerektirir. Yalnızca geçerli `ClientCredentialType` Bu bağlama için `Certificate`.|  
|TransportWithMessageCredential|Bütünlüğü, gizliliği ve sunucu kimlik doğrulaması ile Aktarım güvenliği sağlanır. İstemci kimlik doğrulaması yoluyla SOAP ileti güvenliği sağlanır. Bu mod, kullanıcının kullanıcı adı/parola kullanarak kimlik doğrulaması ve ileti aktarım güvenliğini sağlamak için var olan bir HTTP dağıtım olduğunda geçerlidir.|  
|TransportCredentialOnly|Bu mod, ileti bütünlüğü ve gizliliği sağlamaz. Bu, http tabanlı istemci kimlik doğrulaması sağlar. Bu mod, dikkatli kullanılmalıdır. Burada aktarım güvenliği (IPSec gibi) diğer yollarla sağlanmaktadır ve yalnızca istemci kimlik doğrulaması WCF altyapısı tarafından sağlanan ortamlarda kullanılmalıdır.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<taşıma >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|Temel HTTP hizmeti için taşıma güvenlik ayarlarını tanımlar. Bu öğe için karşılık gelen <xref:System.ServiceModel.HttpTransportSecurity>.|  
|[\<İleti >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|Temel HTTP hizmeti için ileti güvenlik ayarlarını tanımlar. Bu öğe için karşılık gelen <xref:System.ServiceModel.BasicHttpMessageSecurity>.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|bağlama|Bağlama öğesi [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, SOAP ileti güvenli olmadığından ve istemci kimliği doğrulanmamış. Bu öğe için ek güvenlik ayarları yapılandırmanızı sağlar `basicHttpBinding` öğesi.  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [Hizmet ve İstemcileri Güvenli Hale Getirme](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Kimlik Bilgisi Türü Seçme](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [Bağlamalar](../../../../../docs/framework/wcf/bindings.md)
- [Sistem Tarafından Sağlanan Bağlamaları Yapılandırma](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<bağlama >](../../../../../docs/framework/misc/binding.md)
