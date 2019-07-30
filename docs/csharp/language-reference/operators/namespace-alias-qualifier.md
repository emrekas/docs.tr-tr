---
title: ':: operator- C# Reference'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: c494e8dbb18f44ce5520b21800a21d3feb03da59
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631136"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c0c71-102">:: işleci (C# başvuru)</span><span class="sxs-lookup"><span data-stu-id="c0c71-102">:: operator (C# reference)</span></span>

<span data-ttu-id="c0c71-103">Ad alanı diğer adı niteleyicisi`::`(), tanımlayıcıları aramak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="c0c71-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="c0c71-104">Bu örnekte olduğu gibi her zaman iki tanımlayıcı arasında konumlandırılır:</span><span class="sxs-lookup"><span data-stu-id="c0c71-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="c0c71-105">İşleci bir *using diğer adı yönergesi*ile de kullanılabilir: `::`</span><span class="sxs-lookup"><span data-stu-id="c0c71-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="c0c71-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c0c71-106">Remarks</span></span>

<span data-ttu-id="c0c71-107">Ad alanı diğer adı niteleyicisi `global`olabilir.</span><span class="sxs-lookup"><span data-stu-id="c0c71-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="c0c71-108">Bu, diğer ad alanı yerine genel ad alanında bir arama çağırır.</span><span class="sxs-lookup"><span data-stu-id="c0c71-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="c0c71-109">Daha fazla bilgi için</span><span class="sxs-lookup"><span data-stu-id="c0c71-109">For more information</span></span>

<span data-ttu-id="c0c71-110">`::` İşlecinin nasıl kullanılacağına ilişkin bir örnek için aşağıdaki bölüme bakın:</span><span class="sxs-lookup"><span data-stu-id="c0c71-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="c0c71-111">Nasıl yapılır: Genel ad alanı diğer adını kullan</span><span class="sxs-lookup"><span data-stu-id="c0c71-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="c0c71-112">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="c0c71-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c0c71-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c0c71-113">See also</span></span>

- [<span data-ttu-id="c0c71-114">C#başvurunun</span><span class="sxs-lookup"><span data-stu-id="c0c71-114">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c0c71-115">C# işleçleri</span><span class="sxs-lookup"><span data-stu-id="c0c71-115">C# operators</span></span>](index.md)
- [<span data-ttu-id="c0c71-116">. işlecinde</span><span class="sxs-lookup"><span data-stu-id="c0c71-116">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="c0c71-117">extern diğer adı</span><span class="sxs-lookup"><span data-stu-id="c0c71-117">extern alias</span></span>](../keywords/extern-alias.md)
