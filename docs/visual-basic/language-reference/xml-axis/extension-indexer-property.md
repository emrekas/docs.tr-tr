---
title: Extension Indexer Özelliği (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: a02c482db81d9d76752cfe66a292dc57c48b2acb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698908"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="d4616-102">Extension Indexer Özelliği (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4616-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="d4616-103">Bir koleksiyondaki öğelere erişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="d4616-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4616-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d4616-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="d4616-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="d4616-105">Parts</span></span>  
  
|<span data-ttu-id="d4616-106">Terim</span><span class="sxs-lookup"><span data-stu-id="d4616-106">Term</span></span>|<span data-ttu-id="d4616-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="d4616-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="d4616-108">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="d4616-108">Required.</span></span> <span data-ttu-id="d4616-109">Sorgulanabilir bir koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="d4616-109">A queryable collection.</span></span> <span data-ttu-id="d4616-110">Diğer bir deyişle, uygulayan koleksiyondan <xref:System.Collections.Generic.IEnumerable%601> veya <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="d4616-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="d4616-111">(</span><span class="sxs-lookup"><span data-stu-id="d4616-111">(</span></span>|<span data-ttu-id="d4616-112">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="d4616-112">Required.</span></span> <span data-ttu-id="d4616-113">Dizin Oluşturucu özelliği başlangıcını gösterir.</span><span class="sxs-lookup"><span data-stu-id="d4616-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="d4616-114">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="d4616-114">Required.</span></span> <span data-ttu-id="d4616-115">Koleksiyonun bir öğesi sıfır tabanlı konumu belirten bir tamsayı ifade.</span><span class="sxs-lookup"><span data-stu-id="d4616-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="d4616-116">)</span><span class="sxs-lookup"><span data-stu-id="d4616-116">)</span></span>|<span data-ttu-id="d4616-117">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="d4616-117">Required.</span></span> <span data-ttu-id="d4616-118">Dizin Oluşturucu özelliği sonunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="d4616-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="d4616-119">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="d4616-119">Return Value</span></span>  
 <span data-ttu-id="d4616-120">Belirtilen konumda koleksiyon nesnesinden veya `Nothing` dizini aralık dışında ise.</span><span class="sxs-lookup"><span data-stu-id="d4616-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4616-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d4616-121">Remarks</span></span>  
 <span data-ttu-id="d4616-122">Extension Indexer özelliği, bir koleksiyondaki tek tek öğelere erişmek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d4616-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="d4616-123">Bu dizin oluşturucu özelliği, genellikle XML eksen özellikleri üzerinde çıkışını kullanılır.</span><span class="sxs-lookup"><span data-stu-id="d4616-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="d4616-124">XML descendent axis özellikleri ve XML alt koleksiyonları dönüş <xref:System.Xml.Linq.XElement> nesneler veya bir öznitelik değeri.</span><span class="sxs-lookup"><span data-stu-id="d4616-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="d4616-125">Visual Basic derleyici çağrıları uzantı dizin oluşturucu özellikleri dönüştürür `ElementAtOrDefault` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d4616-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="d4616-126">Bir dizi dizin oluşturucu aksine `ElementAtOrDefault` yöntemi döndürür `Nothing` dizini aralık dışında ise.</span><span class="sxs-lookup"><span data-stu-id="d4616-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="d4616-127">Bu davranış, bir koleksiyondaki öğe sayısını kolayca belirlenemiyor yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="d4616-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="d4616-128">Bu dizin oluşturucu özelliği, bir uzantı özelliği uygulayan koleksiyonlar için benzer <xref:System.Collections.Generic.IEnumerable%601> veya <xref:System.Linq.IQueryable%601>: yalnızca koleksiyon bir dizin oluşturucu veya varsayılan bir özellik yoksa, kullanılır.</span><span class="sxs-lookup"><span data-stu-id="d4616-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="d4616-129">Değerin bir koleksiyondaki ilk öğenin erişmek için <xref:System.Xml.Linq.XElement> veya <xref:System.Xml.Linq.XAttribute> nesneler, XML kullanabileceğiniz `Value` özelliği.</span><span class="sxs-lookup"><span data-stu-id="d4616-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="d4616-130">Daha fazla bilgi için [XML değeri özelliği](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="d4616-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4616-131">Örnek</span><span class="sxs-lookup"><span data-stu-id="d4616-131">Example</span></span>  
 <span data-ttu-id="d4616-132">Aşağıdaki örnek bir koleksiyonu ikinci alt düğümünde erişmek için uzantı dizin oluşturucu kullanmayı gösterir <xref:System.Xml.Linq.XElement> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="d4616-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="d4616-133">Koleksiyon adlı tüm alt öğe alır child axis özelliği kullanılarak erişilir `phone` içinde `contact` nesne.</span><span class="sxs-lookup"><span data-stu-id="d4616-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="d4616-134">Bu kod, aşağıdaki metni görüntüler:</span><span class="sxs-lookup"><span data-stu-id="d4616-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="d4616-135">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d4616-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="d4616-136">XML Eksen Özellikleri</span><span class="sxs-lookup"><span data-stu-id="d4616-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="d4616-137">XML Değişmez Değerleri</span><span class="sxs-lookup"><span data-stu-id="d4616-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="d4616-138">Visual Basic'de XML oluşturma</span><span class="sxs-lookup"><span data-stu-id="d4616-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="d4616-139">XML Value Özelliği</span><span class="sxs-lookup"><span data-stu-id="d4616-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
