---
title: XPathNavigator kullanarak XML verilerine erişme
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: c57b46e6-5c77-408f-bc4e-67a5dcc9cc05
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1827d93925b3ff2322d246f3d7d214cb57ac02fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707910"
---
# <a name="accessing-xml-data-using-xpathnavigator"></a><span data-ttu-id="2d6a2-102">XPathNavigator kullanarak XML verilerine erişme</span><span class="sxs-lookup"><span data-stu-id="2d6a2-102">Accessing XML Data using XPathNavigator</span></span>
<span data-ttu-id="2d6a2-103"><xref:System.Xml.XPath.XPathNavigator> Sınıfı düğümleri gidin, XML verileri ayıklamak ve kesin türü belirtilmiş XML verilerine erişmek için yöntemler sağlar bir <xref:System.Xml.XPath.XPathDocument> veya <xref:System.Xml.XmlDocument> nesne.</span><span class="sxs-lookup"><span data-stu-id="2d6a2-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to navigate nodes, extract XML data and access strongly typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d6a2-104">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="2d6a2-104">In This Section</span></span>  
 [<span data-ttu-id="2d6a2-105">XPathNavigator Kullanarak Düğüm Kümesinde Gezinme</span><span class="sxs-lookup"><span data-stu-id="2d6a2-105">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="2d6a2-106">Düğüm kümesi gezinti yöntemlerini açıklar <xref:System.Xml.XPath.XPathNavigator> düğümler gezinmek için kullanılan sınıf bir <xref:System.Xml.XPath.XPathDocument> veya <xref:System.Xml.XmlDocument> nesne.</span><span class="sxs-lookup"><span data-stu-id="2d6a2-106">Describes the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class used to navigate nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="2d6a2-107">XPathNavigator Kullanarak Öznitelik ve Ad Alanı Düğümünde Gezinme</span><span class="sxs-lookup"><span data-stu-id="2d6a2-107">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="2d6a2-108">Öznitelik ve ad alanı düğümünde gezinme yöntemlerini açıklar <xref:System.Xml.XPath.XPathNavigator> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="2d6a2-108">Describes the attribute and namespace node navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="2d6a2-109">XPathNavigator Kullanarak XML Verilerini Ayıklama</span><span class="sxs-lookup"><span data-stu-id="2d6a2-109">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="2d6a2-110">XML verileri ayıklamak için çeşitli yöntemler açıklayan bir <xref:System.Xml.XPath.XPathDocument> veya <xref:System.Xml.XmlDocument> nesne.</span><span class="sxs-lookup"><span data-stu-id="2d6a2-110">Describes the various methods of extracting XML data from an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="2d6a2-111">XPathNavigator Kullanarak Türü Kesin Olarak Belirtilmiş XML Verilerine Erişme</span><span class="sxs-lookup"><span data-stu-id="2d6a2-111">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="2d6a2-112">XML veri türü kesin belirlenmiş erişimi açıklar bir <xref:System.Xml.XPath.XPathDocument> veya <xref:System.Xml.XmlDocument> kullanarak nesne <xref:System.Xml.XPath.XPathNavigator> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="2d6a2-112">Describes accessing strongly-typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="2d6a2-113">Kullanıcı Tanımlı İşlevler ve Değişkenler</span><span class="sxs-lookup"><span data-stu-id="2d6a2-113">User Defined Functions and Variables</span></span>](../../../../docs/standard/data/xml/user-defined-functions-and-variables.md)  
 <span data-ttu-id="2d6a2-114">Özel bir uygulama açıklar <xref:System.Xml.Xsl.XsltContext> arabirimler sınıfıyla <xref:System.Xml.Xsl.IXsltContextFunction> ve <xref:System.Xml.Xsl.IXsltContextVariable> uzantı işlevleri ve değişkenler destekler.</span><span class="sxs-lookup"><span data-stu-id="2d6a2-114">Describes implementing a custom <xref:System.Xml.Xsl.XsltContext> class along with the interfaces <xref:System.Xml.Xsl.IXsltContextFunction> and <xref:System.Xml.Xsl.IXsltContextVariable> that support extension functions and variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d6a2-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2d6a2-115">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="2d6a2-116">XPath Veri Modelini Kullanarak XML Verilerini İşleme</span><span class="sxs-lookup"><span data-stu-id="2d6a2-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="2d6a2-117">XPathDocument ve XmlDocument Kullanarak XML Verilerini Okuma</span><span class="sxs-lookup"><span data-stu-id="2d6a2-117">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [<span data-ttu-id="2d6a2-118">XPathNavigator Kullanarak XML Verileri Seçme, Değerlendirme ve Eşleştirme</span><span class="sxs-lookup"><span data-stu-id="2d6a2-118">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="2d6a2-119">XPathNavigator Kullanarak XML Verilerini Düzenleme</span><span class="sxs-lookup"><span data-stu-id="2d6a2-119">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="2d6a2-120">XPathNavigator Kullanarak Şema Doğrulama</span><span class="sxs-lookup"><span data-stu-id="2d6a2-120">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
