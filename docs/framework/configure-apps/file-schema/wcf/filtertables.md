---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c49c7cf3a196595556c2bf1b4ed4365bfe1e4cbf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075736"
---
# <a name="filtertables"></a><span data-ttu-id="b8431-101">\<filterTables ></span><span class="sxs-lookup"><span data-stu-id="b8431-101">\<filterTables></span></span>
<span data-ttu-id="b8431-102">Filtreler eşleştiğinde ileti göndermek için hedef uç noktalar ile yönlendirme filtreleri arasındaki eşlemeleri içeren yönlendirme tablosunun tanımı için bir yapılandırma bölümünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="b8431-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="b8431-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b8431-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b8431-104">\<Yönlendirme ></span><span class="sxs-lookup"><span data-stu-id="b8431-104">\<routing></span></span>  
<span data-ttu-id="b8431-105">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="b8431-105">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8431-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b8431-106">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8431-107">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="b8431-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b8431-108">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="b8431-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8431-109">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="b8431-109">Attributes</span></span>  
 <span data-ttu-id="b8431-110">Yok.</span><span class="sxs-lookup"><span data-stu-id="b8431-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8431-111">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="b8431-111">Child Elements</span></span>  
  
|<span data-ttu-id="b8431-112">Öğe</span><span class="sxs-lookup"><span data-stu-id="b8431-112">Element</span></span>|<span data-ttu-id="b8431-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b8431-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8431-114">\<filtreleri ></span><span class="sxs-lookup"><span data-stu-id="b8431-114">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="b8431-115">Bir yönlendirme tablosu, ne zaman eşleşen filtre ileti göndermek için hedef uç noktalar ile yönlendirme filtreleri arasındaki eşlemeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="b8431-115">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8431-116">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="b8431-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b8431-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="b8431-117">Element</span></span>|<span data-ttu-id="b8431-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b8431-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8431-119">\<Yönlendirme ></span><span class="sxs-lookup"><span data-stu-id="b8431-119">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="b8431-120">Yönlendirme filtreleri ve yönlendirme tablolarını içeren bir yapılandırma bölümü.</span><span class="sxs-lookup"><span data-stu-id="b8431-120">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8431-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b8431-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
