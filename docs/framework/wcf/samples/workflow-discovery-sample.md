---
title: İş Akışı Keşif Örneği
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: 9a0d3ad22b4663ee71b5b2aa8d0e3d64f20996d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006466"
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="ae06f-102">İş Akışı Keşif Örneği</span><span class="sxs-lookup"><span data-stu-id="ae06f-102">Workflow Discovery Sample</span></span>
<span data-ttu-id="ae06f-103">Bu örnek, bir iş akışı hizmeti bulunabilir hale getirme ve belirli bir hizmet için arayan bir özel kod etkinliği yazmak nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="ae06f-103">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ae06f-104">Gösteriler</span><span class="sxs-lookup"><span data-stu-id="ae06f-104">Demonstrates</span></span>  
 <span data-ttu-id="ae06f-105">Keşif bulma etkinliği ve iş akışı kullanımı</span><span class="sxs-lookup"><span data-stu-id="ae06f-105">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ae06f-106">Tartışma</span><span class="sxs-lookup"><span data-stu-id="ae06f-106">Discussion</span></span>  
 <span data-ttu-id="ae06f-107">İlk bölümünde örnek bir iş akışı hizmeti bulunabilirlik yapılan yapılandırma kullanarak.</span><span class="sxs-lookup"><span data-stu-id="ae06f-107">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="ae06f-108">Yapılandırma özel meta verileri (örneğin, kapsam) hizmetiyle uygun şekilde uygulamak için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ae06f-108">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="ae06f-109">İstemcide, örnek bulma aramak için belirli bir sözleşme eşleşen bir hizmetini kullanan bir özel kod etkinliği kullanır.</span><span class="sxs-lookup"><span data-stu-id="ae06f-109">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="ae06f-110">Kod etkinliği, daha sonra bir gönderme etkinlik tarafından kullanılan bir URI çıkarır.</span><span class="sxs-lookup"><span data-stu-id="ae06f-110">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ae06f-111">Ayarlamak için derleme ve örneği çalıştırma</span><span class="sxs-lookup"><span data-stu-id="ae06f-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ae06f-112">Bu örneği çalıştırmak için doğru URL ACL olmalıdır HTTP uç noktaları kullanır (bkz [yapılandırma HTTP ve HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) Ayrıntılar için).</span><span class="sxs-lookup"><span data-stu-id="ae06f-112">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) for details).</span></span> <span data-ttu-id="ae06f-113">Yükseltilmiş bir komut isteminde aşağıdaki komutu yürütülürken uygun ACL'lerin eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ae06f-113">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="ae06f-114">Kabuğunuz değişken biçimi anlamıyorsa şu bağımsız değişkenler için kullanıcı adı ve etki alanı değiştirin.</span><span class="sxs-lookup"><span data-stu-id="ae06f-114">Substitute your Domain and Username for the following arguments if your shell does not understand the variable format.</span></span>  
  
     <span data-ttu-id="ae06f-115">**Netsh http ekleme urlacl url =http://+:8000/ kullanıcı etki alanı % =\\% UserName %**</span><span class="sxs-lookup"><span data-stu-id="ae06f-115">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae06f-116">Örnekler, makinenizde zaten yüklü.</span><span class="sxs-lookup"><span data-stu-id="ae06f-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ae06f-117">Devam etmeden önce şu (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="ae06f-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ae06f-118">Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="ae06f-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ae06f-119">Bu örnek, şu dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="ae06f-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
