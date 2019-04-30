---
title: <security> / <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: acb4d04663d841a9b494153caa180855959c145e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670514"
---
# <a name="security-of-netmsmqbinding"></a>\<Güvenlik >, \<netMsmqBinding >
MSMQ bağlama için güvenlik ayarlarını tanımlar. Bu aktarım veya SOAP Güvenliği etkinleştirilmiş ve bu durumda, hangi kimlik doğrulama modu ve koruma düzeyleri kullanımda olup olmadığını belirtir.  
  
 \<system.ServiceModel>  
\<bağlamaları >  
\<netMsmqBinding>  
\<bağlama >  
\<Güvenlik >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|mod|Bütünlüğü, gizlilik ve kimlik doğrulama denetimleri güvenlik türünü belirtir. Geçerli değerler şunlardır:<br /><br /> -Yok: Bu güvenlik devre dışı bırakır.<br />-Taşıma: Koruma ve kimlik doğrulaması taşıma tarafından sunulmaktadır. Bu ileti güvenliği iki sıra yöneticileri arasında geçerlidir. Kuyruk Yöneticisi ve uygulama arasında sunulan güvenlik yoktur. Msmq uygulamalara güvenlik modu bu tür işlevsel olarak eşdeğerdir.<br />-İleti: Uçtan uca uygulama güvenliği belirtir. Aktarım katmanında sunulan güvenlik yoktur. Bu, standart diğer bağlamalar tarafından sunulan güvenlik benzer.<br />-Hem: Hem aktarım hem de SOAP ileti katmanı güvenlik sunar. Aynı kimlik bilgisini iki düzeyde gereklidir.<br /><br /> Aktarım varsayılan değerdir. Bu öznitelik türünde <xref:System.ServiceModel.NetMsmqSecurityMode>.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<İleti >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|SOAP ileti güvenlik ayarlarını tanımlar. Bu öğe türünde <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.|  
|[\<taşıma >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|MSMQ taşıma güvenlik ayarlarını tanımlar. Bu öğe türünde <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|bağlama|Bağlama öğesi [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [Hizmet ve İstemcileri Güvenli Hale Getirme](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Bağlamalar](../../../../../docs/framework/wcf/bindings.md)
- [Sistem Tarafından Sağlanan Bağlamaları Yapılandırma](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<bağlama >](../../../../../docs/framework/misc/binding.md)
- [WCF'de Kuyruklar](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
