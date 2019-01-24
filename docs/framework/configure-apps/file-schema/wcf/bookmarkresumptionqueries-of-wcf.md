---
title: WCF &lt;bookmarkResumptionQueries&gt;
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 80d1c1e4bc61972d44c27bcbdd0eba14d97c2d6c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493956"
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="07ac2-102">WCF &lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="07ac2-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
  
<span data-ttu-id="07ac2-103">İş akışı örneği içinde yer işaretinin sürdürme izlemek için kullanılan sorguları koleksiyonunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="07ac2-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="07ac2-104">Sorgu için yer imi sürdürme kayıtları abone olmak izleme Katılımcısı için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="07ac2-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="07ac2-105">Profil sorguları izleme ile ilgili daha fazla bilgi için bkz: [izleme profilleri](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="07ac2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="07ac2-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="07ac2-106">\<system.serviceModel></span></span>  
<span data-ttu-id="07ac2-107">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="07ac2-107">\<tracking></span></span>  
<span data-ttu-id="07ac2-108">\<profilleri ></span><span class="sxs-lookup"><span data-stu-id="07ac2-108">\<profiles></span></span>  
<span data-ttu-id="07ac2-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="07ac2-109">\<trackingProfile></span></span>  
<span data-ttu-id="07ac2-110">\<İş akışı ></span><span class="sxs-lookup"><span data-stu-id="07ac2-110">\<workflow></span></span>  
<span data-ttu-id="07ac2-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="07ac2-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="07ac2-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="07ac2-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ac2-113">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="07ac2-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07ac2-114">Öznitelikler ve öğeler</span><span class="sxs-lookup"><span data-stu-id="07ac2-114">Attributes and elements</span></span>  
  
<span data-ttu-id="07ac2-115">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="07ac2-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07ac2-116">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="07ac2-116">Attributes</span></span>  
  
<span data-ttu-id="07ac2-117">Yok.</span><span class="sxs-lookup"><span data-stu-id="07ac2-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07ac2-118">Alt öğeleri</span><span class="sxs-lookup"><span data-stu-id="07ac2-118">Child elements</span></span>  
  
|<span data-ttu-id="07ac2-119">Öğe</span><span class="sxs-lookup"><span data-stu-id="07ac2-119">Element</span></span>|<span data-ttu-id="07ac2-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="07ac2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07ac2-121">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="07ac2-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="07ac2-122">İş akışı örneği içinde yer işaretinin sürdürme izlemek için kullanılan sorgu.</span><span class="sxs-lookup"><span data-stu-id="07ac2-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="07ac2-123">Sorgu için yer imi sürdürme kayıtları abone olmak izleme Katılımcısı için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="07ac2-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07ac2-124">Üst öğeler</span><span class="sxs-lookup"><span data-stu-id="07ac2-124">Parent elements</span></span>  
  
|<span data-ttu-id="07ac2-125">Öğe</span><span class="sxs-lookup"><span data-stu-id="07ac2-125">Element</span></span>|<span data-ttu-id="07ac2-126">Açıklama</span><span class="sxs-lookup"><span data-stu-id="07ac2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07ac2-127">\<İş akışı ></span><span class="sxs-lookup"><span data-stu-id="07ac2-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="07ac2-128">Belirli bir iş akışı tarafından tanımlanan tüm sorgularında içeren bir yapılandırma öğesi `activityDefinitionId` özelliği.</span><span class="sxs-lookup"><span data-stu-id="07ac2-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07ac2-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="07ac2-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="07ac2-130">İş Akışı Takip ve İzleme</span><span class="sxs-lookup"><span data-stu-id="07ac2-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="07ac2-131">İzleme Profilleri</span><span class="sxs-lookup"><span data-stu-id="07ac2-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
