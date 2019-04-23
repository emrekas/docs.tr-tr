---
title: 'Nasıl yapılır: Düğüm Parçasını Dönüştürme'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fabf7983a1887fb318bfb8d111b3911f4d90c545
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59345176"
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="73937-102">Nasıl yapılır: Düğüm Parçasını Dönüştürme</span><span class="sxs-lookup"><span data-stu-id="73937-102">How to: Transform a Node Fragment</span></span>
<span data-ttu-id="73937-103">İçerdiği verileri dönüştürme ne zaman bir <xref:System.Xml.XmlDocument> veya <xref:System.Xml.XPath.XPathDocument> XSLT dönüşümleri uygulamak için bir belgenin bir bütün olarak nesnesi.</span><span class="sxs-lookup"><span data-stu-id="73937-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="73937-104">Belge kök düğümü dışındaki bir düğümde geçirirseniz, diğer bir deyişle, bu dönüştürme süreci yüklenen belgedeki tüm düğümleri erişmesini engellemez.</span><span class="sxs-lookup"><span data-stu-id="73937-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="73937-105">Düğüm parçasını dönüştürme için yalnızca düğüm parçasını içeren ayrı bir nesne oluşturun ve gerekir, nesneyi geçirmek <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="73937-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="73937-106">Yordamlar</span><span class="sxs-lookup"><span data-stu-id="73937-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="73937-107">Düğüm parçasını dönüştürme için</span><span class="sxs-lookup"><span data-stu-id="73937-107">To transform a node fragment</span></span>  
  
1. <span data-ttu-id="73937-108">Kaynak belge içeren bir nesne oluşturun.</span><span class="sxs-lookup"><span data-stu-id="73937-108">Create an object containing the source document.</span></span>  
  
2. <span data-ttu-id="73937-109">Dönüştürmek istediğiniz düğüm parçasını bulun.</span><span class="sxs-lookup"><span data-stu-id="73937-109">Locate the node fragment you wish to transform.</span></span>  
  
3. <span data-ttu-id="73937-110">Ayrı bir nesne yalnızca düğüm parçasını ile oluşturun.</span><span class="sxs-lookup"><span data-stu-id="73937-110">Create separate object with just the node fragment.</span></span>  
  
4. <span data-ttu-id="73937-111">Geçirmek için düğüm parçasını <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="73937-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73937-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="73937-112">Example</span></span>  
 <span data-ttu-id="73937-113">Aşağıdaki örnek, bir düğüm parçasını dönüştürür ve sonuçlarını konsola çıkartır.</span><span class="sxs-lookup"><span data-stu-id="73937-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="73937-114">Giriş</span><span class="sxs-lookup"><span data-stu-id="73937-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="73937-115">Books.XML</span><span class="sxs-lookup"><span data-stu-id="73937-115">books.xml</span></span>  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="73937-116">Single.xsl</span><span class="sxs-lookup"><span data-stu-id="73937-116">single.xsl</span></span>  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="73937-117">Çıkış</span><span class="sxs-lookup"><span data-stu-id="73937-117">Output</span></span>  
 <span data-ttu-id="73937-118">Güvenle el kitabı başlıktır</span><span class="sxs-lookup"><span data-stu-id="73937-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73937-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="73937-119">See also</span></span>

- [<span data-ttu-id="73937-120">XslCompiledTransform Sınıfını Kullanma</span><span class="sxs-lookup"><span data-stu-id="73937-120">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
