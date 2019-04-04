---
title: Dizin oluşturucular - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: 5ab0a5e524979110c355391cf800cc82e6d6244f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365028"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="10e8d-102">Dizin Oluşturucular (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="10e8d-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="10e8d-103">Dizin oluşturucular bir sınıf veya yapı dizileri gibi yeni dizine örneklerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="10e8d-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="10e8d-104">Dizinli değerin ayarlanması veya açıkça bir tür veya örnek üye belirtilmeden alınır.</span><span class="sxs-lookup"><span data-stu-id="10e8d-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="10e8d-105">Dizin oluşturucular benzer [özellikleri](../../../csharp/programming-guide/classes-and-structs/properties.md) dışında kendi erişimcileri parametre alır.</span><span class="sxs-lookup"><span data-stu-id="10e8d-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="10e8d-106">Aşağıdaki örnek, basit ile genel bir sınıf tanımlar [alma](../../../csharp/language-reference/keywords/get.md) ve [ayarlamak](../../../csharp/language-reference/keywords/set.md) atamak ve değerleri almak için erişimci metotlarını.</span><span class="sxs-lookup"><span data-stu-id="10e8d-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="10e8d-107">`Program` Sınıfı, dizeleri depolamak için bu sınıfın bir örneğini oluşturur.</span><span class="sxs-lookup"><span data-stu-id="10e8d-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="10e8d-108">Daha fazla örnek için bkz. [ilgili bölümler](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="10e8d-108">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="10e8d-109">İfade gövdesi tanımları</span><span class="sxs-lookup"><span data-stu-id="10e8d-109">Expression Body Definitions</span></span>  
 
<span data-ttu-id="10e8d-110">Bir oluşturucunun get veya set erişimcisi döndürür veya bir değer ayarlar tek bir deyimde oluşmalıdır için yaygın bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="10e8d-110">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="10e8d-111">İfade gövdeli üyeler bu senaryoyu desteklemek için basitleştirilmiş bir sözdizimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="10e8d-111">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="10e8d-112">C# 6 ile başlayarak, aşağıdaki örnekte gösterildiği gibi bir ifade gövdeli üyesi olarak bir salt okunur dizin oluşturucu uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="10e8d-112">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="10e8d-113">Unutmayın `=>` ifade gövdesi ve `get` anahtar sözcüğü kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="10e8d-113">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="10e8d-114">C# 7.0, hem get ile başlayan ve set erişimcisi olabilir uygulanan bir ifade gövdeli üyeler.</span><span class="sxs-lookup"><span data-stu-id="10e8d-114">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="10e8d-115">Bu durumda, her ikisi de `get` ve `set` anahtar sözcükleri kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="10e8d-115">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="10e8d-116">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="10e8d-116">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="10e8d-117">Dizin Oluşturuculara Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="10e8d-117">Indexers Overview</span></span>  
  
-   <span data-ttu-id="10e8d-118">Dizin oluşturucular nesneleri dizilere benzer şekilde dizinlenmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="10e8d-118">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="10e8d-119">A `get` erişimcisinin bir değer döndürür.</span><span class="sxs-lookup"><span data-stu-id="10e8d-119">A `get` accessor returns a value.</span></span> <span data-ttu-id="10e8d-120">A `set` erişimcisinin bir değer atar.</span><span class="sxs-lookup"><span data-stu-id="10e8d-120">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="10e8d-121">[Bu](../../../csharp/language-reference/keywords/this.md) anahtar sözcüğü, dizin oluşturucuyu tanımlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="10e8d-121">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="10e8d-122">[Değer](../../../csharp/language-reference/keywords/value.md) tarafından atanan değerin tanımlamak için kullanılan anahtar sözcüğü `set` dizin oluşturucu.</span><span class="sxs-lookup"><span data-stu-id="10e8d-122">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="10e8d-123">Dizin oluşturucular bir tamsayı değeri tarafından dizine gerekmez; size özel arama mekanizması tanımlama bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="10e8d-123">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="10e8d-124">Dizin oluşturucular aşırı yüklenebilir.</span><span class="sxs-lookup"><span data-stu-id="10e8d-124">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="10e8d-125">Dizin oluşturucular birden fazla biçimsel parametre, örneğin, iki boyutlu bir dizi erişirken olabilir.</span><span class="sxs-lookup"><span data-stu-id="10e8d-125">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="BKMK_RelatedSections"></a> <span data-ttu-id="10e8d-126">İlgili bölümler</span><span class="sxs-lookup"><span data-stu-id="10e8d-126">Related Sections</span></span>  
  
-   [<span data-ttu-id="10e8d-127">Dizin Oluşturucular Kullanma</span><span class="sxs-lookup"><span data-stu-id="10e8d-127">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="10e8d-128">Arabirimlerdeki Dizin Oluşturucular</span><span class="sxs-lookup"><span data-stu-id="10e8d-128">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="10e8d-129">Özellikler ve Dizin Oluşturucular Arasında Karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="10e8d-129">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="10e8d-130">Erişimci Erişilebilirliğini Kısıtlama</span><span class="sxs-lookup"><span data-stu-id="10e8d-130">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="10e8d-131">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="10e8d-131">C# Language Specification</span></span>  

<span data-ttu-id="10e8d-132">Daha fazla bilgi için [dizin oluşturucular](~/_csharplang/spec/classes.md#indexers) içinde [ C# dil belirtimi](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="10e8d-132">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="10e8d-133">Dil belirtimi, C# sözdizimi ve kullanımı için kesin bir kaynaktır.</span><span class="sxs-lookup"><span data-stu-id="10e8d-133">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="10e8d-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="10e8d-134">See also</span></span>

- [<span data-ttu-id="10e8d-135">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="10e8d-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="10e8d-136">Özellikler</span><span class="sxs-lookup"><span data-stu-id="10e8d-136">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
