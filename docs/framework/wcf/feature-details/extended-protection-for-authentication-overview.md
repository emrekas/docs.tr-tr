---
title: Kimlik Doğrulama için Genişletilmiş Koruma Genel Bakış
ms.date: 03/30/2017
ms.assetid: 3d2ceffe-a7bf-4bd9-a5a2-9406423bd7f8
ms.openlocfilehash: 5eb9e07bfd80e325a5223e6a7c6108134c4a3faa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647830"
---
# <a name="extended-protection-for-authentication-overview"></a>Kimlik Doğrulama için Genişletilmiş Koruma Genel Bakış
Kimlik doğrulama için genişletilmiş koruma, bir saldırganın istemci kimlik bilgileri yakalar ve bunları bir sunucuya yönlendirdiği ortadaki-de-adam (MITM) saldırılarına karşı korumaya yardımcı olur.  
  
 Üç katılımcılarıyla bir senaryo düşünün: bir istemci, sunucu ve saldırganın. Sunucu URL'si yok `https://server`, saldırgan URL sahipken `https://attacker`. Saldırgan, sunucunun değilmiş gibi saldırgan erişme içine istemci ipuçları. Saldırgan, ardından sunucusuna bir istek gönderir. Saldırgan, güvenli bir kaynağa erişmeye çalıştığında, sunucunun saldırgan bir WWW-Authenticate üstbilgisi ile yanıtlar. Saldırgan kimlik doğrulama bilgileri olmadığından, istemcide WWW-Authenticate üstbilgisi gönderir. İstemci yetkilendirme üst bilgisi bir saldırgana gönderir ve bir saldırgan, sunucuya üst bilgisi gönderir ve istemci kimlik bilgileri kullanılarak güvenli kaynaklara erişim alır.  
  
 Şu anda, bir istemci uygulaması kendisini sunucuya Kerberos, Özet veya HTTPS kullanarak NTLM kullanarak kimlik doğrulamasını gerçekleştirdiğinde aktarım düzeyi güvenlik (TLS) kanalı ilk kurulur ve kimlik doğrulaması kullanarak bu kanal gerçekleşir. Ancak, Güvenli Yuva Katmanı (SSL) tarafından oluşturulan oturum anahtarı ile kimlik doğrulaması sırasında oluşturulan oturum anahtarı arasındaki hiçbir bağlama yok. Bu nedenle, önceki senaryoda iletişimin (örneğin, bir HTTPS kanalı aracılığıyla), bir TLS üzerinden yer alıyorsa vardır oluşturulan iki SSL kanalı: bir istemci ve saldırganın ve başka bir saldırgan sunucusu arasında arasında. İstemci kimlik bilgileri istemciden sunucuya ilk saldırgan ile istemci arasında SSL kanalı üzerinden ve daha sonra saldırgan sunucusu arasındaki kanalı üzerinden gönderilir. İstemci kimlik bilgileri tarafından sunucuya ulaşmak sonra sunucu üzerinde bu kimlik bilgilerinin gönderilen kanal saldırgan ve istemci ile kaynaklandığını algılama olmadan kimlik bilgilerini doğrular.  
  
 TLS güvenli bir dış kanal ve istemci kimlik doğrulaması iç kanal kullanın ve bir kanal bağlama simgesi (CBT) sunucusuna geçirilecek çözümüdür. CBT TLS güvenli dış kanal bir özelliktir ve dış kanal üzerinden istemci kimlik doğrulaması iç kanal konuşmaya bağlamak için kullanılır.  
  
 Önceki senaryoda, istemci saldırgan TLS kanalının CBT sunucuya gönderilen yetkilendirme bilgilerle birleştirilir. CBT kullanan bir sunucu, istemci saldırgan kanala saldırgan sunuculu kanala eklenen CBT karşılık gelen istemci kimlik doğrulama bilgileri bulunan CBT karşılaştırır. Bir CBT belirli bir kanalın hedefe olduğundan istemci-saldırgan CBT saldırgan-server CBT eşleşmiyor. Bu sunucunun MITM saldırı algılama ve kimlik doğrulama isteği reddet sağlar.  
  
 İstemci tarafı herhangi bir yapılandırma ayarı gerektirmez. İstemci CBT sunucuya geçirmek için güncelleştirilmiş sonra bunu her zaman yapar. Sunucu aynı zamanda güncelleştirildiyse, CBT kullanın veya bunu yoksaymak için yapılandırılabilir. Bunu güncelleştirilmemiş, onu yoksayar.  
  
 Sunucunun aşağıdaki koruma düzeyleri sahip olabilir:  
  
-   Yok. Kanal bağlama doğrulama yapılmaz. Bu güncelleştirilmemiş tüm sunucuların davranıştır.  
  
-   Kısmi. Güncelleştirilen tüm istemcilerin, sunucuya kanal bağlama bilgileri sağlamanız gerekir. Güncelleştirilmemiş istemciler, bunu yapmak gerekmez. Bu uygulama uyumluluğu için sağlayan bir ara bir seçenektir.  
  
-   Tam. Tüm istemciler, kanal bağlama bilgileri sağlamanız gerekir. Sunucu, bunu yapmayın istemcilerinden kimlik doğrulama istekleri reddeder.  
  
 Win7 CBT/genişletilmiş koruma örnek daha fazla bilgi için bkz.  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Windows Server AppFabric için güvenlik modeli](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
