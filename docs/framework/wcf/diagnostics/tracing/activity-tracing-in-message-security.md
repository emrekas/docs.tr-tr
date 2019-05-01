---
title: İleti Güvenliğinde Etkinlik İzleme
ms.date: 03/30/2017
ms.assetid: 68862534-3b2e-4270-b097-8121b12a2c97
ms.openlocfilehash: c3bd36598fd903dc016959149e563174624d084b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912658"
---
# <a name="activity-tracing-in-message-security"></a>İleti Güvenliğinde Etkinlik İzleme
Bu konuda, aşağıdaki üç aşamaya olur güvenlik işlenmek Etkinlik izleme açıklanmaktadır.  
  
- Anlaşma/SCT exchange. Bu, daha sonra (ikili veri değişimi üzerinden) taşıma veya ileti katman (üzerinden SOAP ileti alışverişlerinde) oluşabilir.  
  
- İleti şifreleme/şifre çözme, imza doğrulaması ve kimlik doğrulaması ile. Ortam etkinlik, genellikle "işlem Action." görüntülenir  
  
- Yetkilendirme ve doğrulama. Bu, yerel olarak veya ne zaman uç noktalar arasında iletişim kuran oluşabilir.  
  
## <a name="negotiationsct-exchange"></a>Anlaşma/SCT exchange  
 Anlaşma/SCT değişimi aşamasında, istemcide iki etkinlik türleri oluşturulur: "Güvenli oturum ayarlayın" ve "Güvenli oturumu kapat." "Güvenli Oturumu Kapat" Cancel iletisi izlemelerini içerse de "Güvenli oturum ayarlayın" k/RSTR/SCT ileti alışverişlerinde izlemelerini kapsar.  
  
 Sunucuda, her istek/yanıt lk/RSTR/SCT için kendi etkinliğinde görüntülenir. Varsa `propagateActivity` = `true` hem sunucu hem de istemci, sunucunun etkinliklerde aynı Kimliğe sahip ve "Kurulum güvenli hizmet izleme görüntüleyicisini görüntülendiğinde oturumdaki" birlikte görünür.  
  
 Bu etkinlik izleme modeli, kullanıcı adı/parola kimlik doğrulaması, sertifika kimlik doğrulaması ve NTLM kimlik doğrulaması için geçerli değil.  
  
 Etkinlikleri ve izlemeler anlaşma ve SCT exchange için aşağıdaki tabloda listelenmektedir.  
  
||Zaman zaman anlaşma/SCT exchange olur|Etkinlikler|izlemeleri|  
|-|-------------------------------------------------|----------------|------------|  
|Güvenli aktarım<br /><br /> (HTTPS, SSL)|Üzerinde ilk iletisi alındı.|İzlemeler ortam etkinliğinde gönderilir.|-Exchange izlemeleri<br />-Oluşturulan kanalının güvenliğini sağlayın<br />-Alınan gizlilikler paylaşın.|  
|Güvenli ileti katmanı<br /><br /> (WSHTTP)|Üzerinde ilk iletisi alındı.|İstemcide:<br /><br /> -"Kurulum güvenli oturum" dışında bu ilk iletiyi "işlem Action" her istek/yanıt RSTR/lk/SCT için.<br />-"Güvenli Oturumu Kapat" için "Kapat Proxy etkinliği." dışında iptal exchange Bu etkinlik, güvenli oturum kapatıldığında bağlı olarak bazı diğer ortam etkinliği dışında oluşabilir.<br /><br /> Sunucuda:<br /><br /> -Bir "İşlem Action" etkinlik her istek/yanıt SCT/lk/iptal için sunucu üzerinde. Varsa `propagateActivity` = `true`"Ayarlanmış yukarı güvenlik oturumu" k/RSTR/SCT etkinlikleri birleştirilir ve istemciden "Kapat" etkinliği ile iptal edilir.<br /><br /> "Ayarlanmış yukarı güvenli oturum" için iki aşaması vardır:<br /><br /> 1.  Kimlik doğrulama anlaşma. Bu istemci uygun kimlik bilgilerine zaten sahipse, isteğe bağlıdır. Bu aşama, ileti alışverişlerinde veya güvenli aktarım aracılığıyla yapılabilir. İkinci durumda, 1 veya 2 k/RSTR değişimleri oluşabilir. Bu değişimler için önceden tasarlanmış yeni istek/yanıt etkinlikler izlemeleri gönderilir.<br />2.  Bir lk/RSTR exchange burayı olur oturum kurma (SCT) güvenli hale getirin. Bu, daha önce açıklandığı gibi aynı ortam etkinlikleri sahiptir.|-Exchange izlemeleri<br />-Oluşturulan kanalının güvenliğini sağlayın<br />-Alınan gizlilikler paylaşın.|  
  
> [!NOTE]
>  Karma güvenlik modu, ikili alışverişlerine Anlaşma kimlik doğrulama olur, ancak ileti Exchange'de SCT olur. Saf aktarım modunda anlaşma hiçbir ek etkinlikler ile aktarma yalnızca içinde gerçekleşir.  
  
## <a name="message-encryption-and-decryption"></a>İleti şifreleme ve şifre çözme  
 Aşağıdaki tabloda, etkinlikleri ve izlemeler imzası kimlik doğrulaması yanı sıra ileti şifreleme/şifre çözme için listeler.  
  
||Güvenli aktarım<br /><br /> (HTTPS, SSL) ve güvenli ileti katman<br /><br /> (WSHTTP)|  
|-|---------------------------------------------------------------------------------|  
|Saati şifreleme/şifre çözme yanı sıra imzası kimlik doğrulaması'olmuyor iletisi|Alınan ileti üzerinde|  
|Etkinlikler|İzlemeler, istemci ve sunucu üzerinde ProcessAction etkinliğinde gönderilir.|  
|izlemeleri|-   sendSecurityHeader (sender):<br />-Oturum ileti<br />-İstek verileri şifreleme<br />-receiveSecurityHeader (alıcı):<br />-İmzasını<br />-Yanıt verilerin şifresini<br />-Kimlik doğrulaması|  
  
> [!NOTE]
>  Saf aktarım modunda, yalnızca içinde hiçbir ek etkinlikler ile Aktarım ileti şifreleme/şifre çözme gerçekleşir.  
  
## <a name="authorization-and-verification"></a>Yetkilendirme ve doğrulama  
 Aşağıdaki tabloda, yetkilendirme için izlemeler ve etkinlikleri listeler.  
  
||Yetkilendirme durumda zaman|Etkinlikler|izlemeleri|  
|-|-------------------------------------|----------------|------------|  
|Yerel (varsayılan)|İletinin sonra sunucuda şifresi çözülür|İzlemeler, sunucuda ProcessAction etkinliğinde gönderilir.|Yetkili kullanıcı.|  
|Remote|İletinin sonra sunucuda şifresi çözülür|İzlemeleri ProcessAction etkinlik tarafından çağrılan yeni bir etkinlik içinde gönderilir.|Yetkili kullanıcı.|
