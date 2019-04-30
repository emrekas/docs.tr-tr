---
title: '- Operator - C# başvurusu'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 8cf6e8871a88e2b37b9531ecbd616289523473c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61688806"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="10d68-102">-işleci (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="10d68-102">- operator (C# Reference)</span></span>

<span data-ttu-id="10d68-103">`-` İşleci bir birli veya ikili işleç olarak işlev görebilir.</span><span class="sxs-lookup"><span data-stu-id="10d68-103">The `-` operator can function as either a unary or a binary operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="10d68-104">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="10d68-104">Remarks</span></span>

<span data-ttu-id="10d68-105">Birli `-` işleçleri tüm sayısal türler için önceden tanımlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="10d68-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="10d68-106">Bir tekli sonucunu `-` işlemdir üzerinde bir sayısal tür işleneni sayısal negation.</span><span class="sxs-lookup"><span data-stu-id="10d68-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>

<span data-ttu-id="10d68-107">İkili `-` işleçleri ikinci işlenen ilk çıkarılacak tüm sayısal ve sabit listesi türleri için önceden tanımlanmış.</span><span class="sxs-lookup"><span data-stu-id="10d68-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>

<span data-ttu-id="10d68-108">Temsilci türleri de sağlayan bir ikili `-` işleci, temsilci kaldırma gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="10d68-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>

<span data-ttu-id="10d68-109">Kullanıcı tanımlı türler aşırı yükleme birli `-` ve ikili `-` işleçleri.</span><span class="sxs-lookup"><span data-stu-id="10d68-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="10d68-110">Daha fazla bilgi için [işleç anahtar sözcüğü](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="10d68-110">For more information, see [operator keyword](../keywords/operator.md).</span></span>

## <a name="example"></a><span data-ttu-id="10d68-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="10d68-111">Example</span></span>

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a><span data-ttu-id="10d68-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="10d68-112">See also</span></span>

- [<span data-ttu-id="10d68-113">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="10d68-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="10d68-114">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="10d68-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="10d68-115">C# işleçleri</span><span class="sxs-lookup"><span data-stu-id="10d68-115">C# operators</span></span>](index.md)