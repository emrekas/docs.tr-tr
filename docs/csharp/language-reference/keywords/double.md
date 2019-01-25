---
title: double anahtar sözcüğü - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
ms.openlocfilehash: 50e11e8547c2887ace677d2c86dcf055326ff9a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708161"
---
# <a name="double-c-reference"></a><span data-ttu-id="de72d-102">double (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="de72d-102">double (C# Reference)</span></span>

<span data-ttu-id="de72d-103">`double` Anahtar sözcüğü, 64-bit kayan nokta değerlerini depolayan bir basit türü gösterir.</span><span class="sxs-lookup"><span data-stu-id="de72d-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="de72d-104">İçin yaklaşık aralık ve duyarlık aşağıdaki tabloda gösterilmektedir `double` türü.</span><span class="sxs-lookup"><span data-stu-id="de72d-104">The following table shows the precision and approximate range for the `double` type.</span></span>

|<span data-ttu-id="de72d-105">Tür</span><span class="sxs-lookup"><span data-stu-id="de72d-105">Type</span></span>|<span data-ttu-id="de72d-106">Yaklaşık aralık</span><span class="sxs-lookup"><span data-stu-id="de72d-106">Approximate range</span></span>|<span data-ttu-id="de72d-107">Duyarlık</span><span class="sxs-lookup"><span data-stu-id="de72d-107">Precision</span></span>|<span data-ttu-id="de72d-108">.NET türü</span><span class="sxs-lookup"><span data-stu-id="de72d-108">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`double`|<span data-ttu-id="de72d-109">±5.0 × 10<sup>−324</sup> ±1.7 × 10 için<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="de72d-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="de72d-110">yaklaşık 15-17 basamak</span><span class="sxs-lookup"><span data-stu-id="de72d-110">~15-17 digits</span></span>|<xref:System.Double?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="de72d-111">Sabit değerler</span><span class="sxs-lookup"><span data-stu-id="de72d-111">Literals</span></span>

<span data-ttu-id="de72d-112">Varsayılan olarak, atama işlecinin sağ tarafında gerçek sayısal bir dize olarak işlem görür `double`.</span><span class="sxs-lookup"><span data-stu-id="de72d-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="de72d-113">Ancak, tam sayı olarak kabul edilmesini isterseniz `double`, sonek d ya da D, örneğin kullanın:</span><span class="sxs-lookup"><span data-stu-id="de72d-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>

```csharp
double x = 3D;
```

## <a name="conversions"></a><span data-ttu-id="de72d-114">Dönüşümler</span><span class="sxs-lookup"><span data-stu-id="de72d-114">Conversions</span></span>

<span data-ttu-id="de72d-115">Tamsayı sayısal türleri ve kayan nokta türleri bir ifadede karıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="de72d-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="de72d-116">Bu durumda, tamsayı türleri için kayan nokta türleri dönüştürülür.</span><span class="sxs-lookup"><span data-stu-id="de72d-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="de72d-117">İfadenin değerlendirilmesi aşağıdaki kurallara göre gerçekleştirilir:</span><span class="sxs-lookup"><span data-stu-id="de72d-117">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="de72d-118">Kayan nokta türlerinden biri ise `double`, ifadenin değerlendirdiği `double`, veya [bool](../../../csharp/language-reference/keywords/bool.md) karşılaştırmalar ilişkisel ve eşitlik karşılaştırmaları.</span><span class="sxs-lookup"><span data-stu-id="de72d-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../../../csharp/language-reference/keywords/bool.md) in relational comparisons and comparisons for equality.</span></span>

- <span data-ttu-id="de72d-119">Yoksa hiçbir `double` türü olarak değerlendirilen ifade, [float](../../../csharp/language-reference/keywords/float.md), veya [bool](../../../csharp/language-reference/keywords/bool.md) karşılaştırmalar ilişkisel ve eşitlik karşılaştırmaları.</span><span class="sxs-lookup"><span data-stu-id="de72d-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or to [bool](../../../csharp/language-reference/keywords/bool.md) in relational comparisons and comparisons for equality.</span></span>

 <span data-ttu-id="de72d-120">Bir kayan nokta ifadesi, aşağıdaki adımlardan birini değerleri içerebilir:</span><span class="sxs-lookup"><span data-stu-id="de72d-120">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="de72d-121">Pozitif ve negatif sıfır.</span><span class="sxs-lookup"><span data-stu-id="de72d-121">Positive and negative zero.</span></span>

- <span data-ttu-id="de72d-122">Pozitif ve negatif sonsuz.</span><span class="sxs-lookup"><span data-stu-id="de72d-122">Positive and negative infinity.</span></span>

- <span data-ttu-id="de72d-123">Değer bir sayı değil (NaN).</span><span class="sxs-lookup"><span data-stu-id="de72d-123">Not-a-Number value (NaN).</span></span>

- <span data-ttu-id="de72d-124">Sıfır olmayan değerler sınırlı kümesi.</span><span class="sxs-lookup"><span data-stu-id="de72d-124">The finite set of nonzero values.</span></span>

<span data-ttu-id="de72d-125">Bu değerler hakkında daha fazla bilgi için bkz. IEEE standardı ikili Floating-Point aritmetik, kullanılabilir [IEEE](https://www.ieee.org) Web sitesi.</span><span class="sxs-lookup"><span data-stu-id="de72d-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) Web site.</span></span>

## <a name="example"></a><span data-ttu-id="de72d-126">Örnek</span><span class="sxs-lookup"><span data-stu-id="de72d-126">Example</span></span>

<span data-ttu-id="de72d-127">Aşağıdaki örnekte, bir [int](../../../csharp/language-reference/keywords/int.md), [kısa](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md)ve `double` vererek birlikte eklenen bir `double` sonucu.</span><span class="sxs-lookup"><span data-stu-id="de72d-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>

[!code-csharp[csrefKeywordsTypes#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="de72d-128">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="de72d-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="de72d-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="de72d-129">See also</span></span>

- [<span data-ttu-id="de72d-130">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="de72d-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="de72d-131">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="de72d-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="de72d-132">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="de72d-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="de72d-133">Varsayılan Değerler Tablosu</span><span class="sxs-lookup"><span data-stu-id="de72d-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)
- [<span data-ttu-id="de72d-134">Yerleşik Türler Tablosu</span><span class="sxs-lookup"><span data-stu-id="de72d-134">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="de72d-135">Kayan Nokta Türleri Tablosu</span><span class="sxs-lookup"><span data-stu-id="de72d-135">Floating-Point Types Table</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)
- [<span data-ttu-id="de72d-136">Örtük Sayısal Dönüştürmeler Tablosu</span><span class="sxs-lookup"><span data-stu-id="de72d-136">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="de72d-137">Açık Sayısal Dönüştürmeler Tablosu</span><span class="sxs-lookup"><span data-stu-id="de72d-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
