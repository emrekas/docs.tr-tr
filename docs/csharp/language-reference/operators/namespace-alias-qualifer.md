---
title: ':: işleci - C# başvurusu'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2618131f27271e7c06cb6d425fc22b5bd9750c49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61688858"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="15ba5-102">:: işleci (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="15ba5-102">:: operator (C# Reference)</span></span>

<span data-ttu-id="15ba5-103">Ad alanı diğer ad niteleyicisi (`::`) tanımlayıcıları aramak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="15ba5-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="15ba5-104">Her zaman, bu örnekte olduğu gibi iki tanımlayıcı arasında konumlandırılmış:</span><span class="sxs-lookup"><span data-stu-id="15ba5-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="15ba5-105">`::` İşleci de kullanılabilir olan bir *ALIAS yönergesi kullanarak*:</span><span class="sxs-lookup"><span data-stu-id="15ba5-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="15ba5-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="15ba5-106">Remarks</span></span>

<span data-ttu-id="15ba5-107">Ad alanı diğer ad niteleyicisi olabilir `global`.</span><span class="sxs-lookup"><span data-stu-id="15ba5-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="15ba5-108">Bu genel ad alanı yerine bir diğer adlı ad alanı içinde bir arama başlatır.</span><span class="sxs-lookup"><span data-stu-id="15ba5-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="15ba5-109">Daha fazla bilgi için</span><span class="sxs-lookup"><span data-stu-id="15ba5-109">For more information</span></span>

<span data-ttu-id="15ba5-110">Nasıl kullanılacağına ilişkin bir örnek `::` işleci, aşağıdaki bölüme bakın:</span><span class="sxs-lookup"><span data-stu-id="15ba5-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="15ba5-111">Nasıl yapılır: Genel Namespace diğer adlarını kullanma</span><span class="sxs-lookup"><span data-stu-id="15ba5-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="15ba5-112">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="15ba5-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="15ba5-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="15ba5-113">See also</span></span>

- [<span data-ttu-id="15ba5-114">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="15ba5-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="15ba5-115">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="15ba5-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="15ba5-116">C# işleçleri</span><span class="sxs-lookup"><span data-stu-id="15ba5-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="15ba5-117">Ad Alanı Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="15ba5-117">Namespace Keywords</span></span>](../keywords/namespace-keywords.md)
- [<span data-ttu-id="15ba5-118">. işleci</span><span class="sxs-lookup"><span data-stu-id="15ba5-118">. operator</span></span>](member-access-operator.md)
- [<span data-ttu-id="15ba5-119">extern diğer adı</span><span class="sxs-lookup"><span data-stu-id="15ba5-119">extern alias</span></span>](../keywords/extern-alias.md)