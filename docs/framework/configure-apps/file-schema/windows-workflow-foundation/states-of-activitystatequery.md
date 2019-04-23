---
title: <states> / <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: fa3736fc13f6f40f52d15b8257b7a79f4179d738
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189605"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="87701-102">\<durumları >, \<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="87701-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="87701-103">Kendisi için bir izleme kaydını yayılan abone olunan etkinliğin durumları içeren yapılandırma öğelerinin koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="87701-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="87701-104">Profil sorguları izleme ile ilgili daha fazla bilgi için bkz: [izleme profilleri](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="87701-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="87701-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="87701-105">\<system.serviceModel></span></span>  
<span data-ttu-id="87701-106">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="87701-106">\<tracking></span></span>  
<span data-ttu-id="87701-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="87701-107">\<trackingProfile></span></span>  
<span data-ttu-id="87701-108">\<İş akışı ></span><span class="sxs-lookup"><span data-stu-id="87701-108">\<workflow></span></span>  
<span data-ttu-id="87701-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="87701-109">\<activityStateQueries></span></span>  
<span data-ttu-id="87701-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="87701-110">\<activityStateQuery></span></span>  
<span data-ttu-id="87701-111">\<durumları ></span><span class="sxs-lookup"><span data-stu-id="87701-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87701-112">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="87701-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87701-113">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="87701-113">Attributes and Elements</span></span>  
 <span data-ttu-id="87701-114">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="87701-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87701-115">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="87701-115">Attributes</span></span>  
 <span data-ttu-id="87701-116">Yok.</span><span class="sxs-lookup"><span data-stu-id="87701-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="87701-117">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="87701-117">Child Elements</span></span>  
  
|<span data-ttu-id="87701-118">Öğe</span><span class="sxs-lookup"><span data-stu-id="87701-118">Element</span></span>|<span data-ttu-id="87701-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="87701-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87701-120">\<Durum ></span><span class="sxs-lookup"><span data-stu-id="87701-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="87701-121">Kendisi için bir izleme kaydını yayılan abone olunan etkinliğin durumları içeren bir yapılandırma öğesi.</span><span class="sxs-lookup"><span data-stu-id="87701-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87701-122">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="87701-122">Parent Elements</span></span>  
  
|<span data-ttu-id="87701-123">Öğe</span><span class="sxs-lookup"><span data-stu-id="87701-123">Element</span></span>|<span data-ttu-id="87701-124">Açıklama</span><span class="sxs-lookup"><span data-stu-id="87701-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87701-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="87701-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="87701-126">Bir alt etkinlik üst etkinliği tarafından iptal etmek için istekleri izlemek için kullanılan bir yapılandırma öğesini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="87701-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="87701-127">Sorgu istek kayıt nesneleri iptal etmek için abone olmak izleme Katılımcısı için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="87701-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87701-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="87701-128">Remarks</span></span>  
 <span data-ttu-id="87701-129">Bir benzersiz bir ActivityStateQuery bir iş akışı yürütülmesini izlerken veri çıkarma özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="87701-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="87701-130">İzleme erişme post düzenlediğinizde bu yürütme ek bağlam sağlar.</span><span class="sxs-lookup"><span data-stu-id="87701-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="87701-131">Kullanabileceğiniz [ \<bağımsız değişkenleri >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<durumları >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) ve [ \<durumları >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) öğeleri herhangi bir değişken veya bağımsız değişken ayıklamak için bir iş akışındaki herhangi bir etkinlikten.</span><span class="sxs-lookup"><span data-stu-id="87701-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="87701-132">Aşağıdaki örnek, değişkenler ve bağımsız değişkenler ayıklar bir etkinlik durumu sorgusu gösterir, etkinliğin `Closed` izleme kaydını yayılan.</span><span class="sxs-lookup"><span data-stu-id="87701-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="87701-133">Değişkenler ve bağımsız değişkenler yalnızca bir ActivityStateRecord ile ayıklanabileceği ve bu nedenle içinde bir izleme abone olduğunuz kullanarak profil [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="87701-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87701-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="87701-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="87701-135">İş Akışı Takip ve İzleme</span><span class="sxs-lookup"><span data-stu-id="87701-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="87701-136">İzleme Profilleri</span><span class="sxs-lookup"><span data-stu-id="87701-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
