---
title: '&lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: c11fd38e7c40f740d4c1c36ab87c44744ed0daab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627998"
---
# <a name="ltbackuplistgt"></a><span data-ttu-id="18843-102">&lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="18843-102">&lt;backupList&gt;</span></span>
<span data-ttu-id="18843-103">Bir birincil uç noktaya erişilemiyor durumunda kullanmak için yönlendirme hizmeti istediğiniz uç nokta kümesine numaralandırır yedek listesini tanımlamak için bir yapılandırma bölümünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="18843-103">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="18843-104">Listedeki ilk uç kapalı ise, yönlendirme hizmeti otomatik olarak bir listesi için devredilmesini.</span><span class="sxs-lookup"><span data-stu-id="18843-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="18843-105">Bu istemci uygulamanıza karmaşık desenlerle nasıl ele alınacağını ya da tüm hizmetlerinizin dağıtıldığı öğretmek zorunda kalmadan uygulamanıza güvenilirlik eklemeniz için hızlı bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="18843-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="18843-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="18843-106">\<system.serviceModel></span></span>  
<span data-ttu-id="18843-107">\<Yönlendirme ></span><span class="sxs-lookup"><span data-stu-id="18843-107">\<routing></span></span>  
<span data-ttu-id="18843-108">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="18843-108">\<backupLists></span></span>  
<span data-ttu-id="18843-109">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="18843-109">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18843-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="18843-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18843-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="18843-111">Attributes and Elements</span></span>  
 <span data-ttu-id="18843-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="18843-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18843-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="18843-113">Attributes</span></span>  
  
|<span data-ttu-id="18843-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="18843-114">Attribute</span></span>|<span data-ttu-id="18843-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="18843-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18843-116">name</span><span class="sxs-lookup"><span data-stu-id="18843-116">name</span></span>|<span data-ttu-id="18843-117">Bu uç nokta listesini tanımlamak için kullanılan adı belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="18843-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18843-118">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="18843-118">Child Elements</span></span>  
  
|<span data-ttu-id="18843-119">Öğe</span><span class="sxs-lookup"><span data-stu-id="18843-119">Element</span></span>|<span data-ttu-id="18843-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="18843-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18843-121">\<Filtre ></span><span class="sxs-lookup"><span data-stu-id="18843-121">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="18843-122">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="18843-122">Parent Elements</span></span>  
  
|<span data-ttu-id="18843-123">Öğe</span><span class="sxs-lookup"><span data-stu-id="18843-123">Element</span></span>|<span data-ttu-id="18843-124">Açıklama</span><span class="sxs-lookup"><span data-stu-id="18843-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18843-125">\<Yönlendirme ></span><span class="sxs-lookup"><span data-stu-id="18843-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="18843-126">Yedekleme uç noktaları listesi.</span><span class="sxs-lookup"><span data-stu-id="18843-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18843-127">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="18843-127">Remarks</span></span>  
 <span data-ttu-id="18843-128">Bu bölümde, bir ileti için bir iletişim özel durumu olması durumunda birincil uç noktasına gönderilirken aktarılmaz uç noktaları sıralı bir koleksiyonunu içerir.</span><span class="sxs-lookup"><span data-stu-id="18843-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="18843-129">Birincil uç noktaya gönderme listelenen `endpointName` özniteliği [ \<Ekle >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) bir iletişim özel durumu ile başarısız oluyor, yönlendirme hizmeti ilk uç noktasına bu iletiyi göndermeyi deneyecek yapılandırma bölümü.</span><span class="sxs-lookup"><span data-stu-id="18843-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="18843-130">Bu da bir iletişim özel durumu ile başarısız olursa, yönlendirme hizmeti iletişim özel durumu veya tüm uç noktaların dışındaki bir hata gönderme girişimi başarılı olana kadar döndürür, bu bölümde yer alan sonraki iletiye ileti göndermeye çalışır koleksiyonu bir hata döndürdü.</span><span class="sxs-lookup"><span data-stu-id="18843-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="18843-131">Bir iletişim özel durumu "Hedef" adlı birincil uç noktaya gönderme döndürürse, aşağıdaki örnekte, "alternateServiceQueue" ileti göndermek hizmet dener.</span><span class="sxs-lookup"><span data-stu-id="18843-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="18843-132">Bu deneme bir iletişim özel durumu da döndürürse, yönlendirme hizmeti koleksiyonda sonraki uç nokta ileti göndermek dener.</span><span class="sxs-lookup"><span data-stu-id="18843-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a><span data-ttu-id="18843-133">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="18843-133">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
