---
title: 'Nasıl yapılır: İnternet ile İletişim Kurmak Üzere Ara Sunucu Kullanan bir WebRequest’i Etkinleştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: a2179e767a0556f5223f2f4c1cc91708133120a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103707"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="01510-102">Nasıl yapılır: İnternet ile İletişim Kurmak Üzere Ara Sunucu Kullanan bir WebRequest’i Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="01510-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="01510-103">Bu örnek, tüm olanak sağlayacak bir genel proxy örneği oluşturur <xref:System.Net.WebRequest> Internet ile iletişim kurmak için bir ara sunucu kullanmak için.</span><span class="sxs-lookup"><span data-stu-id="01510-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="01510-104">Bu örnek, proxy sunucusu adlandırıldığını varsayar `webproxy` ve üzerinde iletişim bağlantı noktası 80, standart HTTP bağlantı noktası.</span><span class="sxs-lookup"><span data-stu-id="01510-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01510-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="01510-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="01510-106">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="01510-106">Compiling the Code</span></span>  
 <span data-ttu-id="01510-107">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="01510-107">This example requires:</span></span>  
  
-   <span data-ttu-id="01510-108">A [ `using` yönergesi](../../csharp/language-reference/keywords/using-directive.md) için **System.Net** ad alanı.</span><span class="sxs-lookup"><span data-stu-id="01510-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01510-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="01510-109">See also</span></span>

- [<span data-ttu-id="01510-110">Uygulama Protokolleri Kullanma</span><span class="sxs-lookup"><span data-stu-id="01510-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="01510-111">Ara Sunucu Üzerinden İnternet Erişimi</span><span class="sxs-lookup"><span data-stu-id="01510-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
