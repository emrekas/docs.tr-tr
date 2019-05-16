---
title: Özel Durum Türleri
description: Tanımlama ve kullanma hakkında bilgi edinin F# özel durum türleri.
ms.date: 05/16/2016
ms.openlocfilehash: b7203dc042c7207bca95cfd0372790bfe52e0226
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645565"
---
# <a name="exception-types"></a><span data-ttu-id="95942-103">Özel Durum Türleri</span><span class="sxs-lookup"><span data-stu-id="95942-103">Exception Types</span></span>

<span data-ttu-id="95942-104">Özel durumları iki kategorisi vardır F#: .NET özel durum türlerini ve F# özel durum türleri.</span><span class="sxs-lookup"><span data-stu-id="95942-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="95942-105">Bu konu nasıl tanımlanacağını ve kullanılacağını açıklar F# özel durum türleri.</span><span class="sxs-lookup"><span data-stu-id="95942-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="95942-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="95942-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="95942-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="95942-107">Remarks</span></span>

<span data-ttu-id="95942-108">Önceki sözdiziminde, *özel durum türü* yeni adı F# özel durum türü ve *bağımsız değişken türü* bu türde bir özel durum yükselttiğinizde sağlanabilir bir bağımsız değişken türünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="95942-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="95942-109">Bir demet türü için'ı kullanarak birden çok bağımsız değişkeni belirtebilirsiniz *bağımsız değişken türü*.</span><span class="sxs-lookup"><span data-stu-id="95942-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="95942-110">Tipik bir tanımı için bir F# özel durum aşağıdakine benzer.</span><span class="sxs-lookup"><span data-stu-id="95942-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="95942-111">Bu tür bir özel durum kullanarak oluşturabileceğiniz `raise` gibi işlev.</span><span class="sxs-lookup"><span data-stu-id="95942-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="95942-112">Kullanabileceğiniz bir F# özel durum türünü doğrudan filtreleri bir `try...with` aşağıdaki örnekte gösterildiği gibi ifade.</span><span class="sxs-lookup"><span data-stu-id="95942-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="95942-113">İle tanımladığınız özel durum türü `exception` anahtar sözcüğünü F# devralan yeni bir türdür `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="95942-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="95942-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="95942-114">See also</span></span>

- [<span data-ttu-id="95942-115">Özel Durum İşleme</span><span class="sxs-lookup"><span data-stu-id="95942-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="95942-116">Özel durumlar: `raise` işlevi</span><span class="sxs-lookup"><span data-stu-id="95942-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="95942-117">Özel durum hiyerarşisi</span><span class="sxs-lookup"><span data-stu-id="95942-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
