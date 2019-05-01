---
title: Web ve Yuva İzinleri
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
ms.openlocfilehash: 78ad06107155408b2aca854a8251c21a24c6577a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788095"
---
# <a name="web-and-socket-permissions"></a><span data-ttu-id="886a1-102">Web ve Yuva İzinleri</span><span class="sxs-lookup"><span data-stu-id="886a1-102">Web and Socket Permissions</span></span>
<span data-ttu-id="886a1-103">Internet güvenliği kullanan uygulamalar için <xref:System.Net> ad alanı tarafından sağlanır <xref:System.Net.WebPermission> ve <xref:System.Net.SocketPermission> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="886a1-103">Internet security for applications using the <xref:System.Net> namespace is provided by the <xref:System.Net.WebPermission> and <xref:System.Net.SocketPermission> classes.</span></span> <span data-ttu-id="886a1-104">**WebPermission** sınıfı uygulama isteği verilerini Sağdan bir URI veya Internet'e bir URI sunmak için denetler.</span><span class="sxs-lookup"><span data-stu-id="886a1-104">The **WebPermission** class controls an application's right to request data from a URI or to serve a URI to the Internet.</span></span> <span data-ttu-id="886a1-105">**SocketPermission** sınıfını kullanmak doğru uygulama denetimleri bir <xref:System.Net.Sockets.Socket> verileri bir yerel bağlantı noktasında kabul etmek için veya başka bir adreste bağlantı noktası numarası, konak temel alınarak bir aktarım protokolünü kullanarak uzak aygıtıyla bağlantı kurmayı ve Yuva Aktarımı Protokolü.</span><span class="sxs-lookup"><span data-stu-id="886a1-105">The **SocketPermission** class controls an application's right to use a <xref:System.Net.Sockets.Socket> to accept data on a local port or to contact remote devices using a transport protocol at another address, based on the host, port number, and transport protocol of the socket.</span></span>  
  
 <span data-ttu-id="886a1-106">Kullandığınız hangi izin sınıfı uygulama türüne bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="886a1-106">Which permission class you use depends on your application type.</span></span> <span data-ttu-id="886a1-107">Kullanan uygulamalar <xref:System.Net.WebRequest> ve alt öğelerini kullanması gereken **WebPermission** izinleri yönetmek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="886a1-107">Applications that use <xref:System.Net.WebRequest> and its descendants should use the **WebPermission** class to manage permissions.</span></span> <span data-ttu-id="886a1-108">Yuva düzeyinde erişim kullanan uygulamaların kullanması gereken **SocketPermission** izinleri yönetmek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="886a1-108">Applications that use socket-level access should use the **SocketPermission** class to manage permissions.</span></span>  
  
 <span data-ttu-id="886a1-109">**WebPermission** ve **SocketPermission** iki izinleri tanımlayın: kabul edin ve bağlanın.</span><span class="sxs-lookup"><span data-stu-id="886a1-109">**WebPermission** and **SocketPermission** define two permissions: accept and connect.</span></span> <span data-ttu-id="886a1-110">Kabul etmek uygulamanın başka bir tarafın gelen bağlantının yanıt verme hakkı tanımaz.</span><span class="sxs-lookup"><span data-stu-id="886a1-110">Accept grants the application the right to answer an incoming connection from another party.</span></span> <span data-ttu-id="886a1-111">Connect uygulama başka bir tarafa bağlantı verme hakkı tanımaz.</span><span class="sxs-lookup"><span data-stu-id="886a1-111">Connect grants the application the right to initiate a connection to another party.</span></span>  
  
 <span data-ttu-id="886a1-112">İçin **SocketPermission** örnekleri, bir uygulamanın yerel gelen bağlantıları kabul edebilir anlamına gelir kabul Aktarım adresi; bağlandıkları bir uygulamanın bazı Uzak (veya yerel) aktarım adresine bağlanabileceği anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="886a1-112">For **SocketPermission** instances, accept means that an application can accept incoming connections on a local transport address; connect means that an application can connect to some remote (or local) transport address.</span></span>  
  
 <span data-ttu-id="886a1-113">İçin **WebPermission** örnekleri, bir uygulama tarafından denetlenen URI verebilirsiniz anlamına gelir kabul **WebPermission** uygulama (olup bu URI'ye erişebileceği anlamına gelir; dünya bağlanma Uzak veya yerel).</span><span class="sxs-lookup"><span data-stu-id="886a1-113">For **WebPermission** instances, accept means that an application can export the URI controlled by the **WebPermission** to the world; connect means that an application can access that URI (whether it is remote or local).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="886a1-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="886a1-114">See also</span></span>

- [<span data-ttu-id="886a1-115">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="886a1-115">Security</span></span>](../../../docs/standard/security/index.md)
- [<span data-ttu-id="886a1-116">Ağ Programlama Güvenliği</span><span class="sxs-lookup"><span data-stu-id="886a1-116">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)
