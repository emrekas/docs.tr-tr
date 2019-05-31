---
title: Genel arabirimler - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: 7fc79874c8e1ff24c38d288d3f6708e2851419e3
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423480"
---
# <a name="generic-interfaces-c-programming-guide"></a><span data-ttu-id="9e271-102">Genel Arabirimler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="9e271-102">Generic Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="9e271-103">Genellikle, genel amaçlı koleksiyon sınıfları, veya bir koleksiyondaki öğeleri temsil eden genel sınıfları arabirimler tanımlamak yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="9e271-103">It is often useful to define interfaces either for generic collection classes, or for the generic classes that represent items in the collection.</span></span> <span data-ttu-id="9e271-104">Genel sınıflar için tercih genel arabirimler gibi kullanmaktır <xref:System.IComparable%601> yerine <xref:System.IComparable>, değer türleri kutulama ve kutudan çıkarma işlemleri önlemek için.</span><span class="sxs-lookup"><span data-stu-id="9e271-104">The preference for generic classes is to use generic interfaces, such as <xref:System.IComparable%601> rather than <xref:System.IComparable>, in order to avoid boxing and unboxing operations on value types.</span></span> <span data-ttu-id="9e271-105">.NET Framework sınıf kitaplığı ile koleksiyon sınıflarını kullanmak için çeşitli genel arabirimlerin tanımlar <xref:System.Collections.Generic> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="9e271-105">The .NET Framework class library defines several generic interfaces for use with the collection classes in the <xref:System.Collections.Generic> namespace.</span></span>  
  
 <span data-ttu-id="9e271-106">Bir arabirim bir tür parametresi kısıtlaması olarak belirtildiğinde yalnızca arabirim türleri kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9e271-106">When an interface is specified as a constraint on a type parameter, only types that implement the interface can be used.</span></span> <span data-ttu-id="9e271-107">Aşağıdaki kod örnekte gösterildiği bir `SortedList<T>` türetilen sınıf `GenericList<T>` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="9e271-107">The following code example shows a `SortedList<T>` class that derives from the `GenericList<T>` class.</span></span> <span data-ttu-id="9e271-108">Daha fazla bilgi için [genel türlere giriş](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="9e271-108">For more information, see [Introduction to Generics](../../../csharp/programming-guide/generics/index.md).</span></span> <span data-ttu-id="9e271-109">`SortedList<T>` kısıtlama ekler `where T : IComparable<T>`.</span><span class="sxs-lookup"><span data-stu-id="9e271-109">`SortedList<T>` adds the constraint `where T : IComparable<T>`.</span></span> <span data-ttu-id="9e271-110">Böylece `BubbleSort` yönteminde `SortedList<T>` genel kullanılacak <xref:System.IComparable%601.CompareTo%2A> liste öğelerini yöntemi.</span><span class="sxs-lookup"><span data-stu-id="9e271-110">This enables the `BubbleSort` method in `SortedList<T>` to use the generic <xref:System.IComparable%601.CompareTo%2A> method on list elements.</span></span> <span data-ttu-id="9e271-111">Bu örnekte, liste öğelerini basit bir sınıfı olan `Person`, uygulayan `IComparable<Person>`.</span><span class="sxs-lookup"><span data-stu-id="9e271-111">In this example, list elements are a simple class, `Person`, that implements `IComparable<Person>`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 <span data-ttu-id="9e271-112">Birden çok arabirim olarak tek bir tür kısıtlamaları şu şekilde belirlenebilir:</span><span class="sxs-lookup"><span data-stu-id="9e271-112">Multiple interfaces can be specified as constraints on a single type, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 <span data-ttu-id="9e271-113">Bir arabirim gibi birden fazla tür parametresi tanımlayabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="9e271-113">An interface can define more than one type parameter, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 <span data-ttu-id="9e271-114">Sınıflar için geçerli olan kurallar devralma ayrıca arayüzlere uygulanır:</span><span class="sxs-lookup"><span data-stu-id="9e271-114">The rules of inheritance that apply to classes also apply to interfaces:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 <span data-ttu-id="9e271-115">Dönüş değeri olarak yalnızca kendi tür parametresi kullandığı anlamına gelir değişken karşıtı genel arabirim ise genel arabirimler genel olmayan Ara birimden devralınabilir.</span><span class="sxs-lookup"><span data-stu-id="9e271-115">Generic interfaces can inherit from non-generic interfaces if the generic interface is contravariant, which means it only uses its type parameter as a return value.</span></span> <span data-ttu-id="9e271-116">.NET Framework sınıf kitaplığındaki <xref:System.Collections.Generic.IEnumerable%601> devraldığı <xref:System.Collections.IEnumerable> çünkü <xref:System.Collections.Generic.IEnumerable%601> yalnızca kullanır `T` dönüş değerini <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> ve <xref:System.Collections.Generic.IEnumerator%601.Current%2A> özellik Alıcısı.</span><span class="sxs-lookup"><span data-stu-id="9e271-116">In the .NET Framework class library, <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable> because <xref:System.Collections.Generic.IEnumerable%601> only uses `T` in the return value of <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> and in the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property getter.</span></span>  
  
 <span data-ttu-id="9e271-117">Somut sınıflar gibi kapalı oluşturulmuş arabirimler uygulayabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="9e271-117">Concrete classes can implement closed constructed interfaces, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 <span data-ttu-id="9e271-118">Arabirim tarafından şu şekilde gerekli tüm bağımsız değişkenler sınıfı parametre listesi sağlayan sürece genel sınıflar genel arabirimler veya kapalı bir oluşturulmuş arabirimler uygulayabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="9e271-118">Generic classes can implement generic interfaces or closed constructed interfaces as long as the class parameter list supplies all arguments required by the interface, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 <span data-ttu-id="9e271-119">Yöntem aşırı yükü denetleyen kuralları Genel sınıflar, yapılar genel veya genel arabirimler içinde yöntemleri için aynıdır.</span><span class="sxs-lookup"><span data-stu-id="9e271-119">The rules that control method overloading are the same for methods within generic classes, generic structs, or generic interfaces.</span></span> <span data-ttu-id="9e271-120">Daha fazla bilgi için [genel yöntemler](../../../csharp/programming-guide/generics/generic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="9e271-120">For more information, see [Generic Methods](../../../csharp/programming-guide/generics/generic-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e271-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9e271-121">See also</span></span>

- [<span data-ttu-id="9e271-122">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9e271-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9e271-123">Genel Türlere Giriş</span><span class="sxs-lookup"><span data-stu-id="9e271-123">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="9e271-124">interface</span><span class="sxs-lookup"><span data-stu-id="9e271-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)
- [<span data-ttu-id="9e271-125">Genel Türler</span><span class="sxs-lookup"><span data-stu-id="9e271-125">Generics</span></span>](~/docs/standard/generics/index.md)
