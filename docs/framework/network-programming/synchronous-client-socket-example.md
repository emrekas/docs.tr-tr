---
title: Zaman Uyumlu İstemci Yuvası Örneği
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sockets, code examples
- synchronous client sockets
- sockets, synchronous client sockets
ms.assetid: 2c7d5be7-2221-467c-a839-5744ec4d576d
ms.openlocfilehash: ef8669e9e78f65451ffb250283a1f14c89d61270
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219752"
---
# <a name="synchronous-client-socket-example"></a><span data-ttu-id="92b46-102">Zaman Uyumlu İstemci Yuvası Örneği</span><span class="sxs-lookup"><span data-stu-id="92b46-102">Synchronous Client Socket Example</span></span>
<span data-ttu-id="92b46-103">Aşağıdaki örnek program bir sunucuya bağlanan bir istemcinin oluşturur.</span><span class="sxs-lookup"><span data-stu-id="92b46-103">The following example program creates a client that connects to a server.</span></span> <span data-ttu-id="92b46-104">İstemci, sunucunun bir yanıt döndürür kadar istemci uygulamanın yürütülmesini askıya alınmış şekilde zaman uyumlu bir yuva ile oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="92b46-104">The client is built with a synchronous socket, so execution of the client application is suspended until the server returns a response.</span></span> <span data-ttu-id="92b46-105">Uygulama sunucusuna bir dize gönderir ve daha sonra konsolda sunucu tarafından döndürülen dize görüntüler.</span><span class="sxs-lookup"><span data-stu-id="92b46-105">The application sends a string to the server and then displays the string returned by the server on the console.</span></span>  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class SynchronousSocketClient  
  
    Public Shared Sub Main()  
        ' Data buffer for incoming data.  
        Dim bytes(1024) As Byte  
  
        ' Connect to a remote device.  
  
        ' Establish the remote endpoint for the socket.  
        ' This example uses port 11000 on the local computer.  
        Dim ipHostInfo As IPHostEntry = Dns.GetHostEntry(Dns.GetHostName())  
        Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
        Dim remoteEP As New IPEndPoint(ipAddress, 11000)  
  
        ' Create a TCP/IP socket.  
        Dim sender As New Socket(ipAddress.AddressFamily, _  
            SocketType.Stream, ProtocolType.Tcp)  
  
        ' Connect the socket to the remote endpoint.  
        sender.Connect(remoteEP)  
  
        Console.WriteLine("Socket connected to {0}", _  
            sender.RemoteEndPoint.ToString())  
  
        ' Encode the data string into a byte array.  
        Dim msg As Byte() = _  
            Encoding.ASCII.GetBytes("This is a test<EOF>")  
  
        ' Send the data through the socket.  
        Dim bytesSent As Integer = sender.Send(msg)  
  
        ' Receive the response from the remote device.  
        Dim bytesRec As Integer = sender.Receive(bytes)  
        Console.WriteLine("Echoed test = {0}", _  
            Encoding.ASCII.GetString(bytes, 0, bytesRec))  
  
        ' Release the socket.  
        sender.Shutdown(SocketShutdown.Both)  
        sender.Close()  
    End Sub  
  
End Class 'SynchronousSocketClient  
```  
  
```csharp  
using System;  
using System.Net;  
using System.Net.Sockets;  
using System.Text;  
  
public class SynchronousSocketClient {  
  
    public static void StartClient() {  
        // Data buffer for incoming data.  
        byte[] bytes = new byte[1024];  
  
        // Connect to a remote device.  
        try {  
            // Establish the remote endpoint for the socket.  
            // This example uses port 11000 on the local computer.  
            IPHostEntry ipHostInfo = Dns.GetHostEntry(Dns.GetHostName());  
            IPAddress ipAddress = ipHostInfo.AddressList[0];  
            IPEndPoint remoteEP = new IPEndPoint(ipAddress,11000);  
  
            // Create a TCP/IP  socket.  
            Socket sender = new Socket(ipAddress.AddressFamily,   
                SocketType.Stream, ProtocolType.Tcp );  
  
            // Connect the socket to the remote endpoint. Catch any errors.  
            try {  
                sender.Connect(remoteEP);  
  
                Console.WriteLine("Socket connected to {0}",  
                    sender.RemoteEndPoint.ToString());  
  
                // Encode the data string into a byte array.  
                byte[] msg = Encoding.ASCII.GetBytes("This is a test<EOF>");  
  
                // Send the data through the socket.  
                int bytesSent = sender.Send(msg);  
  
                // Receive the response from the remote device.  
                int bytesRec = sender.Receive(bytes);  
                Console.WriteLine("Echoed test = {0}",  
                    Encoding.ASCII.GetString(bytes,0,bytesRec));  
  
                // Release the socket.  
                sender.Shutdown(SocketShutdown.Both);  
                sender.Close();  
  
            } catch (ArgumentNullException ane) {  
                Console.WriteLine("ArgumentNullException : {0}",ane.ToString());  
            } catch (SocketException se) {  
                Console.WriteLine("SocketException : {0}",se.ToString());  
            } catch (Exception e) {  
                Console.WriteLine("Unexpected exception : {0}", e.ToString());  
            }  
  
        } catch (Exception e) {  
            Console.WriteLine( e.ToString());  
        }  
    }  
  
    public static int Main(String[] args) {  
        StartClient();  
        return 0;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="92b46-106">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="92b46-106">See also</span></span>

- [<span data-ttu-id="92b46-107">Zaman Uyumlu Sunucu Yuvası Örneği</span><span class="sxs-lookup"><span data-stu-id="92b46-107">Synchronous Server Socket Example</span></span>](../../../docs/framework/network-programming/synchronous-server-socket-example.md)
- [<span data-ttu-id="92b46-108">Zaman Uyumlu İstemci Yuvası Kullanma</span><span class="sxs-lookup"><span data-stu-id="92b46-108">Using a Synchronous Client Socket</span></span>](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)
- [<span data-ttu-id="92b46-109">Yuva Kod Örnekleri</span><span class="sxs-lookup"><span data-stu-id="92b46-109">Socket Code Examples</span></span>](../../../docs/framework/network-programming/socket-code-examples.md)
