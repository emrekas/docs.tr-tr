---
title: Yayma
ms.date: 03/30/2017
ms.assetid: f8181e75-d693-48d1-b333-a776ad3b382a
ms.openlocfilehash: faa0e6ecb53963587e3fc253cd8beae1dc2c4bf5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154043"
---
# <a name="propagation"></a><span data-ttu-id="b03be-102">Yayma</span><span class="sxs-lookup"><span data-stu-id="b03be-102">Propagation</span></span>
<span data-ttu-id="b03be-103">Bu konu, Windows Communication Foundation (WCF) izleme modelinde Etkinlik yayma açıklar.</span><span class="sxs-lookup"><span data-stu-id="b03be-103">This topic describes activity propagation in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
## <a name="using-propagation-to-correlate-activities-across-endpoints"></a><span data-ttu-id="b03be-104">Uç noktalar genelinde etkinliklerini ilişkilendirmek için yayma kullanma</span><span class="sxs-lookup"><span data-stu-id="b03be-104">Using Propagation to Correlate Activities Across Endpoints</span></span>  
 <span data-ttu-id="b03be-105">Hata doğrudan bağıntı kullanıcıyla aynı işlem birimini için uygulama uç noktalar genelinde, örneğin, bir istek izler yayılmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="b03be-105">Propagation provides the user with direct correlation of error traces for the same unit of processing across application endpoints, for example, a request.</span></span> <span data-ttu-id="b03be-106">Farklı uç noktada aynı işlem birimini için yayılan hataları bile uygulama etki alanları arasında aynı etkinliğinde gruplandırılır.</span><span class="sxs-lookup"><span data-stu-id="b03be-106">Errors emitted at different endpoints for the same unit of processing are grouped in the same activity, even across application domains.</span></span> <span data-ttu-id="b03be-107">Bu, ileti üst bilgilerinde etkinlik kimliği yayma aracılığıyla gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="b03be-107">This is done through propagation of the activity ID in the message headers.</span></span> <span data-ttu-id="b03be-108">Bu nedenle, sunucu bir iç hata nedeniyle istemci zaman aşımına uğrarsa, her iki hata doğrudan bağıntı aynı etkinliği görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="b03be-108">Therefore, if a client times out because of an internal error in the server, both errors appear in the same activity for direct correlation.</span></span>  
  
 <span data-ttu-id="b03be-109">Bunu yapmak için `ActivityTracing` önceki örnekte gösterildiği gibi ayarlar.</span><span class="sxs-lookup"><span data-stu-id="b03be-109">To do this, use the `ActivityTracing` setting as demonstrated in the previous example.</span></span> <span data-ttu-id="b03be-110">Buna ek olarak, `propagateActivity` özniteliğini `System.ServiceModel` tüm uç noktaları, izleme kaynağı.</span><span class="sxs-lookup"><span data-stu-id="b03be-110">In addition, set the `propagateActivity` attribute for the `System.ServiceModel` trace source at all endpoints.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing" propagateActivity="true" >  
```  
  
 <span data-ttu-id="b03be-111">Etkinlik yayma TLS üzerinde etkinlik kimliği içeren giden iletiler için bir başlık eklemek WCF neden olan yapılandırılabilir bir özelliktir.</span><span class="sxs-lookup"><span data-stu-id="b03be-111">Activity propagation is a configurable capability that causes WCF to add a header to outbound messages, which includes the activity ID on the TLS.</span></span> <span data-ttu-id="b03be-112">Bu sunucu tarafında sonraki izlemeleri üzerinde dahil ederek, istemci ve sunucu etkinlikleri ilişkilendirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b03be-112">By including this on subsequent traces on the server side, we can correlate client and server activities.</span></span>  
  
## <a name="propagation-definition"></a><span data-ttu-id="b03be-113">Yayma tanımı</span><span class="sxs-lookup"><span data-stu-id="b03be-113">Propagation Definition</span></span>  
 <span data-ttu-id="b03be-114">Aşağıdaki koşulların tümü uygularsanız N etkinliği için etkinlik M'ın gAId yayılır.</span><span class="sxs-lookup"><span data-stu-id="b03be-114">Activity M’s gAId is propagated to activity N if all of the following conditions apply.</span></span>  
  
-   <span data-ttu-id="b03be-115">N, M nedeniyle oluşturulur</span><span class="sxs-lookup"><span data-stu-id="b03be-115">N is created because of M</span></span>  
  
-   <span data-ttu-id="b03be-116">N-M'ın gAId bilinir</span><span class="sxs-lookup"><span data-stu-id="b03be-116">M’s gAId is known to N</span></span>  
  
-   <span data-ttu-id="b03be-117">N'ın gAId M'ın gAId için eşittir.</span><span class="sxs-lookup"><span data-stu-id="b03be-117">N's gAId is equal to M’s gAId.</span></span>  
  
 <span data-ttu-id="b03be-118">Aşağıdaki XML şemada gösterildiği gibi gAId ActivityID ileti üst bilgisi dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="b03be-118">The gAId is propagated through the ActivityId message header, as illustrated in the following XML schema.</span></span>  
  
```xml  
<xsd:element name="ActivityId" type="integer" minOccurs="0">  
  <xsd:attribute name="CorrelationId" type="integer" minOccurs="0"/>  
</xsd:element>  
```  
  
 <span data-ttu-id="b03be-119">İleti üst bilgisi bir örnek verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="b03be-119">The following is an example of the message header.</span></span>  
  
```xml  
<MessageLogTraceRecord>  
  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope"
                      xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      <a:Action s:mustUnderstand="1">http://Microsoft.ServiceModel.Samples/ICalculator/Subtract  
      </a:Action>  
      <a:MessageID>urn:uuid:f0091eae-d339-4c7e-9408-ece34602f1ce  
      </a:MessageID>  
      <ActivityId CorrelationId="f94c6af1-7d5d-4295-b693-4670a8a0ce34"
               xmlns="http://schemas.microsoft.com/2004/09/ServiceModel/Diagnostics">  
        17f59a29-b435-4a15-bf7b-642ffc40eac8  
      </ActivityId>  
      <a:ReplyTo>  
          <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
      </a:ReplyTo>  
      <a:To s:mustUnderstand="1">net.tcp://localhost/servicemodelsamples/service</a:To>  
   </s:Header>  
   <s:Body>  
     <Subtract xmlns="http://Microsoft.ServiceModel.Samples">  
       <n1>145</n1>  
       <n2>76.54</n2>  
     </Subtract>  
   </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
## <a name="propagation-and-activity-boundaries"></a><span data-ttu-id="b03be-120">Doldurma ve etkinlik sınırları</span><span class="sxs-lookup"><span data-stu-id="b03be-120">Propagation and Activity Boundaries</span></span>  
 <span data-ttu-id="b03be-121">Etkinlik Kimliği uç noktalar genelinde yayıldığında, ileti alıcısı yayan bir başlatma ve durdurma izler, (yayılan) etkinlik kimliği ile</span><span class="sxs-lookup"><span data-stu-id="b03be-121">When the activity ID is propagated across endpoints, the message receiver emits a Start and Stop traces with that (propagated) activity ID.</span></span> <span data-ttu-id="b03be-122">Bu nedenle, her izleme kaynağından o gAId ile başlatma ve durdurma bir izleme yoktur.</span><span class="sxs-lookup"><span data-stu-id="b03be-122">Therefore, there is a Start and Stop trace with that gAId from each trace source.</span></span> <span data-ttu-id="b03be-123">Uç noktalar aynı işlem içinde ve izleme kaynak adının aynısını kullanın, birden fazla başlatma ve durdurma aynı düzenlenir (aynı gAId, aynı izleme kaynağı, aynı işlemde) ile oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="b03be-123">If the endpoints are in the same process and use the same trace source name, multiple Start and Stop with the same lAId (same gAId, same trace source, same process) are created.</span></span>  
  
## <a name="synchronization"></a><span data-ttu-id="b03be-124">Eşitleme</span><span class="sxs-lookup"><span data-stu-id="b03be-124">Synchronization</span></span>  
 <span data-ttu-id="b03be-125">Olaylar farklı makinelerde çalışan uç noktalar arasında eşitlemek için bir bağıntı kimliği iletilerinde yayılır ActivityID üst bilgi eklenir.</span><span class="sxs-lookup"><span data-stu-id="b03be-125">To synchronize events across endpoints that run on different machines, a CorrelationId is added to the ActivityId header that is propagated in messages.</span></span> <span data-ttu-id="b03be-126">Araçları olayları makineler arasında saat tutarsızlık ile eşitlemek için bu kodu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b03be-126">Tools can use this ID to synchronize events across machines with clock discrepancy.</span></span> <span data-ttu-id="b03be-127">Özellikle, hizmet izleme Görüntüleyicisi aracı, uç noktalar arasında ileti akışları göstermek için bu kimliği kullanır.</span><span class="sxs-lookup"><span data-stu-id="b03be-127">Specifically, the Service Trace Viewer tool uses this ID for showing message flows between endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03be-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b03be-128">See also</span></span>

- [<span data-ttu-id="b03be-129">İzlemeyi Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="b03be-129">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [<span data-ttu-id="b03be-130">İlişkilendirilmiş İzlemeleri Görüntülemek ve Sorun Gidermek için Hizmet İzleme Görüntüleyicisini Kullanma</span><span class="sxs-lookup"><span data-stu-id="b03be-130">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="b03be-131">Uçtan Uca İzleme Senaryoları</span><span class="sxs-lookup"><span data-stu-id="b03be-131">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="b03be-132">Hizmet İzleme Görüntüleyicisi Aracı (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="b03be-132">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
