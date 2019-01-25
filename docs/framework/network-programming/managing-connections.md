---
title: Bağlantıları yönetme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, connections
- HTTP, classes for connecting
- requesting data from Internet, connections
- sending data, connections
- receiving data, connections
- ServicePoint class, about ServicePoint class
- response to Internet request, connections
- connections [.NET Framework], classes
- network resources, connections
- downloading Internet resources, connections
- ServicePointManager class, about ServicePointManager class
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
ms.openlocfilehash: e5579dd05e11de9dd54023604f7515fb52fb29a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650739"
---
# <a name="managing-connections"></a><span data-ttu-id="5ca7c-102">Bağlantıları yönetme</span><span class="sxs-lookup"><span data-stu-id="5ca7c-102">Managing Connections</span></span>
<span data-ttu-id="5ca7c-103">Veri kaynaklarına bağlanmak için HTTP kullanan uygulamalar, .NET Framework'ün kullanabileceğiniz <xref:System.Net.ServicePoint> ve <xref:System.Net.ServicePointManager> sınıfları için Internet bağlantılarını yönetme ve en yüksek ölçek ve performans elde etmelerine yardımcı olmak için.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-103">Applications that use HTTP to connect to data resources can use the .NET Framework's <xref:System.Net.ServicePoint> and <xref:System.Net.ServicePointManager> classes to manage connections to the Internet and to help them achieve optimum scale and performance.</span></span>  
  
 <span data-ttu-id="5ca7c-104">**ServicePoint** sınıfı için uygulama bağlanabilir Internet kaynaklarına erişebilmesi için bir uç nokta ile bir uygulama sağlar.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-104">The **ServicePoint** class provides an application with an endpoint to which the application can connect to access Internet resources.</span></span> <span data-ttu-id="5ca7c-105">Her **ServicePoint** yardımcı performansını artırmak için bağlantıları arasında en iyi duruma getirme bilgilerini paylaşarak bağlantıları Internet sunucusuyla iyileştirme bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-105">Each **ServicePoint** contains information that helps optimize connections with an Internet server by sharing optimization information between connections to improve performance.</span></span>  
  
 <span data-ttu-id="5ca7c-106">Her **ServicePoint** bir Tekdüzen Kaynak Tanımlayıcısı (URI) tarafından tanımlanır ve düzeni tanımlayıcı ve konak parçaları URI göre kategorilere ayrılır.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-106">Each **ServicePoint** is identified by a Uniform Resource Identifier (URI) and is categorized according to the scheme identifier and host fragments of the URI.</span></span> <span data-ttu-id="5ca7c-107">Örneğin, aynı **ServicePoint** örneği istekleri için bir URI'leri sunar `http://www.contoso.com/index.htm` ve `http://www.contoso.com/news.htm?date=today` aynı düzen tanımlayıcısı (http) ve konak parçaları sahip olduğundan (`www.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="5ca7c-107">For example, the same **ServicePoint** instance would provide requests to the URIs `http://www.contoso.com/index.htm` and `http://www.contoso.com/news.htm?date=today` since they have the same scheme identifier (http) and host fragments (`www.contoso.com`).</span></span> <span data-ttu-id="5ca7c-108">Uygulama zaten sunucuya kalıcı bir bağlantı varsa `www.contoso.com`, iki bağlantı oluşturmak için gereğinden kurtulursunuz hem istekleri almak için bu bağlantıyı kullanır.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-108">If the application already has a persistent connection to the server `www.contoso.com`, it uses that connection to retrieve both requests, avoiding the need to create two connections.</span></span>  
  
 <span data-ttu-id="5ca7c-109">**ServicePointManager** oluşturma ve yok edilmesini yönetir, statik bir sınıftır **ServicePoint** örnekleri.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-109">**ServicePointManager** is a static class that manages the creation and destruction of **ServicePoint** instances.</span></span> <span data-ttu-id="5ca7c-110">**ServicePointManager** oluşturur bir **ServicePoint** uygulama koleksiyonunda mevcut olmayan bir Internet kaynağına istediğinde **ServicePoint** örnekleri.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-110">The **ServicePointManager** creates a **ServicePoint** when the application requests an Internet resource that is not in the collection of existing **ServicePoint** instances.</span></span> <span data-ttu-id="5ca7c-111">**ServicePoint** örnekleri yok, en fazla boşta kalma süresi aştığınızda veya sayısı varolan **ServicePoint** örnekleri üst sınırını aşıyor **ServicePoint**uygulama örnekleri.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-111">**ServicePoint** instances are destroyed when they have exceeded their maximum idle time or when the number of existing **ServicePoint** instances exceeds the maximum number of **ServicePoint** instances for the application.</span></span> <span data-ttu-id="5ca7c-112">Varsayılan en fazla boşta kalma süresi hem üst sınırını denetleyebilirsiniz **ServicePoint** ayarlayarak örnekleri <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> ve <xref:System.Net.ServicePointManager.MaxServicePoints%2A> özellikleri **ServicePointManager**.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-112">You can control both the default maximum idle time and the maximum number of **ServicePoint** instances by setting the <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> and <xref:System.Net.ServicePointManager.MaxServicePoints%2A> properties on the **ServicePointManager**.</span></span>  
  
 <span data-ttu-id="5ca7c-113">İstemci ve sunucu arasındaki bağlantı sayısı, uygulamanın aktarım hızını önemli bir etkisi olabilir.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-113">The number of connections between a client and server can have a dramatic impact on application throughput.</span></span> <span data-ttu-id="5ca7c-114">Varsayılan olarak, bir uygulama kullanarak <xref:System.Net.HttpWebRequest> sınıfı iki kalıcı bağlantı verilen bir sunucu için en fazla kullanır, ancak bir uygulama başına temelinde en fazla bağlantı sayısını ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-114">By default, an application using the <xref:System.Net.HttpWebRequest> class uses a maximum of two persistent connections to a given server, but you can set the maximum number of connections on a per-application basis.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ca7c-115">HTTP/1.1 belirtimini uygulamadan sunucu başına iki bağlantı için bağlantı sayısını sınırlar.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-115">The HTTP/1.1 specification limits the number of connections from an application to two connections per server.</span></span>  
  
 <span data-ttu-id="5ca7c-116">En yüksek bağlantı sayısını, uygulamanın çalıştığı gerçek koşullara bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-116">The optimum number of connections depends on the actual conditions in which the application runs.</span></span> <span data-ttu-id="5ca7c-117">Uygulama için kullanılabilir bağlantı sayısının artırılması uygulama performansını etkileyebilir değil.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-117">Increasing the number of connections available to the application may not affect application performance.</span></span> <span data-ttu-id="5ca7c-118">Daha fazla bağlantı etkisini belirlemek için bağlantı sayısını değişen sırasında performans testleri çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-118">To determine the impact of more connections, run performance tests while varying the number of connections.</span></span> <span data-ttu-id="5ca7c-119">Statik değiştirerek bir uygulamanın kullandığı bağlantı sayısını değiştirebilirsiniz <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> özelliği **ServicePointManager** uygulama başlatma sırasında aşağıdaki kod örneğinde gösterildiği gibi sınıf.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-119">You can change the number of connections that an application uses by changing the static <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> property on the **ServicePointManager** class at application initialization, as shown in the following code sample.</span></span>  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 <span data-ttu-id="5ca7c-120">Değiştirme **ServicePointManager.DefaultConnectionLimit** özelliği daha önce başlatılmış etkilemez **ServicePoint** örnekleri.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-120">Changing the **ServicePointManager.DefaultConnectionLimit** property does not affect previously initialized **ServicePoint** instances.</span></span> <span data-ttu-id="5ca7c-121">Aşağıdaki kod, var olan bir bağlantı sınırı değiştirme gösterir **ServicePoint** sunucusunun `http://www.contoso.com` depolanan değere `newLimit`.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-121">The following code demonstrates changing the connection limit on an existing **ServicePoint** for the server `http://www.contoso.com` to the value stored in `newLimit`.</span></span>  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ca7c-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-122">See also</span></span>
- [<span data-ttu-id="5ca7c-123">Bağlantı Gruplandırma</span><span class="sxs-lookup"><span data-stu-id="5ca7c-123">Connection Grouping</span></span>](../../../docs/framework/network-programming/connection-grouping.md)
- [<span data-ttu-id="5ca7c-124">Uygulama Protokolleri Kullanma</span><span class="sxs-lookup"><span data-stu-id="5ca7c-124">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
