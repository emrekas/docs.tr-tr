---
ms.openlocfilehash: d75eff2d2a43ab4488577014ec43a9826b2b2924
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68237844"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a>WCF TransportDefaults Ssl3 Kaldır

|   |   |
|---|---|
|Ayrıntılar|Aktarım güvenliği ile NetTcp ve sertifika kimlik bilgisi türü kullanırken, SSL 3 artık güvenli bağlantı anlaşması için kullanılan bir varsayılan protokoldür. Çoğu durumda olması gerekir mevcut uygulamalara herhangi bir etkisi olarak TLS 1.0 her zaman protokol listesinde NetTcp için eklenmiştir. Var olan tüm istemciler bir bağlantı kullanarak en az TLS1.0.|
|Öneri|Ssl3 gerekiyorsa, aşağıdaki yapılandırma mekanizmalardan biri Ssl3 anlaşma protokolleri listesine eklemek için kullanın.<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>[&lt;sslStreamSecurity&gt; bölümünü &lt;customBinding&gt;] ~ / docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</li></ul>|
|Kapsam|Kenar|
|Sürüm|4.6.2|
|Tür|Çalışma zamanı|
|Etkilenen API’ler|<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
