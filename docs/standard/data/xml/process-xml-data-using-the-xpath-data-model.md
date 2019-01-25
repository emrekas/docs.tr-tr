---
title: XPath veri modelini kullanarak XML verilerini işleme
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 536c6fce-1453-4654-9c72-bca54d47e081
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67fbacd24b888b9c45072bcb34031f38adc118e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728404"
---
# <a name="process-xml-data-using-the-xpath-data-model"></a><span data-ttu-id="458de-102">XPath veri modelini kullanarak XML verilerini işleme</span><span class="sxs-lookup"><span data-stu-id="458de-102">Process XML Data Using the XPath Data Model</span></span>
<span data-ttu-id="458de-103"><xref:System.Xml?displayProperty=nameWithType> Ad alanı XML belgeleri, parçalar, düğüm veya düğüm kümeleri bellek içi, programlı bir gösterimini sağlar kullanarak <xref:System.Xml.XmlDocument> veya <xref:System.Xml.XPath.XPathDocument> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="458de-103">The <xref:System.Xml?displayProperty=nameWithType> namespace provides a programmatic representation of XML documents, fragments, nodes, or node-sets in-memory, using the <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> classes.</span></span>  
  
 <span data-ttu-id="458de-104"><xref:System.Xml.XPath.XPathDocument> Sınıfı XPath veri modelini kullanarak bir XML belgesi hızlı, salt okunur, bellek içi bir gösterimini sağlar.</span><span class="sxs-lookup"><span data-stu-id="458de-104">The <xref:System.Xml.XPath.XPathDocument> class provides a fast, read-only, in-memory representation of an XML document using the XPath data model.</span></span> <span data-ttu-id="458de-105"><xref:System.Xml.XmlDocument> Sınıf uygulama W3C belge nesne modeli (DOM) Düzey 1 çekirdek ve çekirdek DOM düzeyi 2 olan bir XML belgesi düzenlenebilir bir bellek içi gösterimini sağlar.</span><span class="sxs-lookup"><span data-stu-id="458de-105">The <xref:System.Xml.XmlDocument> class provides an editable in-memory representation of an XML document implementing W3C Document Object Model (DOM) Level 1 Core and Core DOM Level 2.</span></span> <span data-ttu-id="458de-106">Her iki sınıfları uygulayan <xref:System.Xml.XPath.IXPathNavigable> arabirim ve dönüş bir <xref:System.Xml.XPath.XPathNavigator> seçin, değerlendirmek, gidin ve bazı durumlarda, temel alınan XML verileri düzenlemek için kullanılan nesne.</span><span class="sxs-lookup"><span data-stu-id="458de-106">Both classes implement the <xref:System.Xml.XPath.IXPathNavigable> interface and return an <xref:System.Xml.XPath.XPathNavigator> object used to select, evaluate, navigate, and in some cases, edit the underlying XML data.</span></span>  
  
 <span data-ttu-id="458de-107">Aşağıdaki bölümlerde işlevselliğini <xref:System.Xml.XPath.XPathNavigator> sınıf tabanlı döndürdüğü sınıfta.</span><span class="sxs-lookup"><span data-stu-id="458de-107">The following sections describe the functionality of the <xref:System.Xml.XPath.XPathNavigator> class based on the class that returns it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="458de-108">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="458de-108">In This Section</span></span>  
 [<span data-ttu-id="458de-109">XPathDocument ve XmlDocument Kullanarak XML Verilerini Okuma</span><span class="sxs-lookup"><span data-stu-id="458de-109">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 <span data-ttu-id="458de-110">Salt okunur oluşturmayı açıklar <xref:System.Xml.XPath.XPathDocument> bir XML belgesi ve düzenlenebilir bir oluşturma okumak için sınıf nesnesi <xref:System.Xml.XmlDocument> okuyun ve bir XML belgesi düzenlemek için sınıf nesnesi.</span><span class="sxs-lookup"><span data-stu-id="458de-110">Describes how to create a read-only <xref:System.Xml.XPath.XPathDocument> class object to read an XML document and how to create an editable <xref:System.Xml.XmlDocument> class object to read and edit an XML document.</span></span> <span data-ttu-id="458de-111">Bu konu açıklar nasıl dönüş bir <xref:System.Xml.XPath.XPathNavigator> gidin ve bir XML belgesi düzenlemek için her bir sınıftan nesne.</span><span class="sxs-lookup"><span data-stu-id="458de-111">This topic also describes how return an <xref:System.Xml.XPath.XPathNavigator> object from each class to navigate and edit an XML document.</span></span>  
  
 [<span data-ttu-id="458de-112">XPathNavigator Kullanarak XML Verileri Seçme, Değerlendirme ve Eşleştirme</span><span class="sxs-lookup"><span data-stu-id="458de-112">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="458de-113">Yöntemlerini açıklar <xref:System.Xml.XPath.XPathNavigator> düğümleri seçmek için kullanılan sınıf bir <xref:System.Xml.XPath.XPathDocument> veya <xref:System.Xml.XmlDocument> bir XPath sorgusu kullanarak nesne, değerlendirmek ve bir XPath ifadesi sonuçları inceleyin ve bir XML belgesindeki düğüm, belirli bir XPath eşleşip eşleşmediğini belirler ifade.</span><span class="sxs-lookup"><span data-stu-id="458de-113">Describes the methods of the <xref:System.Xml.XPath.XPathNavigator> class used to select nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath query, evaluate and examine the results of an XPath expression, and determine if a node in an XML document matches a given XPath expression.</span></span>  
  
 [<span data-ttu-id="458de-114">XPathNavigator Kullanarak XML Verilerine Erişme</span><span class="sxs-lookup"><span data-stu-id="458de-114">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="458de-115">Yöntemlerini açıklar <xref:System.Xml.XPath.XPathNavigator> düğümleri gidin, XML verileri ayıklamak ve kesin türü belirtilmiş XML verilerine erişmek için kullanılan sınıf bir <xref:System.Xml.XPath.XPathDocument> veya <xref:System.Xml.XmlDocument> nesne.</span><span class="sxs-lookup"><span data-stu-id="458de-115">Describes the methods of the <xref:System.Xml.XPath.XPathNavigator> class used to navigate nodes, extract XML data and access strongly typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="458de-116">XPathNavigator Kullanarak XML Verilerini Düzenleme</span><span class="sxs-lookup"><span data-stu-id="458de-116">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="458de-117">Yöntemlerini açıklar <xref:System.Xml.XPath.XPathNavigator> eklemek, değiştirmek ve bir XML belgesi içindeki düğümleri ve değerleri kaldırmak için kullanılan sınıf bir <xref:System.Xml.XmlDocument> nesne.</span><span class="sxs-lookup"><span data-stu-id="458de-117">Describes the methods of the <xref:System.Xml.XPath.XPathNavigator> class used to insert, modify and remove nodes and values from an XML document contained in an <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="458de-118">XPathNavigator Kullanarak Şema Doğrulama</span><span class="sxs-lookup"><span data-stu-id="458de-118">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 <span data-ttu-id="458de-119">İçindeki XML içeriği doğrulama yöntemlerini açıklar bir <xref:System.Xml.XPath.XPathDocument> veya <xref:System.Xml.XmlDocument> nesne.</span><span class="sxs-lookup"><span data-stu-id="458de-119">Describes the ways to validate the XML content contained in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="458de-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="458de-120">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="458de-121">DOM Modelini Kullanarak XML Verilerini İşleme</span><span class="sxs-lookup"><span data-stu-id="458de-121">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)
