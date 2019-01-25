---
title: bool anahtar sözcüğü - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 958b58b31193dbf4c03709e4ab7ba38f7f30e0ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590492"
---
# <a name="bool-c-reference"></a><span data-ttu-id="50520-102">bool (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="50520-102">bool (C# Reference)</span></span>

<span data-ttu-id="50520-103">`bool` Anahtar sözcüğü, bir diğer adını <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50520-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="50520-104">Boole değerleri depolamak üzere değişkenler bildirmek için kullanılır: [true](true-literal.md) ve [false](false-literal.md).</span><span class="sxs-lookup"><span data-stu-id="50520-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="50520-105">Bir değeri de olabilir bir Boolean değişkeni gerektirip gerektirmediğini `null`, kullanın `bool?`.</span><span class="sxs-lookup"><span data-stu-id="50520-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="50520-106">Daha fazla bilgi için [bool? türü](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) bölümünü [boş değer atanabilir türleri kullanma](../../programming-guide/nullable-types/using-nullable-types.md) makalesi.</span><span class="sxs-lookup"><span data-stu-id="50520-106">For more information, see [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="50520-107">Sabit değerler</span><span class="sxs-lookup"><span data-stu-id="50520-107">Literals</span></span>

<span data-ttu-id="50520-108">Bir Boolean değerine atayabilirsiniz bir `bool` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="50520-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="50520-109">İçin değerlendirilen bir ifade de atayabilirsiniz `bool` için bir `bool` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="50520-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="50520-110">Varsayılan değer olan bir `bool` değişkendir `false`.</span><span class="sxs-lookup"><span data-stu-id="50520-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="50520-111">Varsayılan değer olan bir `bool?` değişkendir `null`.</span><span class="sxs-lookup"><span data-stu-id="50520-111">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="50520-112">Dönüşümler</span><span class="sxs-lookup"><span data-stu-id="50520-112">Conversions</span></span>

<span data-ttu-id="50520-113">C++ ' türünde bir değer `bool` türün değerine dönüştürülebilir `int`; diğer bir deyişle, `false` Sıfıra eşdeğer olan ve `true` sıfır olmayan değerlere eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="50520-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="50520-114">C# ' ta yoktur arasında dönüştürme `bool` türü ve diğer türleri.</span><span class="sxs-lookup"><span data-stu-id="50520-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="50520-115">Örneğin, aşağıdaki `if` ifadesi C# içinde geçerli değil:</span><span class="sxs-lookup"><span data-stu-id="50520-115">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="50520-116">Türünde bir değişken test etmek için `int`, açıkça gibi sıfır, bir değer gibi karşılaştırın gerekir:</span><span class="sxs-lookup"><span data-stu-id="50520-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="50520-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="50520-117">Example</span></span>

<span data-ttu-id="50520-118">Bu örnekte, bir karakter klavyeden girmeniz ve program, girdi karakteri bir harf olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="50520-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="50520-119">Bir harf ise, küçük harfler veya büyük olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="50520-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="50520-120">Bu denetimler ile gerçekleştirilen <xref:System.Char.IsLetter%2A>, ve <xref:System.Char.IsLower%2A>, hangi iade her ikisi de `bool` türü:</span><span class="sxs-lookup"><span data-stu-id="50520-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="50520-121">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="50520-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="50520-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="50520-122">See also</span></span>

- [<span data-ttu-id="50520-123">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="50520-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="50520-124">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="50520-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="50520-125">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="50520-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="50520-126">Tam Sayı Türleri Tablosu</span><span class="sxs-lookup"><span data-stu-id="50520-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="50520-127">Yerleşik Türler Tablosu</span><span class="sxs-lookup"><span data-stu-id="50520-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="50520-128">Örtük Sayısal Dönüştürmeler Tablosu</span><span class="sxs-lookup"><span data-stu-id="50520-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="50520-129">Açık Sayısal Dönüştürmeler Tablosu</span><span class="sxs-lookup"><span data-stu-id="50520-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
