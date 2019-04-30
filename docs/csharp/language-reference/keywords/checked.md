---
title: checked anahtar sözcüğü - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: 5ce9291fd047dfa9c69048887ccbd878819f2de8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61662018"
---
# <a name="checked-c-reference"></a><span data-ttu-id="95d6e-102">checked (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="95d6e-102">checked (C# Reference)</span></span>

<span data-ttu-id="95d6e-103">`checked` Anahtar sözcüğü, Tamsayı türünde aritmetik işlemler ve dönüştürmeler için denetleme taşma açıkça etkinleştirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="95d6e-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="95d6e-104">Hedef türün aralığı dışında bir değer ifade oluşturursa, varsayılan olarak, yalnızca sabit değerleri içeren ifade bir derleyici hatasına neden olur.</span><span class="sxs-lookup"><span data-stu-id="95d6e-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="95d6e-105">İfade, bir veya daha fazla sabit olmayan değerler içeriyorsa, derleyici taşma algılamaz.</span><span class="sxs-lookup"><span data-stu-id="95d6e-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="95d6e-106">Atanan ifade değerlendirme `i2` aşağıdaki örnekte, bir derleyici hatasına neden olmaz.</span><span class="sxs-lookup"><span data-stu-id="95d6e-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>

[!code-csharp[csrefKeywordsChecked#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#3)]

<span data-ttu-id="95d6e-107">Varsayılan olarak, bu sabit ifadeler taşma için çalışma zamanında ya da denetlenmez ve taşma özel geçirmeyin.</span><span class="sxs-lookup"><span data-stu-id="95d6e-107">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="95d6e-108">Önceki örnekte, iki pozitif tam sayının toplamını-2,147,483,639 görüntüler.</span><span class="sxs-lookup"><span data-stu-id="95d6e-108">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>

<span data-ttu-id="95d6e-109">Taşma denetimi etkinleştirilebilir derleyici seçenekleri, ortamı yapılandırması veya kullanımı `checked` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="95d6e-109">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="95d6e-110">Aşağıdaki örnek nasıl kullanılacağını gösteren bir `checked` ifade veya `checked` çalışma zamanında önceki toplamı tarafından üretilen taşma algılamak için blok.</span><span class="sxs-lookup"><span data-stu-id="95d6e-110">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="95d6e-111">Örneklerin her ikisi de bir taşma özel durumu oluşturun.</span><span class="sxs-lookup"><span data-stu-id="95d6e-111">Both examples raise an overflow exception.</span></span>

[!code-csharp[csrefKeywordsChecked#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#4)]

<span data-ttu-id="95d6e-112">[Denetlenmeyen](../../../csharp/language-reference/keywords/unchecked.md) anahtar sözcüğü, taşma denetimi önlemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="95d6e-112">The [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword can be used to prevent overflow checking.</span></span>

## <a name="example"></a><span data-ttu-id="95d6e-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="95d6e-113">Example</span></span>

<span data-ttu-id="95d6e-114">Bu örnek nasıl kullanılacağını gösterir `checked` taşma çalışma zamanında denetimini etkinleştirmek için.</span><span class="sxs-lookup"><span data-stu-id="95d6e-114">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>

[!code-csharp[csrefKeywordsChecked#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="95d6e-115">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="95d6e-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="95d6e-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="95d6e-116">See also</span></span>

- [<span data-ttu-id="95d6e-117">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="95d6e-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="95d6e-118">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="95d6e-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="95d6e-119">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="95d6e-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="95d6e-120">İşaretli ve İşaretsiz</span><span class="sxs-lookup"><span data-stu-id="95d6e-120">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)
- [<span data-ttu-id="95d6e-121">unchecked</span><span class="sxs-lookup"><span data-stu-id="95d6e-121">unchecked</span></span>](../../../csharp/language-reference/keywords/unchecked.md)
