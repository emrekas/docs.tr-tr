---
title: 'Nasıl yapılır: Çift yönlü sözleşme oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: 8cc53f6842d55892ae178e22e2835555a132778b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693642"
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="1b38f-102">Nasıl yapılır: Çift yönlü sözleşme oluşturma</span><span class="sxs-lookup"><span data-stu-id="1b38f-102">How to: Create a Duplex Contract</span></span>
<span data-ttu-id="1b38f-103">Bu konu, çift yönlü Sözleşme (iki yönlü) kullanan yöntemleri oluşturmak için temel adımları gösterir.</span><span class="sxs-lookup"><span data-stu-id="1b38f-103">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="1b38f-104">Çift yönlü sözleşme, istemciler ve sunucular ya da diğer çağrıları başlatabilir, böylece birbiriyle bağımsız olarak iletişim kurmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="1b38f-104">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="1b38f-105">Çift yönlü sözleşme Windows Communication Foundation (WCF) Hizmetleri için kullanılabilir üç ileti modelinden biridir.</span><span class="sxs-lookup"><span data-stu-id="1b38f-105">The duplex contract is one of three message patterns available to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="1b38f-106">Diğer iki ileti desenleri olan tek yönlü ve istek-yanıt.</span><span class="sxs-lookup"><span data-stu-id="1b38f-106">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="1b38f-107">Çift yönlü sözleşme, istemci ve sunucu arasında iki yönlü sözleşmeler oluşur ve yöntem çağrıları bağıntılı gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="1b38f-107">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="1b38f-108">Bu tür bir sözleşme hizmetiniz daha fazla bilgi için istemci sorgu veya olay istemci üzerinde açıkça kullanın.</span><span class="sxs-lookup"><span data-stu-id="1b38f-108">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> <span data-ttu-id="1b38f-109">Bir istemci uygulaması için çift yönlü sözleşme oluşturma hakkında daha fazla bilgi için bkz. [nasıl yapılır: Çift yönlü sözleşme ile hizmetlere erişme](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="1b38f-109">For more information about creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="1b38f-110">Çalışma örnek için bkz: [çift yönlü](../../../../docs/framework/wcf/samples/duplex.md) örnek.</span><span class="sxs-lookup"><span data-stu-id="1b38f-110">For a working sample, see the [Duplex](../../../../docs/framework/wcf/samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="1b38f-111">Çift yönlü sözleşme oluşturma</span><span class="sxs-lookup"><span data-stu-id="1b38f-111">To create a duplex contract</span></span>  
  
1.  <span data-ttu-id="1b38f-112">Çift yönlü sözleşme sunucu tarafı yapan arabirim oluşturun.</span><span class="sxs-lookup"><span data-stu-id="1b38f-112">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2.  <span data-ttu-id="1b38f-113">Uygulama <xref:System.ServiceModel.ServiceContractAttribute> arabirimi sınıfı.</span><span class="sxs-lookup"><span data-stu-id="1b38f-113">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3.  <span data-ttu-id="1b38f-114">Yöntem imzaları arabiriminde bildirin.</span><span class="sxs-lookup"><span data-stu-id="1b38f-114">Declare the method signatures in the interface.</span></span>  
  
4.  <span data-ttu-id="1b38f-115">Uygulama <xref:System.ServiceModel.OperationContractAttribute> genel sözleşmesinin bir parçası olması gereken her yöntem imzası için sınıf.</span><span class="sxs-lookup"><span data-stu-id="1b38f-115">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5.  <span data-ttu-id="1b38f-116">İstemcide hizmet çağırabilirsiniz işlemler kümesini tanımlayan bir geri arama arabirimini oluşturun.</span><span class="sxs-lookup"><span data-stu-id="1b38f-116">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6.  <span data-ttu-id="1b38f-117">Geri arama arabirimini yöntem imzaları bildirin.</span><span class="sxs-lookup"><span data-stu-id="1b38f-117">Declare the method signatures in the callback interface.</span></span>  
  
7.  <span data-ttu-id="1b38f-118">Uygulama <xref:System.ServiceModel.OperationContractAttribute> genel sözleşmesinin bir parçası olması gereken her yöntem imzası için sınıf.</span><span class="sxs-lookup"><span data-stu-id="1b38f-118">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8.  <span data-ttu-id="1b38f-119">İki arabirim çift yönlü sözleşme ayarlayarak bağlantı <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> geri arama arabirimini türü için birincil arabirim özelliği.</span><span class="sxs-lookup"><span data-stu-id="1b38f-119">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="1b38f-120">İstemci üzerinde yöntemleri çağırmak için</span><span class="sxs-lookup"><span data-stu-id="1b38f-120">To call methods on the client</span></span>  
  
1.  <span data-ttu-id="1b38f-121">Birincil sözleşme hizmetin uygulamasında geri çağırma arabirimi için bir değişken bildirir.</span><span class="sxs-lookup"><span data-stu-id="1b38f-121">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2.  <span data-ttu-id="1b38f-122">Tarafından döndürülen nesne başvuru değişkenini <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> yöntemi <xref:System.ServiceModel.OperationContext> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="1b38f-122">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3.  <span data-ttu-id="1b38f-123">Geri çağırma arabirim tarafından tanımlanan yöntemler çağırır.</span><span class="sxs-lookup"><span data-stu-id="1b38f-123">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b38f-124">Örnek</span><span class="sxs-lookup"><span data-stu-id="1b38f-124">Example</span></span>  
 <span data-ttu-id="1b38f-125">Aşağıdaki kod örneği, çift yönlü iletişimi gösterir.</span><span class="sxs-lookup"><span data-stu-id="1b38f-125">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="1b38f-126">Taşıma için hizmet işlemleri ileriye ve geriye doğru hizmet sözleşmesi içeriyor.</span><span class="sxs-lookup"><span data-stu-id="1b38f-126">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="1b38f-127">İstemcinin konumuna raporlama için bir hizmet işlemi içeriyor.</span><span class="sxs-lookup"><span data-stu-id="1b38f-127">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
-   <span data-ttu-id="1b38f-128">Uygulama <xref:System.ServiceModel.ServiceContractAttribute> ve <xref:System.ServiceModel.OperationContractAttribute> öznitelikleri, Web Hizmetleri Açıklama Dili (WSDL) hizmet sözleşme tanımları otomatik olarak oluşturulmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="1b38f-128">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
-   <span data-ttu-id="1b38f-129">Kullanım [ServiceModel meta veri yardımcı Programracı (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) WSDL belgesi (isteğe bağlı) kodu ve bir istemci yapılandırması alınamıyor.</span><span class="sxs-lookup"><span data-stu-id="1b38f-129">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
-   <span data-ttu-id="1b38f-130">Çift yönlü hizmetler gösterme uç noktalarını güvenli hale getirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="1b38f-130">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="1b38f-131">Bir hizmeti çift yönlü bir ileti aldığında yanıt göndermesi yerini belirlemek için gelen bu iletide ReplyTo bakar.</span><span class="sxs-lookup"><span data-stu-id="1b38f-131">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="1b38f-132">Ardından kanal güvenli değildir, güvenilmeyen bir istemci bir hedef makine, hizmet reddi için önde gelen bir hedef makinenin ReplyTo içeren kötü amaçlı bir ileti gönderebilir.</span><span class="sxs-lookup"><span data-stu-id="1b38f-132">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="1b38f-133">Normal istek-yanıt iletileri, bu bir sorun ReplyTo göz ardı edilir ve yanıt üzerinde özgün iletinin geldiği kanal üzerinde gönderilen değildir.</span><span class="sxs-lookup"><span data-stu-id="1b38f-133">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b38f-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1b38f-134">See also</span></span>
- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="1b38f-135">Nasıl yapılır: Çift yönlü sözleşme ile hizmetlere erişim</span><span class="sxs-lookup"><span data-stu-id="1b38f-135">How to: Access Services with a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="1b38f-136">Çift Yönlü</span><span class="sxs-lookup"><span data-stu-id="1b38f-136">Duplex</span></span>](../../../../docs/framework/wcf/samples/duplex.md)
- [<span data-ttu-id="1b38f-137">Hizmetleri Tasarlama ve Uygulama</span><span class="sxs-lookup"><span data-stu-id="1b38f-137">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="1b38f-138">Nasıl yapılır: Bir hizmet sözleşmesini tanımlama</span><span class="sxs-lookup"><span data-stu-id="1b38f-138">How to: Define a Service Contract</span></span>](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="1b38f-139">Oturum</span><span class="sxs-lookup"><span data-stu-id="1b38f-139">Session</span></span>](../../../../docs/framework/wcf/samples/session.md)
