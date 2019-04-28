---
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: cf4a455d80a1a0ac09e99bad967c1feba3653842
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61596544"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="92ff7-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="92ff7-102">223 - OperationFaulted</span></span>
## <a name="properties"></a><span data-ttu-id="92ff7-103">Özellikler</span><span class="sxs-lookup"><span data-stu-id="92ff7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="92ff7-104">Kimlik</span><span class="sxs-lookup"><span data-stu-id="92ff7-104">ID</span></span>|<span data-ttu-id="92ff7-105">223</span><span class="sxs-lookup"><span data-stu-id="92ff7-105">223</span></span>|  
|<span data-ttu-id="92ff7-106">anahtar sözcükler</span><span class="sxs-lookup"><span data-stu-id="92ff7-106">Keywords</span></span>|<span data-ttu-id="92ff7-107">Sorun giderme, ServiceModel EndToEndMonitoring, ögesi,</span><span class="sxs-lookup"><span data-stu-id="92ff7-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="92ff7-108">Düzey</span><span class="sxs-lookup"><span data-stu-id="92ff7-108">Level</span></span>|<span data-ttu-id="92ff7-109">Uyarı</span><span class="sxs-lookup"><span data-stu-id="92ff7-109">Warning</span></span>|  
|<span data-ttu-id="92ff7-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="92ff7-110">Channel</span></span>|<span data-ttu-id="92ff7-111">Microsoft Windows uygulama sunucusu-uygulamalar/analitik</span><span class="sxs-lookup"><span data-stu-id="92ff7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="92ff7-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="92ff7-112">Description</span></span>  
 <span data-ttu-id="92ff7-113">Bu olay yayılan olduğunda hizmet modelinin varsayılan `OperationInvoker` türetilen bir özel durumla karşılaştı `FaultException` kendi metodu çağrılırken hata.</span><span class="sxs-lookup"><span data-stu-id="92ff7-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="92ff7-114">İleti</span><span class="sxs-lookup"><span data-stu-id="92ff7-114">Message</span></span>  
 <span data-ttu-id="92ff7-115">'%1' yöntemi tarafından OperationInvoker çağrıldığında bir FaultException oluşturdu.</span><span class="sxs-lookup"><span data-stu-id="92ff7-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="92ff7-116">Yöntem çağrısı süresi '%2' ms idi.</span><span class="sxs-lookup"><span data-stu-id="92ff7-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="92ff7-117">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="92ff7-117">Details</span></span>  
  
|<span data-ttu-id="92ff7-118">Veri öğesi adı</span><span class="sxs-lookup"><span data-stu-id="92ff7-118">Data Item Name</span></span>|<span data-ttu-id="92ff7-119">Veri öğesi türü</span><span class="sxs-lookup"><span data-stu-id="92ff7-119">Data Item Type</span></span>|<span data-ttu-id="92ff7-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="92ff7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="92ff7-121">methodName</span><span class="sxs-lookup"><span data-stu-id="92ff7-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="92ff7-122">CLR adı tarafından çağrılan yöntemin `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="92ff7-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="92ff7-123">Süresi</span><span class="sxs-lookup"><span data-stu-id="92ff7-123">Duration</span></span>|`xs:long`|<span data-ttu-id="92ff7-124">Geçen milisaniye cinsinden zaman `OperationInvoker` yöntemini çağırmak için.</span><span class="sxs-lookup"><span data-stu-id="92ff7-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="92ff7-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="92ff7-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="92ff7-126">Bu alan, Web barındırılan hizmetleri, Web hiyerarşideki hizmet benzersiz olarak tanımlar.</span><span class="sxs-lookup"><span data-stu-id="92ff7-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="92ff7-127">Biçimi olarak tanımlanan ' Web sitesi adı uygulamanın sanal yolu&#124;hizmet sanal yolu&#124;HizmetAdı '.</span><span class="sxs-lookup"><span data-stu-id="92ff7-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="92ff7-128">Örnek: ' Varsayılan Web sitesi/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="92ff7-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="92ff7-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="92ff7-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="92ff7-130">AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.</span><span class="sxs-lookup"><span data-stu-id="92ff7-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
