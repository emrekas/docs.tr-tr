---
title: if-else - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: ef25b3fb5657d833bbccf5bace71e049623476c9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294425"
---
# <a name="if-else-c-reference"></a><span data-ttu-id="7e7f8-102">if-else (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="7e7f8-102">if-else (C# Reference)</span></span>

<span data-ttu-id="7e7f8-103">Bir `if` deyimi çalıştırmak için hangi deyimi, bir Boolean ifadesinin değerine göre tanımlar.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-103">An `if` statement identifies which statement to run based on the value of a Boolean expression.</span></span> <span data-ttu-id="7e7f8-104">Aşağıdaki örnekte, `bool` değişkeni `condition` ayarlanır `true` ve ardından iade `if` deyimi.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-104">In the following example, the `bool` variable `condition` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="7e7f8-105">Çıktı `The variable is set to true.`.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-105">The output is `The variable is set to true.`.</span></span>

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

<span data-ttu-id="7e7f8-106">Bunları yerleştirerek bu konudaki örnekler çalıştırabilirsiniz `Main` bir konsol uygulaması yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-106">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>

<span data-ttu-id="7e7f8-107">Bir `if` C# deyimi, aşağıdaki örnekte gösterildiği gibi iki form alabilir.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-107">An `if` statement in C# can take two forms, as the following example shows.</span></span>

```csharp
// if-else statement
if (condition)
{
    then-statement;
}
else
{
    else-statement;
}
// Next statement in the program.

// if statement without an else
if (condition)
{
    then-statement;
}
// Next statement in the program.
```

<span data-ttu-id="7e7f8-108">İçinde bir `if-else` ifadesi varsa `condition` true olarak değerlendirilen `then-statement` çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-108">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="7e7f8-109">Varsa `condition` false ise `else-statement` çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-109">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="7e7f8-110">Çünkü `condition` aynı anda true ve false olamaz `then-statement` ve `else-statement` , bir `if-else` deyimi hiçbir zaman hem de çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-110">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="7e7f8-111">Sonra `then-statement` veya `else-statement` çalıştığında, Denetim, sonra sonraki deyime aktarılır `if` deyimi.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-111">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="7e7f8-112">İçinde bir `if` deyimi içermeyen bir `else` deyimi, `condition` true ise `then-statement` çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-112">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="7e7f8-113">Varsa `condition` yanlış denetimi sonra sonraki deyime aktarılır `if` deyimi.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-113">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="7e7f8-114">Hem `then-statement` ve `else-statement` tek bir deyim veya küme ayraçları içine alınmış birden çok deyim içerebilir (`{}`).</span><span class="sxs-lookup"><span data-stu-id="7e7f8-114">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="7e7f8-115">Tek bir deyim için Küme ayraçları isteğe bağlıdır ancak önerilir.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-115">For a single statement, the braces are optional but recommended.</span></span>

<span data-ttu-id="7e7f8-116">Deyim ya da deyimlerinde `then-statement` ve `else-statement` başka dahil olmak üzere, herhangi bir türden olabilir `if` deyimi özgün içinde iç içe `if` deyimi.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-116">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="7e7f8-117">İçinde iç içe geçmiş `if` deyimleri, her `else` yan tümcesi ait son `if` karşılık gelen yok `else`.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-117">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="7e7f8-118">Aşağıdaki örnekte, `Result1` her iki görünür `m > 10` ve `n > 20` true olarak değerlendirin.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-118">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="7e7f8-119">Varsa `m > 10` geçerlidir ancak `n > 20` false ise `Result2` görünür.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-119">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

<span data-ttu-id="7e7f8-120">Bunun yerine, isterseniz `Result2` olduğunda görüntülenecek `(m > 10)` başındaki ve sonundaki iç içe'kurmak için küme ayraçlarını kullanarak bu ilişkiyi belirleyebilir, yanlış `if` aşağıdaki örnekte gösterildiği gibi bir ifade.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-120">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

<span data-ttu-id="7e7f8-121">`Result2` görünür koşul `(m > 10)` yanlış olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-121">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>

## <a name="example"></a><span data-ttu-id="7e7f8-122">Örnek</span><span class="sxs-lookup"><span data-stu-id="7e7f8-122">Example</span></span>

<span data-ttu-id="7e7f8-123">Aşağıdaki örnekte, bir karakter klavyeden girmeniz ve iç içe bir programın kullandığı `if` girdi karakteri alfabetik bir karakter olup olmadığını belirlemek için deyimi.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-123">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="7e7f8-124">Girdi karakteri alfabetik bir karakter ise, programın giriş karakterin büyük harf veya küçük harf olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-124">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="7e7f8-125">Her durum için bir ileti görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-125">A message appears for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a><span data-ttu-id="7e7f8-126">Örnek</span><span class="sxs-lookup"><span data-stu-id="7e7f8-126">Example</span></span>

<span data-ttu-id="7e7f8-127">Ayrıca yuvalayabilirsiniz bir `if` başka bir blok içinde bir ifade aşağıdaki kodu kısmi gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-127">You also can nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="7e7f8-128">Örnek Yuvalar `if` iki başka blokları ve ardından bloğu içindeki deyimler.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-128">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="7e7f8-129">True veya false her blok içinde hangi koşullar açıklamaları belirtin.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-129">The comments specify which conditions are true or false in each block.</span></span>

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a><span data-ttu-id="7e7f8-130">Örnek</span><span class="sxs-lookup"><span data-stu-id="7e7f8-130">Example</span></span>

<span data-ttu-id="7e7f8-131">Aşağıdaki örnek, bir girdi karakteri küçük harf, bir büyük harf veya sayı olup olmadığını belirler.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-131">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="7e7f8-132">Üç tüm koşullar false olursa, karakterin alfasayısal bir karakter değildir.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-132">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="7e7f8-133">Örneğin, her örneği için bir ileti görüntüler.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-133">The example displays a message for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

<span data-ttu-id="7e7f8-134">Yalnızca bir deyimde başka bloğu ya da sonra blok herhangi bir geçerli ifade olabilir, koşul için geçerli bir Boole ifade kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-134">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="7e7f8-135">Kullanabileceğiniz [mantıksal işleçler](../operators/boolean-logical-operators.md) gibi `!`, `&&`, `||`, `&`, `|`, ve `^` Bileşik koşul yapma.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-135">You can use [logical operators](../operators/boolean-logical-operators.md) such as `!`, `&&`, `||`, `&`, `|`, and `^` to make compound conditions.</span></span> <span data-ttu-id="7e7f8-136">Aşağıdaki kod örnekleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-136">The following code shows examples.</span></span>

```csharp
// NOT
bool result = true;
if (!result)
{
    Console.WriteLine("The condition is true (result is false).");
}
else
{
    Console.WriteLine("The condition is false (result is true).");
}

// Short-circuit AND
int m = 9;
int n = 7;
int p = 5;
if (m >= n && m >= p)
{
    Console.WriteLine("Nothing is larger than m.");
}

// AND and NOT
if (m >= n && !(p > m))
{
    Console.WriteLine("Nothing is larger than m.");
}

// Short-circuit OR
if (m > n || m > p)
{
    Console.WriteLine("m isn't the smallest.");
}

// NOT and OR
m = 4;
if (!(m >= n || m >= p))
{
    Console.WriteLine("Now m is the smallest.");
}
// Output:
// The condition is false (result is true).
// Nothing is larger than m.
// Nothing is larger than m.
// m isn't the smallest.
// Now m is the smallest.
```

## <a name="c-language-specification"></a><span data-ttu-id="7e7f8-137">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="7e7f8-137">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7e7f8-138">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7e7f8-138">See also</span></span>

- [<span data-ttu-id="7e7f8-139">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="7e7f8-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7e7f8-140">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="7e7f8-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7e7f8-141">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="7e7f8-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="7e7f8-142">?: İşleç</span><span class="sxs-lookup"><span data-stu-id="7e7f8-142">?: Operator</span></span>](../operators/conditional-operator.md)
- [<span data-ttu-id="7e7f8-143">if-else Deyimi (C++)</span><span class="sxs-lookup"><span data-stu-id="7e7f8-143">if-else Statement (C++)</span></span>](/cpp/cpp/if-else-statement-cpp)
- [<span data-ttu-id="7e7f8-144">switch</span><span class="sxs-lookup"><span data-stu-id="7e7f8-144">switch</span></span>](switch.md)
