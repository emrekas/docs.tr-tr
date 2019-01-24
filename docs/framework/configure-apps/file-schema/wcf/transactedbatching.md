---
title: '&lt;transactedBatching&gt;'
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 2f89a1a6c2cc110a4695b792c5aa801b516393be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566001"
---
# <a name="lttransactedbatchinggt"></a><span data-ttu-id="09e5c-102">&lt;transactedBatching&gt;</span><span class="sxs-lookup"><span data-stu-id="09e5c-102">&lt;transactedBatching&gt;</span></span>
<span data-ttu-id="09e5c-103">Hareket işlem grubu oluşturma için desteklenip desteklenmediğini belirtir alma işlemleri.</span><span class="sxs-lookup"><span data-stu-id="09e5c-103">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="09e5c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="09e5c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="09e5c-105">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="09e5c-105">\<behaviors></span></span>  
<span data-ttu-id="09e5c-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="09e5c-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="09e5c-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="09e5c-107">\<behavior></span></span>  
<span data-ttu-id="09e5c-108">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="09e5c-108">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e5c-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="09e5c-109">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09e5c-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="09e5c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="09e5c-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="09e5c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09e5c-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="09e5c-112">Attributes</span></span>  
  
|<span data-ttu-id="09e5c-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="09e5c-113">Attribute</span></span>|<span data-ttu-id="09e5c-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="09e5c-114">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="09e5c-115">En fazla sayısını belirten bir tamsayı gruplanabilecek operations birlikte tek bir işlemle alırsınız.</span><span class="sxs-lookup"><span data-stu-id="09e5c-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="09e5c-116">Varsayılan değer 0'dır.</span><span class="sxs-lookup"><span data-stu-id="09e5c-116">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09e5c-117">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="09e5c-117">Child Elements</span></span>  
 <span data-ttu-id="09e5c-118">Yok.</span><span class="sxs-lookup"><span data-stu-id="09e5c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09e5c-119">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="09e5c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="09e5c-120">Öğe</span><span class="sxs-lookup"><span data-stu-id="09e5c-120">Element</span></span>|<span data-ttu-id="09e5c-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="09e5c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09e5c-122">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="09e5c-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="09e5c-123">Bir uç nokta davranışı belirtir.</span><span class="sxs-lookup"><span data-stu-id="09e5c-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09e5c-124">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="09e5c-124">Remarks</span></span>  
 <span data-ttu-id="09e5c-125">Birkaç batch girişimleri toplu işlem ile yapılandırılmış bir taşıma işlemlerini tek bir işleme alırsınız.</span><span class="sxs-lookup"><span data-stu-id="09e5c-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="09e5c-126">Bunu, bir işlem oluşturmak ve bunu yapmadan görece yüksek maliyeti yaparak her alma işlemi engellenir.</span><span class="sxs-lookup"><span data-stu-id="09e5c-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09e5c-127">Örnek</span><span class="sxs-lookup"><span data-stu-id="09e5c-127">Example</span></span>  
 <span data-ttu-id="09e5c-128">Aşağıdaki örnek, bir hizmet yapılandırma dosyasında işlenen toplu işleme davranışını eklemek gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="09e5c-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />
      <!-- the mex endpoint is explosed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <behaviors>
    <endpointBehaviors>
      <behavior name="endpointBehavior">
        <transactedBatching maxBatchSize="10" />
      </behavior>
    </endpointBehaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="true" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="09e5c-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="09e5c-129">See also</span></span>
- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
