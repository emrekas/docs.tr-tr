---
title: '&lt;backupList&gt; &lt;ekleme&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 2cc7cce62082317bb86218d68bd2881b74649771
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670192"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="56015-102">&lt;backupList&gt; &lt;ekleme&gt;</span><span class="sxs-lookup"><span data-stu-id="56015-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="56015-103">Bir yedekleme uç nokta öğesini tanımlayan bir yapılandırma öğesini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="56015-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="56015-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="56015-104">\<system.serviceModel></span></span>  
<span data-ttu-id="56015-105">\<Yönlendirme ></span><span class="sxs-lookup"><span data-stu-id="56015-105">\<routing></span></span>  
<span data-ttu-id="56015-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="56015-106">\<backupLists></span></span>  
<span data-ttu-id="56015-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="56015-107">\<backupList></span></span>  
<span data-ttu-id="56015-108">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="56015-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56015-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="56015-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56015-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="56015-110">Attributes and Elements</span></span>  
 <span data-ttu-id="56015-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="56015-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56015-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="56015-112">Attributes</span></span>  
  
|<span data-ttu-id="56015-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="56015-113">Attribute</span></span>|<span data-ttu-id="56015-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="56015-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56015-115">name</span><span class="sxs-lookup"><span data-stu-id="56015-115">name</span></span>|<span data-ttu-id="56015-116">Yedekleme uç noktası adını belirten dize.</span><span class="sxs-lookup"><span data-stu-id="56015-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56015-117">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="56015-117">Child Elements</span></span>  
 <span data-ttu-id="56015-118">Yok.</span><span class="sxs-lookup"><span data-stu-id="56015-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56015-119">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="56015-119">Parent Elements</span></span>  
  
|<span data-ttu-id="56015-120">Öğe</span><span class="sxs-lookup"><span data-stu-id="56015-120">Element</span></span>|<span data-ttu-id="56015-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="56015-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56015-122">\<Yönlendirme ></span><span class="sxs-lookup"><span data-stu-id="56015-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="56015-123">Birincil uç noktaya erişilemiyor durumunda kullanmak için yönlendirme hizmeti istediğiniz uç noktalarının bir listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="56015-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56015-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="56015-124">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
