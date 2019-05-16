---
title: try-catch-finally - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 66f24994c7fcd2037887507bae65f590e4f90019
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633871"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="7b424-102">try-catch-finally (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="7b424-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="7b424-103">Bir ortak kullanımı da, `catch` ve `finally` elde edilir ve kaynakları birlikte olan bir `try` engelleme, olağanüstü durumlarda içeren bir `catch` engelleyin ve kaynakları serbest `finally` blok.</span><span class="sxs-lookup"><span data-stu-id="7b424-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="7b424-104">Daha fazla bilgi ve yeniden özel durumları atma ilişkin örnekler için bkz. [try-catch](try-catch.md) ve [özel durumları atma](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="7b424-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="7b424-105">Hakkında daha fazla bilgi için `finally` engellemek için bkz: [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="7b424-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="7b424-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="7b424-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="7b424-107">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="7b424-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7b424-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7b424-108">See also</span></span>

- [<span data-ttu-id="7b424-109">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="7b424-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7b424-110">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="7b424-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7b424-111">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="7b424-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="7b424-112">try, throw ve catch Deyimleri (C++)</span><span class="sxs-lookup"><span data-stu-id="7b424-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="7b424-113">Özel Durum İşleme Deyimleri</span><span class="sxs-lookup"><span data-stu-id="7b424-113">Exception Handling Statements</span></span>](exception-handling-statements.md)
- [<span data-ttu-id="7b424-114">throw</span><span class="sxs-lookup"><span data-stu-id="7b424-114">throw</span></span>](throw.md)
- [<span data-ttu-id="7b424-115">Nasıl yapılır: Açıkça özel durumlar oluşturma</span><span class="sxs-lookup"><span data-stu-id="7b424-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="7b424-116">using Deyimi</span><span class="sxs-lookup"><span data-stu-id="7b424-116">using Statement</span></span>](using-statement.md)
