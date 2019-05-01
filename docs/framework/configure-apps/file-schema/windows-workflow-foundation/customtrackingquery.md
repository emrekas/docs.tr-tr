---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 92060260075017359d8a5f0500d52e52c2217d3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790188"
---
# <a name="customtrackingquery"></a><span data-ttu-id="78756-101">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="78756-101">\<customTrackingQuery></span></span>
<span data-ttu-id="78756-102">Kod etkinlikleriniz tanımlayan olayları izlemek için kullanılan sorguları koleksiyonunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="78756-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="78756-103">Sorgu özel izleme kayıtları abone olmak izleme Katılımcısı için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="78756-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="78756-104">Profil sorguları izleme ile ilgili daha fazla bilgi için bkz: [profillerini izleme](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="78756-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="78756-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="78756-105">\<system.serviceModel></span></span>  
<span data-ttu-id="78756-106">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="78756-106">\<tracking></span></span>  
<span data-ttu-id="78756-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="78756-107">\<trackingProfile></span></span>  
<span data-ttu-id="78756-108">\<İş akışı ></span><span class="sxs-lookup"><span data-stu-id="78756-108">\<workflow></span></span>  
<span data-ttu-id="78756-109">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="78756-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="78756-110">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="78756-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78756-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="78756-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78756-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="78756-112">Attributes and Elements</span></span>  
 <span data-ttu-id="78756-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="78756-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78756-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="78756-114">Attributes</span></span>  
  
|<span data-ttu-id="78756-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="78756-115">Attribute</span></span>|<span data-ttu-id="78756-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="78756-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78756-117">activityName</span><span class="sxs-lookup"><span data-stu-id="78756-117">activityName</span></span>|<span data-ttu-id="78756-118">İzleme kayıt oluşturulan etkinliğin adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="78756-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="78756-119">name</span><span class="sxs-lookup"><span data-stu-id="78756-119">name</span></span>|<span data-ttu-id="78756-120">Yayılan özel izleme kayıt adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="78756-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78756-121">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="78756-121">Child Elements</span></span>  
 <span data-ttu-id="78756-122">Yok.</span><span class="sxs-lookup"><span data-stu-id="78756-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78756-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="78756-123">Parent Elements</span></span>  
  
|<span data-ttu-id="78756-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="78756-124">Element</span></span>|<span data-ttu-id="78756-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="78756-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78756-126">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="78756-126">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="78756-127">Kod etkinlikleriniz tanımlayan olayları izlemek için kullanılan sorgu.</span><span class="sxs-lookup"><span data-stu-id="78756-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78756-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="78756-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="78756-129">İş Akışı Takip ve İzleme</span><span class="sxs-lookup"><span data-stu-id="78756-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="78756-130">İzleme Profilleri</span><span class="sxs-lookup"><span data-stu-id="78756-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
