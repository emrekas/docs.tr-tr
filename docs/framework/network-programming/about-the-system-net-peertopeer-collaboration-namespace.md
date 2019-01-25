---
title: System.Net.PeerToPeer.Collaboration Namespace hakkında
ms.date: 03/30/2017
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
ms.openlocfilehash: 5bb96e11cf51e7e5b37d895310fa9a113899f34c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570871"
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a>System.Net.PeerToPeer.Collaboration Namespace hakkında
<xref:System.Net.PeerToPeer.Collaboration> Ad alanı, sınıflar ve eşler arası işbirliği altyapısı kullanılarak eş işbirliği etkinlikleri uygulamak için kullanılan API'ler sağlar.  
  
## <a name="classes"></a>Sınıflar  
 Eşler arası işbirliği etkinlik uygulamasında kullanılan ana sınıfları şunlardır:  
  
-   <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, Eş kişileri depolamak için kullanılabilir.  
  
-   <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> , Oyun, sohbet istemcisi veya konferans çözüm gibi işbirliği yapmak üzere.  
  
-   Bir etkinlik işbirliği eşler.  Bu eşlerden olarak gösterilebilir <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>, veya <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> nesneleri.  
  
-   Statik <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> hangi uygulamaların kullanılabilir belirtir ve hangi eşlerin katılan bunları kendi sınıf.  
  
 <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> Yöntemleri bir işbirliği oturumu genel eşlere davet etmek için kullanılır.  Çağıran bir eş için başka bir eş uygulama, nesne veya durum bilgilerini sinyal güncelleştirmeleri işbirliği oturumla ilişkili olaylar için abone olabilirsiniz. Varlık sınıfları belirtin olup olmadığını bir <xref:System.Net.PeerToPeer.Collaboration.Peer> işbirliği için kullanılabilir ve <xref:System.Net.PeerToPeer.Collaboration.PeerScope> sınıfı ne kadar katılım eşe yönelik izin verildiğini belirtmek için kullanılır: <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (Genel), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>, (alt ağ) veya <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.  
  
 Bir işbirliği oturumu dört adımdan oluşur:  
  
-   Bulma. Bulmak veya uygulamaları, eşlerdeki ve durum bilgilerini yayımlayabilirsiniz.  Örneğin, aynı oyunlar yüklü olan diğer kişiler yerel alt ağdaki bulun.  
  
-   Davet. Gönder ve uzak peer(s) başlatmak veya katılmak için güvenli davetlerini kabul <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> oturumları.  
  
-   Kişi yönetimi. Bulunan eşleri için kişi olarak ekleyin bir <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.  
  
-   İletişim. İletişimi kurulduğunda kullanın <xref:System.Net> API'leri <xref:System.Net.PeerToPeer> API ya da çok taraflı iletişim için Windows Communication Foundation eş kanalı sınıfları.  
  
 Örneğin, konak eş bir işbirliği oturumu başlatır ve yararlanan <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> konak eş için Kişi Yöneticisi uzak bir eş ve yerel eşlerine birini eklemek için yöntemi.  Üç kullanıcı daha sonra kendi özel işbirliği oturumunda katılacak.  
  
 Tipik P2P uygulamalar: konferans aramaları için işbirliğine dayalı not alma ya da Beyaz Tahta kullanımı, sunucusuz bir sohbet uygulamalar, etkileşimli tanıtım ve çevrimiçi oyun oturumları.  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Net.PeerToPeer.Collaboration>
