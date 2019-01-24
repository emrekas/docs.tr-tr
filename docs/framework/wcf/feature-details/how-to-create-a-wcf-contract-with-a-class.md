---
title: 'Nasıl yapılır: Bir Windows Communication Foundation sözleşme sınıfı ile oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: b32d4feb03daac33af8b7ca3b533a0b7013bb090
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658932"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="c188e-102">Nasıl yapılır: Bir Windows Communication Foundation sözleşme sınıfı ile oluşturma</span><span class="sxs-lookup"><span data-stu-id="c188e-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="c188e-103">Bir Windows Communication Foundation (WCF) sözleşmesi oluşturma tercih edilen yol, bir arabirim kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="c188e-103">The preferred way of creating a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="c188e-104">Daha fazla bilgi için [nasıl yapılır: Bir hizmet sözleşmesini tanımlama](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="c188e-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="c188e-105">Bir alternatif, Anahatlı burayı olan bir sınıf oluşturun ve ardından uygulama <xref:System.ServiceModel.ServiceContractAttribute> sınıfı özniteliği doğrudan ve <xref:System.ServiceModel.OperationContractAttribute> her sözleşmesinin bir parçası olan yöntemler için özniteliği.</span><span class="sxs-lookup"><span data-stu-id="c188e-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c188e-106">`[ServiceContract]` ve `[ServiceContractAttribute]` aynı işlevi görür.</span><span class="sxs-lookup"><span data-stu-id="c188e-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="c188e-107">Aynı şeyi true `[OperationContract]` ve `[OperationContractAttribute]`.</span><span class="sxs-lookup"><span data-stu-id="c188e-107">The same thing is true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="c188e-108">Her durumda, önceki ikincisi için Toplu özellik var.</span><span class="sxs-lookup"><span data-stu-id="c188e-108">In each case, the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="c188e-109">Hizmet sözleşmeleri hakkında daha fazla bilgi için bkz: [Hizmet sözleşmeleri tasarlama](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="c188e-109">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="c188e-110">Bir Windows Communication Foundation sözleşme sınıfı ile oluşturma</span><span class="sxs-lookup"><span data-stu-id="c188e-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1.  <span data-ttu-id="c188e-111">Visual Basic kullanarak yeni bir sınıf oluşturun C#, veya tüm diğer ortak dil çalışma zamanı dil.</span><span class="sxs-lookup"><span data-stu-id="c188e-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="c188e-112">Uygulama <xref:System.ServiceModel.ServiceContractAttribute> sınıfı için sınıf.</span><span class="sxs-lookup"><span data-stu-id="c188e-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3.  <span data-ttu-id="c188e-113">Sınıfı yöntemleri oluşturun.</span><span class="sxs-lookup"><span data-stu-id="c188e-113">Create methods in the class.</span></span>  
  
4.  <span data-ttu-id="c188e-114">Uygulama <xref:System.ServiceModel.OperationContractAttribute> genel WCF sözleşmesinin bir parçası sunulan her yöntem için sınıf.</span><span class="sxs-lookup"><span data-stu-id="c188e-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c188e-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="c188e-115">Example</span></span>  
 <span data-ttu-id="c188e-116">Aşağıdaki kod örneği bir hizmet anlaşmasını tanımlayan bir sınıf gösterir.</span><span class="sxs-lookup"><span data-stu-id="c188e-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="c188e-117">Sahip yöntemleri <xref:System.ServiceModel.OperationContractAttribute> uygulanan sınıfı, varsayılan olarak istek-yanıt iletisi deseni kullanın.</span><span class="sxs-lookup"><span data-stu-id="c188e-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="c188e-118">Bu ileti düzeni hakkında daha fazla bilgi için bkz. [nasıl yapılır: İstek-yanıt anlaşması oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="c188e-118">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="c188e-119">Ayrıca, oluşturabilir ve diğer ileti desenleri öznitelik özelliklerini ayarlayarak kullanın.</span><span class="sxs-lookup"><span data-stu-id="c188e-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="c188e-120">Daha fazla örnek için bkz. [nasıl yapılır: Tek yönlü anlaşma oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) ve [nasıl yapılır: Çift yönlü sözleşme oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="c188e-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c188e-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c188e-121">See also</span></span>
- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
