---
title: -içine C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: b209062a2a3e563ea8e70cb7883d9bbfa3662231
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631522"
---
# <a name="into-c-reference"></a><span data-ttu-id="0419b-102">into (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="0419b-102">into (C# Reference)</span></span>

<span data-ttu-id="0419b-103">`into` Bağlamsal anahtar sözcüğü, sonuçlarını depolamak için geçici bir tanımlayıcı oluşturmak için kullanılabilir bir [grubu](group-clause.md), [birleştirme](join-clause.md) veya [seçin](select-clause.md) yan tümcesine yeni bir tanımlayıcı.</span><span class="sxs-lookup"><span data-stu-id="0419b-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="0419b-104">Bu tanımlayıcı kendisini ek sorgu komutları için bir oluşturucuyu olabilir.</span><span class="sxs-lookup"><span data-stu-id="0419b-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="0419b-105">Kullanıldığında bir `group` veya `select` yan tümcesi, yeni tanımlayıcısı kullanımını bazen olarak adlandırılır bir *devamlılık*.</span><span class="sxs-lookup"><span data-stu-id="0419b-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="0419b-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="0419b-106">Example</span></span>

<span data-ttu-id="0419b-107">Aşağıdaki örnek kullanımını gösterir `into` geçici bir tanımlayıcı etkinleştirmek için anahtar sözcüğü `fruitGroup` sahip olduğu bir çıkarsanan tür `IGrouping`.</span><span class="sxs-lookup"><span data-stu-id="0419b-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="0419b-108">Tanımlayıcısı'nı kullanarak çağırabilirsiniz <xref:System.Linq.Enumerable.Count%2A> yöntemi her grubu ve iki veya daha fazla sözcük içeren grubu seçin.</span><span class="sxs-lookup"><span data-stu-id="0419b-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="0419b-109">Kullanımını `into` içinde bir `group` yan tümcesi, yalnızca gerekli ek sorgu her grubu işlemleri istediğinizde.</span><span class="sxs-lookup"><span data-stu-id="0419b-109">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="0419b-110">Daha fazla bilgi için [group yan tümcesi](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0419b-110">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="0419b-111">Kullanımını gösteren bir örnek `into` içinde bir `join` yan tümcesi bkz [JOIN yan tümcesi](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0419b-111">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0419b-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0419b-112">See also</span></span>

- [<span data-ttu-id="0419b-113">Query Keywords (LINQ)</span><span class="sxs-lookup"><span data-stu-id="0419b-113">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="0419b-114">LINQ Sorgu ifadeleri</span><span class="sxs-lookup"><span data-stu-id="0419b-114">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="0419b-115">group yan tümcesi</span><span class="sxs-lookup"><span data-stu-id="0419b-115">group clause</span></span>](group-clause.md)
