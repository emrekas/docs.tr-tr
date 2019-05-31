---
title: Genel temsilciler - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: ff19b3d71858552158a8ae5d0ab362a86dc98e65
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423502"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="d3a30-102">Genel Temsilciler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="d3a30-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="d3a30-103">A [temsilci](../../../csharp/language-reference/keywords/delegate.md) kendi tür parametreleri tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d3a30-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can define its own type parameters.</span></span> <span data-ttu-id="d3a30-104">Kod başvurularını Genel temsilci kapalı bir oluşturulmuş tür, gibi ne zaman oluşturulacağını tür bağımsız değişkeni belirtebilirsiniz genel bir sınıf örnekleme veya aşağıdaki örnekte gösterildiği gibi bir genel yöntem çağırma:</span><span class="sxs-lookup"><span data-stu-id="d3a30-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="d3a30-105">C# sürüm 2.0 somut yanı sıra Genel temsilci türleri için geçerlidir ve önceki satıra bu Basitleştirilmiş söz dizimi yazmanızı sağlar yöntem grubu dönüştürme adlı yeni bir özellik vardır:</span><span class="sxs-lookup"><span data-stu-id="d3a30-105">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="d3a30-106">Temsilciler genel bir sınıf içinde tanımlanan genel sınıf türündeki parametrelere sınıfı yöntemleri yapan aynı şekilde kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d3a30-106">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="d3a30-107">Temsilci başvurduğu kod şu şekilde içerilen sınıfının, tür bağımsız değişkeni belirtmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="d3a30-107">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="d3a30-108">Genel temsilciler olayları gönderen bağımsız değişken türü kesin belirlenmiş ve ondan dönüştürme artık sahip olduğundan, normal tasarım deseni temel alınarak tanımlarken kullanışlı <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="d3a30-108">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="d3a30-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d3a30-109">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="d3a30-110">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="d3a30-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d3a30-111">Genel Türlere Giriş</span><span class="sxs-lookup"><span data-stu-id="d3a30-111">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="d3a30-112">Genel Yöntemler</span><span class="sxs-lookup"><span data-stu-id="d3a30-112">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)
- [<span data-ttu-id="d3a30-113">Genel Sınıflar</span><span class="sxs-lookup"><span data-stu-id="d3a30-113">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)
- [<span data-ttu-id="d3a30-114">Genel Arabirimler</span><span class="sxs-lookup"><span data-stu-id="d3a30-114">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)
- [<span data-ttu-id="d3a30-115">Temsilciler</span><span class="sxs-lookup"><span data-stu-id="d3a30-115">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="d3a30-116">Genel Türler</span><span class="sxs-lookup"><span data-stu-id="d3a30-116">Generics</span></span>](~/docs/standard/generics/index.md)
