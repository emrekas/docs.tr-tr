---
title: <include> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: bf7a434569bf82066c79962ae24741759b97e5ce
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973697"
---
# <a name="include-visual-basic"></a><span data-ttu-id="cf78a-102">\<Ekle > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf78a-102">\<include> (Visual Basic)</span></span>
<span data-ttu-id="cf78a-103">Türler ve üyeler, kaynak kodunuzdaki açıklayan başka bir dosyaya ifade eder.</span><span class="sxs-lookup"><span data-stu-id="cf78a-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf78a-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="cf78a-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf78a-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="cf78a-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="cf78a-106">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="cf78a-106">Required.</span></span> <span data-ttu-id="cf78a-107">Belgeleri içeren dosyanın adı.</span><span class="sxs-lookup"><span data-stu-id="cf78a-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="cf78a-108">Dosya adını içeren bir yol nitelenmiş olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cf78a-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="cf78a-109">İçine `filename` çift tırnak işaretleri ("").</span><span class="sxs-lookup"><span data-stu-id="cf78a-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="cf78a-110">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="cf78a-110">Required.</span></span> <span data-ttu-id="cf78a-111">Etiketleri yolunu `filename` etikete müşteri adayları `name`.</span><span class="sxs-lookup"><span data-stu-id="cf78a-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="cf78a-112">Yolu, çift tırnak işaretleri içine alın ("").</span><span class="sxs-lookup"><span data-stu-id="cf78a-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="cf78a-113">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="cf78a-113">Required.</span></span> <span data-ttu-id="cf78a-114">Yorumları önündeki etiketinde ad tanımlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="cf78a-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="cf78a-115">`Name` sahip bir `id`.</span><span class="sxs-lookup"><span data-stu-id="cf78a-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="cf78a-116">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="cf78a-116">Required.</span></span> <span data-ttu-id="cf78a-117">Yorumları önünde etiket kimliği.</span><span class="sxs-lookup"><span data-stu-id="cf78a-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="cf78a-118">Kimliği tek tırnak işaretleri içine (' ').</span><span class="sxs-lookup"><span data-stu-id="cf78a-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf78a-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cf78a-119">Remarks</span></span>  
 <span data-ttu-id="cf78a-120">Kullanım `<include>` türlerini açıklayan yorumlar başka bir dosyaya ve kaynak kodunuzu üyelerine başvurmak için etiket.</span><span class="sxs-lookup"><span data-stu-id="cf78a-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="cf78a-121">Bu belge açıklamaları doğrudan, kaynak kodu dosyasında yerleştirme için bir alternatifidir.</span><span class="sxs-lookup"><span data-stu-id="cf78a-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="cf78a-122">`<include>` Etiketini kullanır: W3C XML Path Language (XPath) sürüm 1.0 öneri.</span><span class="sxs-lookup"><span data-stu-id="cf78a-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="cf78a-123">Özelleştirme yolları hakkında daha fazla bilgi için `<include>` bakın <https://www.w3.org/TR/xpath>.</span><span class="sxs-lookup"><span data-stu-id="cf78a-123">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf78a-124">Örnek</span><span class="sxs-lookup"><span data-stu-id="cf78a-124">Example</span></span>  
 <span data-ttu-id="cf78a-125">Bu örnekte `<include>` belge açıklamaları üye adlı bir dosyadan içeri aktarmak için etiket `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="cf78a-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="cf78a-126">Biçimi `commentFile.xml` gibidir.</span><span class="sxs-lookup"><span data-stu-id="cf78a-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf78a-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cf78a-127">See also</span></span>
- [<span data-ttu-id="cf78a-128">XML Açıklama Etiketleri</span><span class="sxs-lookup"><span data-stu-id="cf78a-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
