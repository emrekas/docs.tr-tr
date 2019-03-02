---
title: Diziler - örtük C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicity-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: de47d4a4b588b4e051450976ea91c813210eda1e
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202021"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="7b239-102">Türü Örtük Olarak Belirlenmiş Diziler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="7b239-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="7b239-103">Türü örtük olarak belirlenmiş dizi örneği türü çıkarımı yapılan bir dizi belirtilen dizi başlatıcısında öğeleri oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7b239-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="7b239-104">Örtük olarak yazılmış bir değişken için kuralları, örtük olarak yazılan diziler için de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="7b239-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="7b239-105">Daha fazla bilgi için [örtük olarak yazılan yerel değişkenler](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="7b239-105">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
 <span data-ttu-id="7b239-106">Türü örtük olarak belirlenmiş diziler, genellikle anonim türler ve nesne ve koleksiyon başlatıcıları birlikte sorgu ifadelerinde kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7b239-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>  
  
 <span data-ttu-id="7b239-107">Aşağıdaki örnekler, türü örtük olarak belirlenmiş dizi oluşturma işlemini gösterir:</span><span class="sxs-lookup"><span data-stu-id="7b239-107">The following examples show how to create an implicitly-typed array:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]  
  
 <span data-ttu-id="7b239-108">Önceki örnekte, örtük olarak yazılan diziler ile hiçbir köşeli parantez başlatma ifadesinin sol tarafında kullanılan dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="7b239-108">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="7b239-109">Basit diziler kullanılarak başlatılır unutmayın `new []` olduğu, tek boyutlu diziler gibi.</span><span class="sxs-lookup"><span data-stu-id="7b239-109">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>  
  
## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="7b239-110">Nesne başlatıcılarda örtük olarak yazılan diziler</span><span class="sxs-lookup"><span data-stu-id="7b239-110">Implicitly-typed Arrays in Object Initializers</span></span>

 <span data-ttu-id="7b239-111">Dizi içeren bir anonim tür oluşturduğunuzda, dizi türü nesne başlatıcı içinde örtük olarak yazılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="7b239-111">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="7b239-112">Aşağıdaki örnekte, `contacts` her biri adında bir dizi içeren bir örtük olarak anonim türler dizisidir `PhoneNumbers`.</span><span class="sxs-lookup"><span data-stu-id="7b239-112">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="7b239-113">Unutmayın `var` anahtar sözcüğünü nesne başlatıcılarda içinde kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="7b239-113">Note that the `var` keyword is not used inside the object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="7b239-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7b239-114">See also</span></span>

- [<span data-ttu-id="7b239-115">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="7b239-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7b239-116">Örtülü Olarak Yazılan Yerel Değişkenler</span><span class="sxs-lookup"><span data-stu-id="7b239-116">Implicitly Typed Local Variables</span></span>](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="7b239-117">Diziler</span><span class="sxs-lookup"><span data-stu-id="7b239-117">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)
- [<span data-ttu-id="7b239-118">Anonim Tipler</span><span class="sxs-lookup"><span data-stu-id="7b239-118">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="7b239-119">Nesne ve Koleksiyon Başlatıcıları</span><span class="sxs-lookup"><span data-stu-id="7b239-119">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="7b239-120">var</span><span class="sxs-lookup"><span data-stu-id="7b239-120">var</span></span>](../../../csharp/language-reference/keywords/var.md)
- [<span data-ttu-id="7b239-121">LINQ Sorgu ifadeleri</span><span class="sxs-lookup"><span data-stu-id="7b239-121">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
