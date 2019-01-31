---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: ad41c1afec0b46a404f8f24882587c1dfeb68a80
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267813"
---
# <a name="activitystatequeries"></a><span data-ttu-id="88c68-101">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="88c68-101">\<activityStateQueries></span></span>
<span data-ttu-id="88c68-102">Yaşam döngüsü değişiklikleri bir iş akışı örneği oluşturan etkinliklerinin izlemek için kullanılan sorguları koleksiyonunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="88c68-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="88c68-103">Örneğin, "E-posta Gönder" etkinlik içinde bir iş akışı örneği tamamlanan her zaman izlemek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="88c68-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="88c68-104">Bu sorgu, etkinlik durumu kayıt nesnelerine abone olmak izleme Katılımcısı için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="88c68-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="88c68-105">Abone olmak için kullanılabilir durumları ActivityStates belirtilir.</span><span class="sxs-lookup"><span data-stu-id="88c68-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="88c68-106">Profil sorguları izleme ile ilgili daha fazla bilgi için bkz: [izleme profilleri](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="88c68-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="88c68-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="88c68-107">\<system.serviceModel></span></span>  
<span data-ttu-id="88c68-108">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="88c68-108">\<tracking></span></span>  
<span data-ttu-id="88c68-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="88c68-109">\<trackingProfile></span></span>  
<span data-ttu-id="88c68-110">\<İş akışı ></span><span class="sxs-lookup"><span data-stu-id="88c68-110">\<workflow></span></span>  
<span data-ttu-id="88c68-111">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="88c68-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88c68-112">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="88c68-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88c68-113">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="88c68-113">Attributes and Elements</span></span>  
 <span data-ttu-id="88c68-114">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="88c68-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88c68-115">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="88c68-115">Attributes</span></span>  
 <span data-ttu-id="88c68-116">Yok.</span><span class="sxs-lookup"><span data-stu-id="88c68-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="88c68-117">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="88c68-117">Child Elements</span></span>  
  
|<span data-ttu-id="88c68-118">Öğe</span><span class="sxs-lookup"><span data-stu-id="88c68-118">Element</span></span>|<span data-ttu-id="88c68-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="88c68-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88c68-120">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="88c68-120">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="88c68-121">Bir etkinlik içinde oluşan hataların işlenmesi izlemek için kullanılan sorgu.</span><span class="sxs-lookup"><span data-stu-id="88c68-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="88c68-122">Bu olay bir FaultHandler bir hata her işlediğinde oluşur.</span><span class="sxs-lookup"><span data-stu-id="88c68-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88c68-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="88c68-123">Parent Elements</span></span>  
  
|<span data-ttu-id="88c68-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="88c68-124">Element</span></span>|<span data-ttu-id="88c68-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="88c68-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88c68-126">\<İş akışı ></span><span class="sxs-lookup"><span data-stu-id="88c68-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="88c68-127">Belirli bir iş akışı tarafından tanımlanan tüm sorgularında içeren bir yapılandırma öğesi **activityDefinitionId** özelliği.</span><span class="sxs-lookup"><span data-stu-id="88c68-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88c68-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="88c68-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="88c68-129">İş Akışı Takip ve İzleme</span><span class="sxs-lookup"><span data-stu-id="88c68-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="88c68-130">İzleme Profilleri</span><span class="sxs-lookup"><span data-stu-id="88c68-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
