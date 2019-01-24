---
title: '&lt;Yönlendirme&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 855faedfd2e9523e939174441b0cfa50e052b375
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565884"
---
# <a name="ltroutinggt"></a><span data-ttu-id="32fcf-102">&lt;Yönlendirme&gt;</span><span class="sxs-lookup"><span data-stu-id="32fcf-102">&lt;routing&gt;</span></span>

<span data-ttu-id="32fcf-103">Windows Communication Foundation (WCF) türünü belirleyen ve yönlendirme süzgeçleri kümesini tanımlamak için bir yapılandırma bölümünü temsil eder <xref:System.ServiceModel.Dispatcher.MessageFilter> yönlendirme yanı sıra gelen iletileri değerlendirmek için hedef bitiş noktalarını tanımlayan tabloları yapılırken kullanılacak ne zaman eşleşen bir filtre, iletileri gönderir.</span><span class="sxs-lookup"><span data-stu-id="32fcf-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="32fcf-104">[**\<system.serviceModel>**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="32fcf-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="32fcf-105">&nbsp;&nbsp;**\<Yönlendirme >**</span><span class="sxs-lookup"><span data-stu-id="32fcf-105">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="32fcf-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="32fcf-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String"
               filterName="String"
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32fcf-107">Öznitelikler ve öğeler</span><span class="sxs-lookup"><span data-stu-id="32fcf-107">Attributes and elements</span></span>

<span data-ttu-id="32fcf-108">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="32fcf-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="32fcf-109">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="32fcf-109">Attributes</span></span>

<span data-ttu-id="32fcf-110">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="32fcf-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="32fcf-111">Alt öğeleri</span><span class="sxs-lookup"><span data-stu-id="32fcf-111">Child elements</span></span>

|     | <span data-ttu-id="32fcf-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="32fcf-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="32fcf-113">**\<filtreleri >**</span><span class="sxs-lookup"><span data-stu-id="32fcf-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="32fcf-114">Windows Communication Foundation (WCF) MessageFilter türünü gelen iletileri değerlendirmek kullanılacağını belirlemek yönlendirme süzgeçleri kümesini içerir.</span><span class="sxs-lookup"><span data-stu-id="32fcf-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="32fcf-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="32fcf-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="32fcf-116">Filtreler eşleştiğinde kullanmak için hangi uç noktaya belirtmek için hedef uç noktalar ile yönlendirme filtreleri arasındaki eşlemeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="32fcf-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="32fcf-117">Üst öğeler</span><span class="sxs-lookup"><span data-stu-id="32fcf-117">Parent elements</span></span>

|     | <span data-ttu-id="32fcf-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="32fcf-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="32fcf-119">**\<sistemi. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="32fcf-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="32fcf-120">Tüm WCF yapılandırma öğelerinin kök öğe.</span><span class="sxs-lookup"><span data-stu-id="32fcf-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="32fcf-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="32fcf-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
