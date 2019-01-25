---
title: Yuvalarla dinleme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- sockets, listening with sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- protocols, sockets
- listening with sockets
- Internet, sockets
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
ms.openlocfilehash: 763d1106a289e4aa6530eb07971d6ffb7e6095b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527854"
---
# <a name="listening-with-sockets"></a>Yuvalarla dinleme
Dinleyici veya server yuva ağ üzerindeki bir bağlantı noktasını açın ve bu bağlantı noktasına bağlanmak bir istemci için bekleyin. Diğer ağ adresi ailelerini ve protokolleri mevcut olmasına karşın, bu örnek bir TCP/IP ağı için uzak bir hizmetin nasıl oluşturulacağını gösterir.  
  
 TCP/IP'yi hizmetinin benzersiz adresini, IP adresi ana bilgisayar hizmeti için bir uç nokta oluşturmak için hizmet bağlantı noktası numarasını birleştirerek tanımlanır. <xref:System.Net.Dns> Sınıfı yerel ağ cihaz tarafından desteklenen ağ adresleri hakkında bilgi döndüren yöntemler sağlar. Yerel ağ cihaz birden fazla ağ adresi sahip olduğunda veya yerel sistemin birden fazla ağ aygıtı destekliyorsa **Dns** sınıfı, tüm ağ adresleri hakkında bilgileri döndürür ve uygulama uygun seçmeniz gerekir hizmet için adresi. Internet Atanmış Numaralar Yetkilisi (IANA) ortak Hizmetleri için bağlantı noktası numaralarını tanımlar; Daha fazla bilgi için [hizmet adını ve Aktarım Protokolü bağlantı noktası numarasını kayıt defteri](https://www.iana.org/assignments/port-numbers). Diğer hizmetler için 1024 65,535 aralığında bağlantı noktası numaralarını kayıtlı.  
  
 Aşağıdaki örnek, oluşturur bir <xref:System.Net.IPEndPoint> tarafından döndürülen ilk IP adresini birleştirerek bir sunucu için **Dns** ana bilgisayar bağlantı noktası numarası için kayıtlı bir bağlantı noktası numaralarını aralıktan seçildi.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 Yerel uç nokta belirlendikten sonra <xref:System.Net.Sockets.Socket> Bu uç noktayı kullanarak ile ilişkilendirilmelidir <xref:System.Net.Sockets.Socket.Bind%2A> yöntemi ve kullanarak uç noktası dinleyecek şekilde <xref:System.Net.Sockets.Socket.Listen%2A> yöntemi. **Bağlama** bir özel durum oluşturur belirli adres ve bağlantı noktası zaten kullanılıyor. Aşağıdaki örnek, ilişkilendirme gösterir. bir **yuva** ile bir **IPEndPoint**.  
  
```vb  
Dim listener As New Socket(ipAddress.AddressFamily, _  
    SocketType.Stream, ProtocolType.Tcp) 
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
Socket listener = new Socket(ipAddress.AddressFamily,
    SocketType.Stream, ProtocolType.Tcp);
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 **Dinleme** yöntemi kaç bekleyen bağlantılar belirten tek bir parametre alır **yuva** sunucu meşgul hatası bağlanan istemciye döndürülmeden önce izin verilir. Bu durumda, bir sunucu meşgul yanıtı istemci sayıya 101 döndürülmeden önce en fazla 100 istemci bağlantı kuyruğuna yerleştirilir.  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Zaman Uyumlu Sunucu Yuvası Kullanma](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)
- [Zaman Uyumsuz Sunucu Yuvası Kullanma](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)
- [İstemci Yuvaları Kullanma](../../../docs/framework/network-programming/using-client-sockets.md)
- [Nasıl yapılır: Yuva oluşturun](../../../docs/framework/network-programming/how-to-create-a-socket.md)
- [Yuvalar](../../../docs/framework/network-programming/sockets.md)
