---
title: params anahtar sözcüğü - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 772c8da879eeccbe484c631a47de7fe8a32ec8d2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633577"
---
# <a name="params-c-reference"></a><span data-ttu-id="56149-102">params (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="56149-102">params (C# Reference)</span></span>

<span data-ttu-id="56149-103">Kullanarak `params` belirtebileceğiniz anahtar sözcüğü, bir [yöntem parametresi](method-parameters.md) , değişken sayıda bağımsız değişken alır.</span><span class="sxs-lookup"><span data-stu-id="56149-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span>

<span data-ttu-id="56149-104">Parametre bildiriminde belirtilen türde bağımsız değişkenleri dizisini belirtilen türdeki bağımsız değişkenlerin virgülle ayrılmış bir liste gönderebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56149-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="56149-105">Ayrıca, herhangi bir bağımsız değişken gönderebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56149-105">You also can send no arguments.</span></span> <span data-ttu-id="56149-106">Hiçbir bağımsız değişken uzunluğu gönderirseniz `params` sıfır listesidir.</span><span class="sxs-lookup"><span data-stu-id="56149-106">If you send no arguments, the length of the `params` list is zero.</span></span>

<span data-ttu-id="56149-107">Ek parametre sonra izin verilen `params` anahtar sözcüğü bir yöntem bildiriminde ve tek `params` anahtar sözcüğü bir metodun bildiriminde izin verilir.</span><span class="sxs-lookup"><span data-stu-id="56149-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="56149-108">Bildirilen türü `params` parametresi, aşağıdaki örnekte gösterildiği gibi bir tek boyutlu bir dizi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="56149-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="56149-109">Aksi halde bir derleyici hatası [CS0225](../../misc/cs0225.md) gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="56149-109">Otherwise, a compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

## <a name="example"></a><span data-ttu-id="56149-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="56149-110">Example</span></span>

<span data-ttu-id="56149-111">Aşağıdaki örnek, bağımsız değişkenleri göndermenin çeşitli yollarını gösterir bir `params` parametresi.</span><span class="sxs-lookup"><span data-stu-id="56149-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a><span data-ttu-id="56149-112">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="56149-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="56149-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="56149-113">See also</span></span>

- [<span data-ttu-id="56149-114">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="56149-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="56149-115">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="56149-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="56149-116">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="56149-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="56149-117">Yöntem Parametreleri</span><span class="sxs-lookup"><span data-stu-id="56149-117">Method Parameters</span></span>](method-parameters.md)
