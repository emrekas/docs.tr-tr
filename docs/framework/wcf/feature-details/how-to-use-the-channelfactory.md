---
title: 'Nasıl yapılır: ChannelFactory Kullanma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7d542a3dcae514e75194b49c23a8dec5dd7e8c3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047262"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="51e27-102">Nasıl yapılır: ChannelFactory Kullanma</span><span class="sxs-lookup"><span data-stu-id="51e27-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="51e27-103">Genel <xref:System.ServiceModel.ChannelFactory%601> sınıfı, birden fazla kanal oluşturmak için kullanılan kanal fabrikası oluşturulmasını gerektiren gelişmiş senaryolarda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="51e27-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="51e27-104">Oluşturma ve kullanma ChannelFactory sınıfı</span><span class="sxs-lookup"><span data-stu-id="51e27-104">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="51e27-105">Oluşturun ve bir Windows Communication Foundation (WCF) hizmetini çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="51e27-105">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="51e27-106">Daha fazla bilgi için [Hizmetleri Tasarlama ve uygulama](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Hizmetleri'ni Yapılandırma](../../../../docs/framework/wcf/configuring-services.md), ve [barındırma hizmetleri](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="51e27-106">For more information, see [Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Configuring Services](../../../../docs/framework/wcf/configuring-services.md), and [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
2. <span data-ttu-id="51e27-107">Kullanım [ServiceModel meta veri yardımcı Programracı (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) istemci için anlaşma (arabirimi) oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="51e27-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="51e27-108">İstemci kodunuzda kullanabileceğiniz <xref:System.ServiceModel.ChannelFactory%601> birden fazla uç noktası dinleyicisi oluşturmak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="51e27-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51e27-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="51e27-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
