---
title: Yeni Öğe Başvuruları Oluşturma
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67fdbcdbff64bcd91c80fbeaec0c41982b68d98f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934515"
---
# <a name="creating-new-entity-references"></a><span data-ttu-id="09878-102">Yeni Öğe Başvuruları Oluşturma</span><span class="sxs-lookup"><span data-stu-id="09878-102">Creating New Entity References</span></span>
<span data-ttu-id="09878-103">**CreateEntityReference** yöntemi yeni bir oluşturur **XmlEntityReference** düğümü.</span><span class="sxs-lookup"><span data-stu-id="09878-103">The **CreateEntityReference** method creates a new **XmlEntityReference** node.</span></span> <span data-ttu-id="09878-104">Başvurulan varlık adı zaten bildirildi, XML belge nesne modeli (DOM) bakar.</span><span class="sxs-lookup"><span data-stu-id="09878-104">The XML Document Object Model (DOM) looks to see if the entity name being referenced has already been declared.</span></span> <span data-ttu-id="09878-105">Varsa, alt düğümleri **XmlEntityReference** düğüm varlık bildirimi düğümden kopyalanır.</span><span class="sxs-lookup"><span data-stu-id="09878-105">If it has, the child nodes of **XmlEntityReference** node are copied from the entity declaration node.</span></span> <span data-ttu-id="09878-106">Eşleşen hiçbir varlık bildirimi varsa, bir boş metin düğümü tek varlık referans düğümün alt öğesi eklenir.</span><span class="sxs-lookup"><span data-stu-id="09878-106">If there is no entity declaration that matches, an empty text node is attached as the only child of the entity reference node.</span></span> <span data-ttu-id="09878-107">Çünkü alt düğümlerin **XmlEntityReference** düğümü diğer düğümlere kopyalarını, bu alt düğümlerin salt okunurdur ve değiştirilemez.</span><span class="sxs-lookup"><span data-stu-id="09878-107">Because the child nodes of the **XmlEntityReference** node are copies of other nodes, these child nodes are read-only and cannot be modified.</span></span>  
  
 <span data-ttu-id="09878-108">Düğümleri kopyalandığında olabilir bir ad alanı kapsamında noktasında varlık başvurusu.</span><span class="sxs-lookup"><span data-stu-id="09878-108">When the nodes are copied, there may be a namespace in scope at the point of the entity reference.</span></span> <span data-ttu-id="09878-109">Bu ad alanı yapılandırmasını oluşturulan herhangi bir öğe veya öznitelik düğümleri etkiler.</span><span class="sxs-lookup"><span data-stu-id="09878-109">This namespace affects the configuration of any element or attribute nodes generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09878-110">DOM alt düğüm ekler **EntityReference** eklediğinizde yalnızca **EntityReference** belge düğümü.</span><span class="sxs-lookup"><span data-stu-id="09878-110">The DOM adds child nodes to the **EntityReference** only when you insert the **EntityReference** node to the document.</span></span> <span data-ttu-id="09878-111">Yeni oluşturulan **EntityReference** düğümünüz alt düğüm yok.</span><span class="sxs-lookup"><span data-stu-id="09878-111">Newly created **EntityReference** nodes have no child nodes.</span></span>  
  
 <span data-ttu-id="09878-112">Olsa da **XmlDataDocument** türetilmiş bir sınıf **XmlDocument**, **XmlDataDocument** varlık başvuruları oluşturulmasını desteklemiyor.</span><span class="sxs-lookup"><span data-stu-id="09878-112">Even though the **XmlDataDocument** is a derived class of the **XmlDocument**, the **XmlDataDocument** does not support the creation of entity references.</span></span> <span data-ttu-id="09878-113">Bunun nedeni, **EntityReference** alt öğesi olan salt okunur.</span><span class="sxs-lookup"><span data-stu-id="09878-113">This is because **EntityReference** children are read-only.</span></span> <span data-ttu-id="09878-114">Alt bir **EntityReference** düğüm, birden fazla bölgeye yayılabilir.</span><span class="sxs-lookup"><span data-stu-id="09878-114">The children of an **EntityReference** node can span more than one region.</span></span> <span data-ttu-id="09878-115">Bu durumda, bir satırın bir parçası bir bölümünü içeren bir bölge ile ilişkili bir **EntityReference** salt okunur olacaktır.</span><span class="sxs-lookup"><span data-stu-id="09878-115">In this case, part of a row associated with the region that contains a part of an **EntityReference** will be read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09878-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="09878-116">See also</span></span>

- [<span data-ttu-id="09878-117">XML Belge Nesne Modeli (DOM)</span><span class="sxs-lookup"><span data-stu-id="09878-117">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
