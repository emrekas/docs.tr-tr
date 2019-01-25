---
title: Internet istekleri oluşturma
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
ms.openlocfilehash: 07c15614f22409f427c6f75cd4ddb8cfa218beba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706961"
---
# <a name="creating-internet-requests"></a><span data-ttu-id="9c81a-102">Internet istekleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="9c81a-102">Creating Internet Requests</span></span>
<span data-ttu-id="9c81a-103">Uygulamaları oluşturmak <xref:System.Net.WebRequest> aracılığıyla örnekler <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="9c81a-103">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9c81a-104">Türetilen bir sınıf oluşturur statik bir yöntem budur **WebRequest** geçirilen URI şeması göre.</span><span class="sxs-lookup"><span data-stu-id="9c81a-104">This is a static method that creates a class derived from **WebRequest** based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="9c81a-105">Web, dosya ve FTP istekleri</span><span class="sxs-lookup"><span data-stu-id="9c81a-105">Web, File and FTP Requests</span></span>  
 <span data-ttu-id="9c81a-106">.NET Framework sağlar <xref:System.Net.HttpWebRequest> sınıfından türetilen sınıf **WebRequest**, HTTP ve HTTPS isteklerini işlemek için.</span><span class="sxs-lookup"><span data-stu-id="9c81a-106">The .NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from **WebRequest**, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="9c81a-107">Çoğu durumda **WebRequest** sınıfı bir istekte bulunmak için ihtiyacınız olan tüm özellikler sağlar; gerekirse, ancak çevirebilirsiniz **WebRequest** tarafından oluşturulmuş nesneleri **WebRequest.Create**  yönteme **HttpWebRequest** isteğin HTTP'ye özgü özelliklere erişim türü.</span><span class="sxs-lookup"><span data-stu-id="9c81a-107">In most cases, the **WebRequest** class provides all the properties you need to make a request; however, if necessary, you can cast **WebRequest** objects created by the **WebRequest.Create** method to the **HttpWebRequest** type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="9c81a-108">Benzer şekilde, **HttpWebResponse** nesnesini işleme alınan HTTP ve HTTPS istekleri yanıtlar.</span><span class="sxs-lookup"><span data-stu-id="9c81a-108">Similarly, the **HttpWebResponse** object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="9c81a-109">HTTP özel özelliklerine erişmek için **HttpWebResponse** nesnesi, tür dönüştürme için gereksinim duyduğunuz **WebResponse** nesneleri için **HttpWebResponse** türü.</span><span class="sxs-lookup"><span data-stu-id="9c81a-109">To access the HTTP-specific properties of the **HttpWebResponse** object, you need to cast **WebResponse** objects to the **HttpWebResponse** type.</span></span>  
  
 <span data-ttu-id="9c81a-110">.NET Framework ayrıca sağlar <xref:System.Net.FileWebRequest> ve <xref:System.Net.FileWebResponse> kullandığınız kaynaklar için istekleri işlemek için sınıflar "dosya:" URI şeması.</span><span class="sxs-lookup"><span data-stu-id="9c81a-110">The .NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="9c81a-111">Benzer şekilde, <xref:System.Net.FtpWebRequest> ve <xref:System.Net.FtpWebResponse> sınıfları kullanan kaynaklar için istekleri işlemek için sağlanan "ftp:" düzeni.</span><span class="sxs-lookup"><span data-stu-id="9c81a-111">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="9c81a-112">İsteğiniz bu düzenleri birini kullanan bir kaynak varsa kullanabileceğiniz **WebRequest.Create** hangi, istekte bulunmak bir nesne elde etmek için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="9c81a-112">If your request is for a resource that uses any of these schemes, you can use the **WebRequest.Create** method to obtain an object with which to make your request.</span></span>  
  
 <span data-ttu-id="9c81a-113">Diğer uygulama düzeyi protokolleri kullanan isteklerini işlemek için türetilen protokole özgü sınıfların uygulamanız gereken **WebRequest** ve **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="9c81a-113">To handle requests that use other application-level protocols, you need to implement protocol-specific classes derived from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="9c81a-114">Daha fazla bilgi için [takılabilir protokoller programlama](../../../docs/framework/network-programming/programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="9c81a-114">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c81a-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9c81a-115">See also</span></span>
- [<span data-ttu-id="9c81a-116">Nasıl yapılır: WebRequest sınıfını kullanarak veri isteme</span><span class="sxs-lookup"><span data-stu-id="9c81a-116">How to: Request Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="9c81a-117">Veri İsteme</span><span class="sxs-lookup"><span data-stu-id="9c81a-117">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
