---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 28d19742055c51ca94c36ffddf15dced7dfc14cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924442"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="780f5-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="780f5-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="780f5-103">Özellikler</span><span class="sxs-lookup"><span data-stu-id="780f5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="780f5-104">Kimlik</span><span class="sxs-lookup"><span data-stu-id="780f5-104">ID</span></span>|<span data-ttu-id="780f5-105">1019</span><span class="sxs-lookup"><span data-stu-id="780f5-105">1019</span></span>|  
|<span data-ttu-id="780f5-106">anahtar sözcükler</span><span class="sxs-lookup"><span data-stu-id="780f5-106">Keywords</span></span>|<span data-ttu-id="780f5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="780f5-107">WFRuntime</span></span>|  
|<span data-ttu-id="780f5-108">Düzey</span><span class="sxs-lookup"><span data-stu-id="780f5-108">Level</span></span>|<span data-ttu-id="780f5-109">Ayrıntılı</span><span class="sxs-lookup"><span data-stu-id="780f5-109">Verbose</span></span>|  
|<span data-ttu-id="780f5-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="780f5-110">Channel</span></span>|<span data-ttu-id="780f5-111">Microsoft Windows uygulaması sunucu-uygulamalar/hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="780f5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="780f5-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="780f5-112">Description</span></span>  
 <span data-ttu-id="780f5-113">Bir CancelActivityWorkItem tamamlandığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="780f5-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="780f5-114">İleti</span><span class="sxs-lookup"><span data-stu-id="780f5-114">Message</span></span>  
 <span data-ttu-id="780f5-115">'%1', DisplayName etkinliği için bir CancelActivityWorkItem tamamlandı: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="780f5-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="780f5-116">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="780f5-116">Details</span></span>  
  
|<span data-ttu-id="780f5-117">Veri öğesi adı</span><span class="sxs-lookup"><span data-stu-id="780f5-117">Data Item Name</span></span>|<span data-ttu-id="780f5-118">Veri öğesi türü</span><span class="sxs-lookup"><span data-stu-id="780f5-118">Data Item Type</span></span>|<span data-ttu-id="780f5-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="780f5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="780f5-120">Etkinlik</span><span class="sxs-lookup"><span data-stu-id="780f5-120">Activity</span></span>|<span data-ttu-id="780f5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="780f5-121">xs:string</span></span>|<span data-ttu-id="780f5-122">Etkinlik türü adı.</span><span class="sxs-lookup"><span data-stu-id="780f5-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="780f5-123">displayName</span><span class="sxs-lookup"><span data-stu-id="780f5-123">DisplayName</span></span>|<span data-ttu-id="780f5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="780f5-124">xs:string</span></span>|<span data-ttu-id="780f5-125">Etkinliğin görünen adı.</span><span class="sxs-lookup"><span data-stu-id="780f5-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="780f5-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="780f5-126">InstanceId</span></span>|<span data-ttu-id="780f5-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="780f5-127">xs:string</span></span>|<span data-ttu-id="780f5-128">Etkinlik örneği kimliği.</span><span class="sxs-lookup"><span data-stu-id="780f5-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="780f5-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="780f5-129">AppDomain</span></span>|<span data-ttu-id="780f5-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="780f5-130">xs:string</span></span>|<span data-ttu-id="780f5-131">AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.</span><span class="sxs-lookup"><span data-stu-id="780f5-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
