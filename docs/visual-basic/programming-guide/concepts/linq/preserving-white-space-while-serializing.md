---
title: While Serializing2 boşluk koruma
ms.date: 07/20/2015
ms.assetid: 2d7abbd4-37f4-422b-89dd-0a694b5edc17
ms.openlocfilehash: cbfa9a39c52a40831627429f7ffc9971e0074a50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602045"
---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="8dfb5-102">Serileştirirken boşlukları koruma</span><span class="sxs-lookup"><span data-stu-id="8dfb5-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="8dfb5-103">Bu konuda, bir XML ağacı serileştirilirken boşluk denetlemek nasıl açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="8dfb5-104">Sık karşılaşılan bir senaryodur girintili XML oku, herhangi bir boşluk metin düğümleri (diğer bir deyişle, beyaz boşluk olmayan koruma) olmadan bir bellek içi XML ağacı oluşturmak, bazı XML işlemleri ve XML girintilemeli kaydedin sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="8dfb5-105">Biçimlendirme ile XML serileştirme, yalnızca önemli boşluk XML ağacındaki korunur.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="8dfb5-106">Varsayılan davranışı budur [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dfb5-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="8dfb5-107">Başka bir yaygın bir senaryo, okuma ve değiştirme kasıtlı olarak girintili zaten XML sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="8dfb5-108">Bu girinti herhangi bir şekilde değiştirmek istemeyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="8dfb5-109">Bunu yapmak için [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], yükleme veya XML Ayrıştırma ve XML serileştirme seçildiğinde biçimlendirmeyi devre dışı olduğunda bölünemez boşluğu koruyacak.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="8dfb5-110">XML ağaçlarını serileştirme yöntemleri boşluk davranışını</span><span class="sxs-lookup"><span data-stu-id="8dfb5-110">White Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="8dfb5-111">Aşağıdaki yöntemleri <xref:System.Xml.Linq.XElement> ve <xref:System.Xml.Linq.XDocument> sınıfların serileştirmek bir XML ağacı.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="8dfb5-112">Bir dosyaya bir XML ağacı serileştirebilen bir <xref:System.IO.TextReader>, veya bir <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="8dfb5-113">`ToString` Yöntemi bir dizeye serileştirir.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-113">The `ToString` method serializes to a string.</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="8dfb5-114">Yöntem değil izlerseniz <xref:System.Xml.Linq.SaveOptions> bağımsız değişken olarak, ardından yöntemi biçimlendirir (Girinti) serileştirilmiş XML.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-114">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="8dfb5-115">Bu durumda, XML ağacı Önemsiz tüm bölünemez boşluğu göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-115">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="8dfb5-116">Yöntem alırsanız <xref:System.Xml.Linq.SaveOptions> bağımsız değişken olarak, ardından yöntemi olmayan biçimlendirme belirtebilirsiniz (Girinti) serileştirilmiş XML.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-116">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="8dfb5-117">Bu durumda, XML ağacındaki tüm boşluk korunur.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-117">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dfb5-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8dfb5-118">See also</span></span>
- [<span data-ttu-id="8dfb5-119">(Visual Basic) XML ağaçlarını serileştirme</span><span class="sxs-lookup"><span data-stu-id="8dfb5-119">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
