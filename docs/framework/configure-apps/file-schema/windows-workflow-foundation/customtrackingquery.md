---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 695fccf88ac0d8a672e710ccc632ea58dd2fc693
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398776"
---
# <a name="customtrackingquery"></a><span data-ttu-id="e21b7-101">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="e21b7-101">\<customTrackingQuery></span></span>
<span data-ttu-id="e21b7-102">Kod etkinliklerinizde tanımladığınız olayları izlemek için kullanılan bir sorgu koleksiyonunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="e21b7-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="e21b7-103">Sorgu, izleme katılımcısı için özel izleme kayıtlarına abone olmak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="e21b7-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="e21b7-104">Profil sorgularını izleme hakkında daha fazla bilgi için bkz. [Izleme profilleri](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e21b7-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e21b7-105">[ **\<Yapılandırma >** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e21b7-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e21b7-106">&nbsp;&nbsp;[ **\<sistemin. ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e21b7-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="e21b7-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<İzleme >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="e21b7-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="e21b7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="e21b7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="e21b7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<iş akışı >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e21b7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="e21b7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customTrackingQueries >** ](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="e21b7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="e21b7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customTrackingQuery >**</span><span class="sxs-lookup"><span data-stu-id="e21b7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e21b7-112">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e21b7-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e21b7-113">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="e21b7-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e21b7-114">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="e21b7-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e21b7-115">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="e21b7-115">Attributes</span></span>  
  
|<span data-ttu-id="e21b7-116">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="e21b7-116">Attribute</span></span>|<span data-ttu-id="e21b7-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e21b7-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e21b7-118">activityName</span><span class="sxs-lookup"><span data-stu-id="e21b7-118">activityName</span></span>|<span data-ttu-id="e21b7-119">İzleme kaydını oluşturan etkinliğin adını belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="e21b7-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="e21b7-120">name</span><span class="sxs-lookup"><span data-stu-id="e21b7-120">name</span></span>|<span data-ttu-id="e21b7-121">Yayılan özel izleme kaydının adını belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="e21b7-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e21b7-122">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="e21b7-122">Child Elements</span></span>  
 <span data-ttu-id="e21b7-123">Yok.</span><span class="sxs-lookup"><span data-stu-id="e21b7-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e21b7-124">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="e21b7-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e21b7-125">Öğe</span><span class="sxs-lookup"><span data-stu-id="e21b7-125">Element</span></span>|<span data-ttu-id="e21b7-126">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e21b7-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e21b7-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="e21b7-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="e21b7-128">Kod etkinliklerinizde tanımladığınız olayları izlemek için kullanılan bir sorgu.</span><span class="sxs-lookup"><span data-stu-id="e21b7-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e21b7-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e21b7-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e21b7-130">İş Akışı Takip ve İzleme</span><span class="sxs-lookup"><span data-stu-id="e21b7-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e21b7-131">İzleme Profilleri</span><span class="sxs-lookup"><span data-stu-id="e21b7-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
