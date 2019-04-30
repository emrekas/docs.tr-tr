---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c49c7cf3a196595556c2bf1b4ed4365bfe1e4cbf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704251"
---
# <a name="filtertables"></a><span data-ttu-id="0b6af-101">\<filterTables ></span><span class="sxs-lookup"><span data-stu-id="0b6af-101">\<filterTables></span></span>
<span data-ttu-id="0b6af-102">Filtreler eşleştiğinde ileti göndermek için hedef uç noktalar ile yönlendirme filtreleri arasındaki eşlemeleri içeren yönlendirme tablosunun tanımı için bir yapılandırma bölümünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="0b6af-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="0b6af-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0b6af-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0b6af-104">\<Yönlendirme ></span><span class="sxs-lookup"><span data-stu-id="0b6af-104">\<routing></span></span>  
<span data-ttu-id="0b6af-105">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="0b6af-105">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b6af-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0b6af-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b6af-107">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="0b6af-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0b6af-108">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0b6af-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b6af-109">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="0b6af-109">Attributes</span></span>  
 <span data-ttu-id="0b6af-110">Yok.</span><span class="sxs-lookup"><span data-stu-id="0b6af-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0b6af-111">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="0b6af-111">Child Elements</span></span>  
  
|<span data-ttu-id="0b6af-112">Öğe</span><span class="sxs-lookup"><span data-stu-id="0b6af-112">Element</span></span>|<span data-ttu-id="0b6af-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0b6af-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b6af-114">\<filtreleri ></span><span class="sxs-lookup"><span data-stu-id="0b6af-114">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="0b6af-115">Bir yönlendirme tablosu, ne zaman eşleşen filtre ileti göndermek için hedef uç noktalar ile yönlendirme filtreleri arasındaki eşlemeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="0b6af-115">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b6af-116">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="0b6af-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0b6af-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="0b6af-117">Element</span></span>|<span data-ttu-id="0b6af-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0b6af-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b6af-119">\<Yönlendirme ></span><span class="sxs-lookup"><span data-stu-id="0b6af-119">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="0b6af-120">Yönlendirme filtreleri ve yönlendirme tablolarını içeren bir yapılandırma bölümü.</span><span class="sxs-lookup"><span data-stu-id="0b6af-120">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b6af-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0b6af-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
