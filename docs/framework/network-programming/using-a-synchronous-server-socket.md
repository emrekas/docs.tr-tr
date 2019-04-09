---
title: Zaman Uyumlu Sunucu Yuvası Kullanma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
ms.openlocfilehash: 43e1d54d4e74b49fdf1a8997d1cc89492c9412bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117258"
---
# <a name="using-a-synchronous-server-socket"></a><span data-ttu-id="a8168-102">Zaman Uyumlu Sunucu Yuvası Kullanma</span><span class="sxs-lookup"><span data-stu-id="a8168-102">Using a Synchronous Server Socket</span></span>
<span data-ttu-id="a8168-103">Yuva bağlantısı isteği alınana kadar zaman uyumlu sunucu yuva uygulamanın yürütülmesini askıya alın.</span><span class="sxs-lookup"><span data-stu-id="a8168-103">Synchronous server sockets suspend the execution of the application until a connection request is received on the socket.</span></span> <span data-ttu-id="a8168-104">Zaman uyumlu sunucu yuva ağ kullanımı yoğun uygulamalar, işlemi için uygun değildir, ancak Basit Ağ uygulamaları için uygun olabilir.</span><span class="sxs-lookup"><span data-stu-id="a8168-104">Synchronous server sockets are not suitable for applications that make heavy use of the network in their operation, but they can be suitable for simple network applications.</span></span>  
  
 <span data-ttu-id="a8168-105">Sonra bir <xref:System.Net.Sockets.Socket> kullanarak bir uç noktası dinleyecek şekilde ayarlanır <xref:System.Net.Sockets.Socket.Bind%2A> ve <xref:System.Net.Sockets.Socket.Listen%2A> yöntemleri, gelen bağlantı isteklerini kullanarak kabul etmeye hazır <xref:System.Net.Sockets.Socket.Accept%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a8168-105">After a <xref:System.Net.Sockets.Socket> is set to listen on an endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> and <xref:System.Net.Sockets.Socket.Listen%2A> methods, it is ready to accept incoming connection requests using the <xref:System.Net.Sockets.Socket.Accept%2A> method.</span></span> <span data-ttu-id="a8168-106">Bir bağlantı isteği alınana kadar uygulamanın askıya olduğunda **kabul** yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="a8168-106">The application is suspended until a connection request is received when the **Accept** method is called.</span></span>  
  
 <span data-ttu-id="a8168-107">Bir bağlantı isteği alındığında **kabul** yeni bir **yuva** bağlanan istemcinin ile ilişkili olan örneği.</span><span class="sxs-lookup"><span data-stu-id="a8168-107">When a connection request is received, **Accept** returns a new **Socket** instance that is associated with the connecting client.</span></span> <span data-ttu-id="a8168-108">Aşağıdaki örnek istemciden gelen verileri okur, konsolda görüntüler ve istemcisine verileri görüntülemektedir.</span><span class="sxs-lookup"><span data-stu-id="a8168-108">The following example reads data from the client, displays it on the console, and echoes the data back to the client.</span></span> <span data-ttu-id="a8168-109">**Yuva** herhangi bir Mesajlaşma protokolü, bu nedenle belirtmiyor dize "\<EOF >" ileti verileri sonunu işaretler.</span><span class="sxs-lookup"><span data-stu-id="a8168-109">The **Socket** does not specify any messaging protocol, so the string "\<EOF>" marks the end of the message data.</span></span> <span data-ttu-id="a8168-110">Olduğunu varsayar bir **yuva** adlı `listener` başlatılır ve bir uç noktasına bağlı.</span><span class="sxs-lookup"><span data-stu-id="a8168-110">It assumes that a **Socket** named `listener` has been initialized and bound to an endpoint.</span></span>  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8168-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a8168-111">See also</span></span>

- [<span data-ttu-id="a8168-112">Zaman Uyumsuz Sunucu Yuvası Kullanma</span><span class="sxs-lookup"><span data-stu-id="a8168-112">Using an Asynchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="a8168-113">Zaman Uyumlu Sunucu Yuvası Örneği</span><span class="sxs-lookup"><span data-stu-id="a8168-113">Synchronous Server Socket Example</span></span>](../../../docs/framework/network-programming/synchronous-server-socket-example.md)
- [<span data-ttu-id="a8168-114">Yuvalarla Dinleme</span><span class="sxs-lookup"><span data-stu-id="a8168-114">Listening with Sockets</span></span>](../../../docs/framework/network-programming/listening-with-sockets.md)
