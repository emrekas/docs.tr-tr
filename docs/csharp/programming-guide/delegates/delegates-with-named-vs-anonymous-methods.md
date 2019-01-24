---
title: Temsilcilerin adlandırılmış ve. Anonim yöntemler - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 077bc9d7a433c6fdf60f739f34c25a1b469fea02
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509573"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="8e954-102">Temsilcilerin adlandırılmış ve. Anonim Yöntemler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="8e954-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="8e954-103">A [temsilci](../../../csharp/language-reference/keywords/delegate.md) adlandırılmış bir yöntemle ilişkili olabilir.</span><span class="sxs-lookup"><span data-stu-id="8e954-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can be associated with a named method.</span></span> <span data-ttu-id="8e954-104">Adlandırılmış bir yöntemi kullanarak bir temsilci örneğini oluştururken yöntemi örneğin bir parametre olarak geçirilir:</span><span class="sxs-lookup"><span data-stu-id="8e954-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]  
  
 <span data-ttu-id="8e954-105">Bu işlem, adlandırılmış bir yöntemi kullanılarak çağrılır.</span><span class="sxs-lookup"><span data-stu-id="8e954-105">This is called using a named method.</span></span> <span data-ttu-id="8e954-106">Temsilcilerin adlandırılmış bir yöntem ile oluşturulmuş ya da kapsüllemek bir [statik](../../../csharp/language-reference/keywords/static.md) yöntem veya oluşum yöntemi.</span><span class="sxs-lookup"><span data-stu-id="8e954-106">Delegates constructed with a named method can encapsulate either a [static](../../../csharp/language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="8e954-107">Adlandırılmış yöntemler, C# ' ın önceki sürümlerinde bir temsilci tek yoludur.</span><span class="sxs-lookup"><span data-stu-id="8e954-107">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="8e954-108">Ancak, yeni bir yöntem oluşturma ek yükü istenmeyen olduğu bir durumda C#, bir temsilci ve hemen çağrıldığında, bu temsilci işleyecek bir kod bloğu belirtmenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="8e954-108">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="8e954-109">Bir lambda ifadesi veya anonim yöntemi blok içerebilir.</span><span class="sxs-lookup"><span data-stu-id="8e954-109">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="8e954-110">Daha fazla bilgi için [anonim işlevler](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="8e954-110">For more information, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e954-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8e954-111">Remarks</span></span>  
 <span data-ttu-id="8e954-112">Temsilcinin parametre olarak geçen yöntemi temsilci bildirimi aynı imzaya sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="8e954-112">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="8e954-113">Bir temsilci örneği kapsülleyen ya da statik veya örnek yöntemi olabilir.</span><span class="sxs-lookup"><span data-stu-id="8e954-113">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="8e954-114">Temsilci kullanmanız mümkün olmakla birlikte bir [kullanıma](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parametresi değil öneririz kullanımı ile çok noktaya yayın olay temsilcileri çünkü hangi temsilcinin çağrılacağı bilemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="8e954-114">Although the delegate can use an [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="8e954-115">Örnek 1</span><span class="sxs-lookup"><span data-stu-id="8e954-115">Example 1</span></span>  
 <span data-ttu-id="8e954-116">Bildirme ve bir temsilci kullanarak basit bir örnek verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="8e954-116">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="8e954-117">Dikkat her iki temsilci `Del`ve ilişkili yöntem `MultiplyNumbers`, aynı imzaya sahip</span><span class="sxs-lookup"><span data-stu-id="8e954-117">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]  
  
## <a name="example-2"></a><span data-ttu-id="8e954-118">Örnek 2</span><span class="sxs-lookup"><span data-stu-id="8e954-118">Example 2</span></span>  
 <span data-ttu-id="8e954-119">Aşağıdaki örnekte, bir temsilci hem statik olarak eşleştirilir ve örneği her belirli bilgiler yöntemleri ve döndürür.</span><span class="sxs-lookup"><span data-stu-id="8e954-119">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8e954-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8e954-120">See also</span></span>

- [<span data-ttu-id="8e954-121">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="8e954-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8e954-122">Temsilciler</span><span class="sxs-lookup"><span data-stu-id="8e954-122">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="8e954-123">Anonim Metotlar</span><span class="sxs-lookup"><span data-stu-id="8e954-123">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [<span data-ttu-id="8e954-124">Nasıl yapılır: Temsilcileri (çok noktaya yayın temsilcileri) birleştirme</span><span class="sxs-lookup"><span data-stu-id="8e954-124">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="8e954-125">Olaylar</span><span class="sxs-lookup"><span data-stu-id="8e954-125">Events</span></span>](../../../csharp/programming-guide/events/index.md)
