---
title: '&gt;&gt; Operator - C# başvurusu'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: f7cacd740966f0716e125887568a39abf0d9e454
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725434"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="af810-102">&gt;&gt; İşleci (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="af810-102">&gt;&gt; operator (C# Reference)</span></span>

<span data-ttu-id="af810-103">Sağa kaydırma işleci (`>>`) ilk işlenenin, ikinci işlenen tarafından belirtilen bit sayısının sağa kaydırır.</span><span class="sxs-lookup"><span data-stu-id="af810-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>

## <a name="remarks"></a><span data-ttu-id="af810-104">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="af810-104">Remarks</span></span>

<span data-ttu-id="af810-105">Birinci işlenenin ise bir [int](../keywords/int.md) veya [uint](../keywords/uint.md) (32-bit miktarı), kaydırma sayısı tarafından düşük sıra beş bitleri ikinci işlenenin verilmiştir (ikinci işlenen & 0x1f).</span><span class="sxs-lookup"><span data-stu-id="af810-105">If the first operand is an [int](../keywords/int.md) or [uint](../keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>

<span data-ttu-id="af810-106">Birinci işlenenin ise bir [uzun](../keywords/long.md) veya [ulong](../keywords/ulong.md) (64-bit miktarı), kaydırma sayısı tarafından düşük sıra altı bitleri ikinci işlenenin verilmiştir (ikinci işlenen & 0x3f).</span><span class="sxs-lookup"><span data-stu-id="af810-106">If the first operand is a [long](../keywords/long.md) or [ulong](../keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>

<span data-ttu-id="af810-107">Birinci işlenenin ise bir [int](../keywords/int.md) veya [uzun](../keywords/long.md), sağa kaydırma aritmetik bir kaydırmadır (imza biti için yüksek düzeyli boş bit ayarlanır).</span><span class="sxs-lookup"><span data-stu-id="af810-107">If the first operand is an [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="af810-108">Birinci işlenenin türü ise [uint](../keywords/uint.md) veya [ulong](../keywords/ulong.md), sağa kaydırma mantıksal bir kaydırmadır (yüksek düzeyli bitler sıfır dolgulu).</span><span class="sxs-lookup"><span data-stu-id="af810-108">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>

<span data-ttu-id="af810-109">Kullanıcı tanımlı türler aşırı yükleme `>>` işleci; birinci işlenenin türü kullanıcı tanımlı bir tür olmalı ve ikinci işlenenin türünde olmalıdır [int](../keywords/int.md). Daha fazla bilgi için [işleci](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="af810-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../keywords/int.md). For more information, see [operator](../keywords/operator.md).</span></span> <span data-ttu-id="af810-110">İkili İşleç aşırı karşılık gelen atama işleci, varsa, aynı zamanda örtük olarak aşırı yüklenmiş olur.</span><span class="sxs-lookup"><span data-stu-id="af810-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="af810-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="af810-111">Example</span></span>

[!code-csharp[csRefOperators#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#26)]

## <a name="see-also"></a><span data-ttu-id="af810-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="af810-112">See also</span></span>

- [<span data-ttu-id="af810-113">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="af810-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="af810-114">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="af810-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="af810-115">C#işleçleri</span><span class="sxs-lookup"><span data-stu-id="af810-115">C# operators</span></span>](index.md)