---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: e95b6923d21307b2ef68d4a5369b3cee86540239
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781985"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="e3c1e-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="e3c1e-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="e3c1e-103">Özellikler</span><span class="sxs-lookup"><span data-stu-id="e3c1e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3c1e-104">Kimlik</span><span class="sxs-lookup"><span data-stu-id="e3c1e-104">ID</span></span>|<span data-ttu-id="e3c1e-105">205</span><span class="sxs-lookup"><span data-stu-id="e3c1e-105">205</span></span>|  
|<span data-ttu-id="e3c1e-106">anahtar sözcükler</span><span class="sxs-lookup"><span data-stu-id="e3c1e-106">Keywords</span></span>|<span data-ttu-id="e3c1e-107">Sorun giderme, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e3c1e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e3c1e-108">Düzey</span><span class="sxs-lookup"><span data-stu-id="e3c1e-108">Level</span></span>|<span data-ttu-id="e3c1e-109">Bilgiler</span><span class="sxs-lookup"><span data-stu-id="e3c1e-109">Information</span></span>|  
|<span data-ttu-id="e3c1e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e3c1e-110">Channel</span></span>|<span data-ttu-id="e3c1e-111">Microsoft Windows uygulama sunucusu-uygulamalar/analitik</span><span class="sxs-lookup"><span data-stu-id="e3c1e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e3c1e-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e3c1e-112">Description</span></span>  
 <span data-ttu-id="e3c1e-113">Bu olay, yalnızca hizmet modelin varsayılan önce yayıldığını `OperationInvoker` bir yönteme bir çağrı başlar.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e3c1e-114">İleti</span><span class="sxs-lookup"><span data-stu-id="e3c1e-114">Message</span></span>  
 <span data-ttu-id="e3c1e-115">'%1' yöntemi bir OperationInvoker çağrılır.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="e3c1e-116">Arayan bilgileri: '%2'.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e3c1e-117">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="e3c1e-117">Details</span></span>  
  
|<span data-ttu-id="e3c1e-118">Veri öğesi adı</span><span class="sxs-lookup"><span data-stu-id="e3c1e-118">Data Item Name</span></span>|<span data-ttu-id="e3c1e-119">Veri öğesi türü</span><span class="sxs-lookup"><span data-stu-id="e3c1e-119">Data Item Type</span></span>|<span data-ttu-id="e3c1e-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e3c1e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e3c1e-121">Yöntem adı</span><span class="sxs-lookup"><span data-stu-id="e3c1e-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="e3c1e-122">CLR adı tarafından çağrılan yöntemin `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="e3c1e-123">Arayan Bilgileri</span><span class="sxs-lookup"><span data-stu-id="e3c1e-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="e3c1e-124">'IPAddress:PortNumber' biçimindeki istemci IP adresi ve bağlantı noktası numarası.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="e3c1e-125">İki değer işlem bağlamı içinde 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' iletisi özelliğinden alınır.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="e3c1e-126">TCP olmayan bağlamalarda unutmayın. Bu değer `null`.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="e3c1e-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="e3c1e-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="e3c1e-128">Bu alan, Web barındırılan hizmetleri, Web hiyerarşideki hizmet benzersiz olarak tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e3c1e-129">Biçimi olarak tanımlanan ' Web sitesi adı uygulamanın sanal yolu&#124;hizmet sanal yolu&#124;HizmetAdı '.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e3c1e-130">Örnek: ' Varsayılan Web sitesi/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e3c1e-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e3c1e-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e3c1e-132">AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.</span><span class="sxs-lookup"><span data-stu-id="e3c1e-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
