---
title: Tanımlayıcı adları
description: C# programlama dilinin geçerli tanımlayıcı adları kurallarını öğrenin.
ms.date: 08/21/2018
ms.openlocfilehash: 2147b3846d4ba6d5471b81448489c6d716e3cd61
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606958"
---
# <a name="identifier-names"></a><span data-ttu-id="3fa02-103">Tanımlayıcı adları</span><span class="sxs-lookup"><span data-stu-id="3fa02-103">Identifier names</span></span>

<span data-ttu-id="3fa02-104">Bir **tanımlayıcı** atama türü (sınıf, arabirim, yapı, temsilci veya enum), üye, değişken veya ad alanı adı.</span><span class="sxs-lookup"><span data-stu-id="3fa02-104">An **identifier** is the name you assign to a type (class, interface, struct, delegate, or enum), member, variable, or namespace.</span></span> <span data-ttu-id="3fa02-105">Geçerli tanımlayıcıları şu kurallara uymalıdır:</span><span class="sxs-lookup"><span data-stu-id="3fa02-105">Valid identifiers must follow these rules:</span></span>

- <span data-ttu-id="3fa02-106">Tanımlayıcılar, bir harf ile başlamalı veya `_`.</span><span class="sxs-lookup"><span data-stu-id="3fa02-106">Identifiers must start with a letter, or `_`.</span></span>
- <span data-ttu-id="3fa02-107">Tanımlayıcılar, Unicode harf karakterler, ondalık basamak karakteri, Unicode karakter bağlanma, Unicode karakter birleştirme veya Unicode karakter biçimlendirme içerebilir.</span><span class="sxs-lookup"><span data-stu-id="3fa02-107">Identifiers may contain Unicode letter characters, decimal digit characters, Unicode connecting characters, Unicode combining characters, or Unicode formatting characters.</span></span> <span data-ttu-id="3fa02-108">Unicode kategorileri hakkında daha fazla bilgi için bkz. [Unicode kategorisi veritabanı](https://www.unicode.org/reports/tr44/).</span><span class="sxs-lookup"><span data-stu-id="3fa02-108">For more information on Unicode categories, see the [Unicode Category Database](https://www.unicode.org/reports/tr44/).</span></span>
<span data-ttu-id="3fa02-109">C# anahtar sözcüklerini kullanarak eşleşen tanımlayıcıları bildirebilirsiniz `@` tanımlayıcısını öneke.</span><span class="sxs-lookup"><span data-stu-id="3fa02-109">You can declare identifiers that match C# keywords by using the `@` prefix on the identifier.</span></span> <span data-ttu-id="3fa02-110">`@` Tanımlayıcı adı bir parçası değil.</span><span class="sxs-lookup"><span data-stu-id="3fa02-110">The `@` is not part of the identifier name.</span></span> <span data-ttu-id="3fa02-111">Örneğin, `@if` bildirir adlandırılmış bir tanımlayıcı `if`.</span><span class="sxs-lookup"><span data-stu-id="3fa02-111">For example, `@if` declares an identifier named `if`.</span></span> <span data-ttu-id="3fa02-112">Bunlar [verbatim tanımlayıcıları](../../language-reference/tokens/verbatim.md) öncelikli olarak birlikte çalışabilirlik için diğer dillerde bildirilen tanımlayıcılarına sahip olan.</span><span class="sxs-lookup"><span data-stu-id="3fa02-112">These [verbatim identifiers](../../language-reference/tokens/verbatim.md) are primarily for interoperability with identifiers declared in other languages.</span></span>

<span data-ttu-id="3fa02-113">Geçerli tanımlayıcıları eksiksiz bir açıklaması için bkz. [tanımlayıcıları C# dil belirtimi konudaki](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span><span class="sxs-lookup"><span data-stu-id="3fa02-113">For a complete definition of valid identifiers, see the [Identifiers topic in the C# Language Specification](../../../../_csharplang/spec/lexical-structure.md#identifiers).</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="3fa02-114">Adlandırma kuralları</span><span class="sxs-lookup"><span data-stu-id="3fa02-114">Naming conventions</span></span>

<span data-ttu-id="3fa02-115">Kurallarının yanı sıra, kullanılabilen birkaç tanımlayıcısının [adlandırma kuralları](../../../standard/design-guidelines/naming-guidelines.md) .NET API'lerini kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3fa02-115">In addition to the rules, there are a number of identifier [naming conventions](../../../standard/design-guidelines/naming-guidelines.md) used throughout the .NET APIs.</span></span> <span data-ttu-id="3fa02-116">Kural gereği, C# programları kullanım `PascalCase` tür adları ad alanları ve tüm genel üyeler için.</span><span class="sxs-lookup"><span data-stu-id="3fa02-116">By convention, C# programs use `PascalCase` for type names, namespaces, and all public members.</span></span> <span data-ttu-id="3fa02-117">Ayrıca, aşağıdaki kurallar ortaktır:</span><span class="sxs-lookup"><span data-stu-id="3fa02-117">In addition, the following conventions are common:</span></span>

- <span data-ttu-id="3fa02-118">Büyük harfle adları başlangıç arabirim `I`.</span><span class="sxs-lookup"><span data-stu-id="3fa02-118">Interface names start with a capital `I`.</span></span>
- <span data-ttu-id="3fa02-119">Öznitelik türlerini uç sözcüğünün `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="3fa02-119">Attribute types end with the word `Attribute`.</span></span>
- <span data-ttu-id="3fa02-120">Numaralandırma türleri için bayrakları olmayan bayrakları için tekil bir isim ve çoğul bir isim kullanın.</span><span class="sxs-lookup"><span data-stu-id="3fa02-120">Enum types use a singular noun for non-flags, and a plural noun for flags.</span></span>
- <span data-ttu-id="3fa02-121">Tanımlayıcılar, bu iki ardışık içermemelidir `_` karakter.</span><span class="sxs-lookup"><span data-stu-id="3fa02-121">Identifiers should not contain two consecutive `_` characters.</span></span> <span data-ttu-id="3fa02-122">Bu adlar, derleyicinin ürettiği tanımlayıcıları için ayrılmıştır.</span><span class="sxs-lookup"><span data-stu-id="3fa02-122">Those names are reserved for compiler generated identifiers.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3fa02-123">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="3fa02-123">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3fa02-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3fa02-124">See also</span></span>

- [<span data-ttu-id="3fa02-125">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="3fa02-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3fa02-126">C# Programı İçinde</span><span class="sxs-lookup"><span data-stu-id="3fa02-126">Inside a C# Program</span></span>](../inside-a-program/index.md)
- [<span data-ttu-id="3fa02-127">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="3fa02-127">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="3fa02-128">Sınıflar</span><span class="sxs-lookup"><span data-stu-id="3fa02-128">Classes</span></span>](../classes-and-structs/classes.md)
- [<span data-ttu-id="3fa02-129">Yapılar</span><span class="sxs-lookup"><span data-stu-id="3fa02-129">Structs</span></span>](../classes-and-structs/structs.md)
- [<span data-ttu-id="3fa02-130">Ad Alanları</span><span class="sxs-lookup"><span data-stu-id="3fa02-130">Namespaces</span></span>](../namespaces/index.md)
- [<span data-ttu-id="3fa02-131">Arabirimler</span><span class="sxs-lookup"><span data-stu-id="3fa02-131">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="3fa02-132">Temsilciler</span><span class="sxs-lookup"><span data-stu-id="3fa02-132">Delegates</span></span>](../delegates/index.md)
