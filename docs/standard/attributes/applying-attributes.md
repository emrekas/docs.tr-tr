---
title: Öznitelikleri Uygulama
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- attributes [.NET Framework], applying
ms.assetid: dd7604eb-9fa3-4b60-b2dd-b47739fa3148
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6bf86986f9e6f72fca9d6e88ac16699ff7cdb4e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606485"
---
# <a name="applying-attributes"></a><span data-ttu-id="5d8ef-102">Öznitelikleri Uygulama</span><span class="sxs-lookup"><span data-stu-id="5d8ef-102">Applying Attributes</span></span>
<span data-ttu-id="5d8ef-103">Kodunuzdaki bir öğeye bir öznitelik uygulamak için aşağıdaki işlemi kullanın.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-103">Use the following process to apply an attribute to an element of your code.</span></span>  
  
1.  <span data-ttu-id="5d8ef-104">Ad alanını .NET Framework'ten içe aktararak yeni bir öznitelik tanımlayın veya varolan bir özniteliği kullanın.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-104">Define a new attribute or use an existing attribute by importing its namespace from the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="5d8ef-105">Özniteliği öğenin hemen önüne ekleyerek kod öğesine uygulayın.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-105">Apply the attribute to the code element by placing it immediately before the element.</span></span>  
  
     <span data-ttu-id="5d8ef-106">Her dilin kendi öznitelik sözdizimi bulunur.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-106">Each language has its own attribute syntax.</span></span> <span data-ttu-id="5d8ef-107">C++ ve C#'de öznitelik, köşeli ayraç içine alınır ve öğeden, satır sonu da içerebilen boşluk ile ayrılır.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-107">In C++ and C#, the attribute is surrounded by square brackets and separated from the element by white space, which can include a line break.</span></span> <span data-ttu-id="5d8ef-108">Visual Basic'te öznitelik, açılı ayraç içine alınır ve aynı mantıksal satırda bulunması gerekir; eğer bir satır sonu isterseniz satır devamı karakteri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-108">In Visual Basic, the attribute is surrounded by angle brackets and must be on the same logical line; the line continuation character can be used if a line break is desired.</span></span>
  
3.  <span data-ttu-id="5d8ef-109">Öznitelik için konumsal parametreleri ve adlandırılmış parametreleri belirtin.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-109">Specify positional parameters and named parameters for the attribute.</span></span>  
  
     <span data-ttu-id="5d8ef-110">Konumsal parametreler gereklidir ve adlandırılmış parametrelerden önce gelmeleri gerekir; öznitelik oluşturucularından birinin parametrelerine karşılık gelirler.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-110">Positional parameters are required and must come before any named parameters; they correspond to the parameters of one of the attribute's constructors.</span></span> <span data-ttu-id="5d8ef-111">Adlandırılmış parametreler isteğe bağlıdır ve özniteliğin okuma/yazma özelliklerine karşılık gelirler.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-111">Named parameters are optional and correspond to read/write properties of the attribute.</span></span> <span data-ttu-id="5d8ef-112">C++ ve C#, belirtin `name` = `value` isteğe bağlı her parametre için burada `name` özelliğin adıdır.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-112">In C++, and C#, specify `name`=`value` for each optional parameter, where `name` is the name of the property.</span></span> <span data-ttu-id="5d8ef-113">Visual Basic'te, `name`:=`value` belirtin.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-113">In Visual Basic, specify `name`:=`value`.</span></span>  
  
 <span data-ttu-id="5d8ef-114">Kodunuzu derlediğinizde öznitelik meta verilere yayılır ve çalışma zamanı yansıma hizmetleri ile ortak dil çalışma zamanı ve herhangi bir özel araç veya uygulama tarafından kullanılabilir olur.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-114">The attribute is emitted into metadata when you compile your code and is available to the common language runtime and any custom tool or application through the runtime reflection services.</span></span>  
  
 <span data-ttu-id="5d8ef-115">Kural gereği, tüm öznitelik adları Öznitelik ile biter.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-115">By convention, all attribute names end with Attribute.</span></span> <span data-ttu-id="5d8ef-116">Ancak, Visual Basic ve C# gibi çalışma zamanını hedef alan çeşitli diller, bir özniteliğin tam adını belirtmenizi gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-116">However, several languages that target the runtime, such as Visual Basic and C#, do not require you to specify the full name of an attribute.</span></span> <span data-ttu-id="5d8ef-117">Örneğin, başlatmak istiyorsanız <xref:System.ObsoleteAttribute?displayProperty=nameWithType>, olarak başvurmanız yeterlidir **Kullanımdan kalktı**.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-117">For example, if you want to initialize <xref:System.ObsoleteAttribute?displayProperty=nameWithType>, you only need to reference it as **Obsolete**.</span></span>  
  
## <a name="applying-an-attribute-to-a-method"></a><span data-ttu-id="5d8ef-118">Bir Yönteme Öznitelik Uygulama</span><span class="sxs-lookup"><span data-stu-id="5d8ef-118">Applying an Attribute to a Method</span></span>  
 <span data-ttu-id="5d8ef-119">Aşağıdaki kod örneğinde nasıl belirtileceğini gösterir **System.ObsoleteAttribute**, kodu kullanımdan kalkmış olarak işaretler.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-119">The following code example shows how to declare **System.ObsoleteAttribute**, which marks code as obsolete.</span></span> <span data-ttu-id="5d8ef-120">`"Will be removed in next version"` dizesi özniteliğe geçirilir.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-120">The string `"Will be removed in next version"` is passed to the attribute.</span></span> <span data-ttu-id="5d8ef-121">Bu öznitelik, özniteliğin açıkladığı kod çağırıldığında geçirilen dizeyi görüntüleyen bir derleyici uyarısına neden olur.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-121">This attribute causes a compiler warning that displays the passed string when code that the attribute describes is called.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#3)]
 [!code-csharp[Conceptual.Attributes.Usage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#3)]
 [!code-vb[Conceptual.Attributes.Usage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#3)]  
  
## <a name="applying-attributes-at-the-assembly-level"></a><span data-ttu-id="5d8ef-122">Öznitelikleri Derleme Düzeyinde Uygulama</span><span class="sxs-lookup"><span data-stu-id="5d8ef-122">Applying Attributes at the Assembly Level</span></span>  
 <span data-ttu-id="5d8ef-123">Bir özniteliği derleme düzeyinde uygulamak istiyorsanız, kullanın **derleme** (`Assembly` Visual Basic'te) anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-123">If you want to apply an attribute at the assembly level, use the **assembly** (`Assembly` in Visual Basic) keyword.</span></span> <span data-ttu-id="5d8ef-124">Aşağıdaki kodda gösterildiği **AssemblyTitleAttribute** derleme düzeyinde uygulanır.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-124">The following code shows the **AssemblyTitleAttribute** applied at the assembly level.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#2)]
 [!code-csharp[Conceptual.Attributes.Usage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#2)]
 [!code-vb[Conceptual.Attributes.Usage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#2)]  
  
 <span data-ttu-id="5d8ef-125">Bu öznitelik uygulandığında `"My Assembly"` dizesi, dosyanın meta veri bölümündeki derleme bildirimine yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-125">When this attribute is applied, the string `"My Assembly"` is placed in the assembly manifest in the metadata portion of the file.</span></span> <span data-ttu-id="5d8ef-126">Özniteliğini kullanarak ya da görüntüleyebilirsiniz [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) veya özniteliği almak için özel bir program oluşturarak.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-126">You can view the attribute either by using the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by creating a custom program to retrieve the attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d8ef-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5d8ef-127">See also</span></span>

- [<span data-ttu-id="5d8ef-128">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="5d8ef-128">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- [<span data-ttu-id="5d8ef-129">Özniteliklerde Depolanan Bilgileri Alma</span><span class="sxs-lookup"><span data-stu-id="5d8ef-129">Retrieving Information Stored in Attributes</span></span>](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)
- [<span data-ttu-id="5d8ef-130">Kavramları</span><span class="sxs-lookup"><span data-stu-id="5d8ef-130">Concepts</span></span>](/cpp/windows/attributed-programming-concepts)
- [<span data-ttu-id="5d8ef-131">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="5d8ef-131">Attributes</span></span>](https://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
