---
title: '&lt;msmqIntegrationBinding&gt; &lt;güvenliği&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: db263148a5a0993b546ffdd565ae7cf2edef580c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493787"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a>&lt;msmqIntegrationBinding&gt; &lt;güvenliği&gt;
Message Queuing (MSMQ) tümleştirme kanal taşıma güvenlik ayarlarını tanımlar.  
  
 \<system.ServiceModel>  
\<bağlamaları >  
msmqIntegrationBinding  
\<bağlama >  
\<Güvenlik >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|mod|Güvenlik türü bu denetimleri bütünlüğü, gizlilik ve kimlik doğrulaması ile Message Queuing tümleştirme kanalı belirtir. Geçerli değerler şunlardır:<br /><br /> -Yok: Bu güvenlik devre dışı bırakır.<br />-Taşıma: Koruma ve kimlik doğrulaması taşıma tarafından sunulmaktadır. Bu ileti güvenliği iki sıra yöneticileri arasında geçerlidir. Kuyruk Yöneticisi ve uygulama arasında sunulan güvenlik yoktur. Msmq uygulamalara güvenlik modu bu tür işlevsel olarak eşdeğerdir.<br /><br /> Varsayılan değer `Transport` şeklindedir. Bu öznitelik türünde <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<taşıma >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|Message Queuing tümleştirme taşıma güvenlik ayarlarını tanımlar. Bu öğe türünde <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<bağlama >](../../../../../docs/framework/misc/binding.md)|Bağlama öğesi [ \<MsmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).|  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [WCF'de Kuyruklar](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [Hizmet ve İstemcileri Güvenli Hale Getirme](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Bağlamalar](../../../../../docs/framework/wcf/bindings.md)
- [Sistem Tarafından Sağlanan Bağlamaları Yapılandırma](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<bağlama >](../../../../../docs/framework/misc/binding.md)
- [\<MsmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
