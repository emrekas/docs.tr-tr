---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 3fa5ec62c5e8ac83f3f81fb406499b7e596b3dac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969513"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="9b3e5-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="9b3e5-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="9b3e5-103">İletinin MSMQ bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="9b3e5-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9b3e5-104">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9b3e5-104">Description</span></span>  
 <span data-ttu-id="9b3e5-105">İzleme, bir MSMQ iletisinin bırakıldı gösterir.</span><span class="sxs-lookup"><span data-stu-id="9b3e5-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="9b3e5-106">Windows Communication Foundation (WCF) (NetMsmqBinding veya MsmqIntegrationBinding ile kullanılır) bunları işleyemiyor olduğunda MSMQ iletileri bırakılabilir.</span><span class="sxs-lookup"><span data-stu-id="9b3e5-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="9b3e5-107">Bu türden iletilere zehirli ileti olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="9b3e5-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="9b3e5-108">Zehirli ileti ne zaman bırakılan `ReceiveErrorHandling` özelliği NetMsmqBinding veya MsmqIntegrationBinding `Drop`.</span><span class="sxs-lookup"><span data-stu-id="9b3e5-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="9b3e5-109">Bırakılan ileti kuyruktan kaldırılır ve artık kurtarılabilir.</span><span class="sxs-lookup"><span data-stu-id="9b3e5-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="9b3e5-110">Bkz: [Poison ileti işleme](https://go.microsoft.com/fwlink/?LinkID=99546) iletileri zehirli duruma ne zaman ve uygun şekilde işlemek için hizmetinizi yapılandırmak nasıl daha fazla ayrıntı için.</span><span class="sxs-lookup"><span data-stu-id="9b3e5-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b3e5-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9b3e5-111">See also</span></span>

- [<span data-ttu-id="9b3e5-112">İzleme</span><span class="sxs-lookup"><span data-stu-id="9b3e5-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="9b3e5-113">Uygulamanızda Sorun Giderme için İzleme Kullanma</span><span class="sxs-lookup"><span data-stu-id="9b3e5-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9b3e5-114">Yönetim ve Tanılama</span><span class="sxs-lookup"><span data-stu-id="9b3e5-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="9b3e5-115">Poison ileti işleme</span><span class="sxs-lookup"><span data-stu-id="9b3e5-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
