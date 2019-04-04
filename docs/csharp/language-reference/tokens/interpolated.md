---
title: $ - dize ilişkilendirme - C# başvurusu
ms.custom: seodec18
description: Dize ilişkilendirme, daha geleneksel dize bileşik biçimlendirme dizesi çıkış biçimine daha okunabilir ve kullanışlı bir söz dizimi sağlar.
ms.date: 03/26/2018
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: 64728182fe0b758f8da668d19761305e2001f1a5
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920902"
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="159be-103">$ - dize ilişkilendirme (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="159be-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="159be-104">`$` Özel karakter tanımlayan bir dize sabit değeri olarak bir *ilişkilendirilmiş bir dizedir*.</span><span class="sxs-lookup"><span data-stu-id="159be-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="159be-105">İçerebilir bir dize sabit değeri ilişkilendirilmiş bir dizedir *ilişkilendirilmiş ifade*.</span><span class="sxs-lookup"><span data-stu-id="159be-105">An interpolated string is a string literal that might contain *interpolated expressions*.</span></span> <span data-ttu-id="159be-106">İlişkilendirilmiş dize bir sonuç dizesine çözüldüğünde, ilişkilendirilmiş ifadeler öğeleriyle ifade sonuçları dize temsillerini tarafından değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="159be-106">When an interpolated string is resolved to a result string, items with interpolated expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="159be-107">Bu özellik, C# 6 ve sonraki sürümlerinde dil kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="159be-107">This feature is available in C# 6 and later versions of the language.</span></span>

<span data-ttu-id="159be-108">Dize ilişkilendirme, biçimlendirilmiş dize değerinden oluşturmak için daha okunabilir ve kullanışlı bir söz dizimi sağlar bir [bileşik biçimlendirme dizesi](../../../standard/base-types/composite-formatting.md) özelliği.</span><span class="sxs-lookup"><span data-stu-id="159be-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="159be-109">Aşağıdaki örnek, aynı çıktı oluşturmak için her iki özellik kullanır:</span><span class="sxs-lookup"><span data-stu-id="159be-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a><span data-ttu-id="159be-110">Bir aradeğerlendirme dizesinde yapısı</span><span class="sxs-lookup"><span data-stu-id="159be-110">Structure of an interpolated string</span></span>

<span data-ttu-id="159be-111">Bir dize ilişkilendirilmiş dize sabit değeri belirlemek için onunla önüne ekleyin `$` simgesi.</span><span class="sxs-lookup"><span data-stu-id="159be-111">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="159be-112">Arasında beyaz boşluk olamaz `$` ve `"` bir dize sabit değeri başlar.</span><span class="sxs-lookup"><span data-stu-id="159be-112">You cannot have any white space between the `$` and the `"` that starts a string literal.</span></span> <span data-ttu-id="159be-113">Bunun yapılması, bir derleme zamanı hatasına neden olur.</span><span class="sxs-lookup"><span data-stu-id="159be-113">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="159be-114">Bir öğe ile ilişkilendirilmiş ifade yapısı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="159be-114">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="159be-115">Köşeli parantezler içindeki öğeler isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="159be-115">Elements in square brackets are optional.</span></span> <span data-ttu-id="159be-116">Aşağıdaki tablo her öğeyi açıklar:</span><span class="sxs-lookup"><span data-stu-id="159be-116">The following table describes each element:</span></span>

|<span data-ttu-id="159be-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="159be-117">Element</span></span>|<span data-ttu-id="159be-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="159be-118">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="159be-119">Biçimlendirilecek bir sonuç üretir ifade.</span><span class="sxs-lookup"><span data-stu-id="159be-119">The expression that produces a result to be formatted.</span></span> <span data-ttu-id="159be-120">Dize gösterimini `null` sonucudur <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="159be-120">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="159be-121">Sabit ifade değeri, ilişkilendirilmiş ifadenin sonucu dize gösterimi en az karakter sayısını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="159be-121">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="159be-122">Pozitif ise sağa hizalı dize gösterimi; negatif ise sola hizalıdır.</span><span class="sxs-lookup"><span data-stu-id="159be-122">If positive, the string representation is right-aligned; if negative, it's left-aligned.</span></span> <span data-ttu-id="159be-123">Daha fazla bilgi için [hizalama bileşeni](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="159be-123">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="159be-124">Deyim sonucu türü tarafından desteklenen bir biçim dizesi.</span><span class="sxs-lookup"><span data-stu-id="159be-124">A format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="159be-125">Daha fazla bilgi için [biçim dizesi bileşeni](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="159be-125">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="159be-126">Aşağıdaki örnek, yukarıda açıklanan isteğe bağlı bir biçimlendirme bileşenleri kullanır:</span><span class="sxs-lookup"><span data-stu-id="159be-126">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a><span data-ttu-id="159be-127">Özel karakterler</span><span class="sxs-lookup"><span data-stu-id="159be-127">Special characters</span></span>

<span data-ttu-id="159be-128">Bir küme ayracı, dahil etmek için "{" veya "}", bir aradeğerlendirme dizesinde tarafından üretilen metinde iki küme ayraçları kullanın "{{" veya "}}".</span><span class="sxs-lookup"><span data-stu-id="159be-128">To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="159be-129">Daha fazla bilgi için [kaçış küme ayraçları](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="159be-129">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="159be-130">İki nokta üst üste olarak (":") kullanmak için ilişkilendirilmiş ifade öğenin özel anlama sahip bir [koşullu işleç](../operators/conditional-operator.md) , parantez içindeki ifade bir ilişkilendirilmiş ifadede alın.</span><span class="sxs-lookup"><span data-stu-id="159be-130">As the colon (":") has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="159be-131">Aşağıdaki örnek, sonuç dizesinde ayraç ekleme ve bir ilişkilendirilmiş ifadede koşullu bir işleç kullanma işlemini gösterir:</span><span class="sxs-lookup"><span data-stu-id="159be-131">The following example shows how to include a brace in a result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="159be-132">Verbatim ilişkilendirilmiş bir dize ile başlayan `$` karakteri ve ardından `@` karakter.</span><span class="sxs-lookup"><span data-stu-id="159be-132">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="159be-133">Harfi harfine dizeler hakkında daha fazla bilgi için bkz: [dize](../keywords/string.md) ve [tam tanımlayıcı](verbatim.md) konuları.</span><span class="sxs-lookup"><span data-stu-id="159be-133">For more information about verbatim strings, see the [string](../keywords/string.md) and [verbatim identifier](verbatim.md) topics.</span></span>

> [!NOTE]
> <span data-ttu-id="159be-134">`$` Belirteci önce görünmelidir `@` verbatim ilişkilendirilmiş dize belirteci.</span><span class="sxs-lookup"><span data-stu-id="159be-134">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a><span data-ttu-id="159be-135">Örtük dönüşümler ve belirterek `IFormatProvider` uygulama</span><span class="sxs-lookup"><span data-stu-id="159be-135">Implicit conversions and specifying `IFormatProvider` implementation</span></span>

<span data-ttu-id="159be-136">Bir aradeğerlendirme dizesinde üç örtük dönüştürmelerine vardır:</span><span class="sxs-lookup"><span data-stu-id="159be-136">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="159be-137">Bir araya alınmış dizeye dönüştürme bir <xref:System.String> ilişkilendirilmiş ifade ile ilişkilendirilmiş dize çözümü sonucu olan örneği öğelerini sonuçları düzgün şekilde biçimlendirilmiş dize temsillerini ile değiştiriliyor.</span><span class="sxs-lookup"><span data-stu-id="159be-137">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="159be-138">Bu dönüştürme, geçerli kültürü kullanır.</span><span class="sxs-lookup"><span data-stu-id="159be-138">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="159be-139">Bir araya alınmış dizeye dönüştürme bir <xref:System.FormattableString> Biçimlendirilecek ifade sonuçları ile birlikte bir bileşik biçimlendirme dizesi temsil eden örneği.</span><span class="sxs-lookup"><span data-stu-id="159be-139">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="159be-140">Kültüre özgü ile birden çok sonuç dizeleri oluşturmak için tek bir içerik sağlayan <xref:System.FormattableString> örneği.</span><span class="sxs-lookup"><span data-stu-id="159be-140">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="159be-141">Yapmak için aşağıdaki yöntemlerden birini arayın:</span><span class="sxs-lookup"><span data-stu-id="159be-141">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="159be-142">A <xref:System.FormattableString.ToString> için bir sonuç dizesi oluşturur aşırı <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="159be-142">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="159be-143">Bir <xref:System.FormattableString.Invariant%2A> için bir sonuç dizesi oluşturur yöntemi <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="159be-143">An <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="159be-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> yönteminin belirtilen kültür için bir sonuç dizesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="159be-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="159be-145">Ayrıca <xref:System.FormattableString.ToString(System.IFormatProvider)> kullanıcı tanımlı bir uygulamasını sağlamak üzere yöntemi <xref:System.IFormatProvider> özel biçimlendirmeyi destekleyen arabirimi.</span><span class="sxs-lookup"><span data-stu-id="159be-145">You also can use the <xref:System.FormattableString.ToString(System.IFormatProvider)> method to provide a user-defined implementation of the <xref:System.IFormatProvider> interface that supports custom formatting.</span></span> <span data-ttu-id="159be-146">Daha fazla bilgi için [Icustomformatter ile özel biçimlendirme](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span><span class="sxs-lookup"><span data-stu-id="159be-146">For more information, see [Custom Formatting with ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span></span>

1. <span data-ttu-id="159be-147">Bir araya alınmış dizeye dönüştürme bir <xref:System.IFormattable> Ayrıca, birden çok sonuç oluşturmanıza olanak sağlayan örnek dizeleri tek bir kültüre özgü içerikle <xref:System.IFormattable> örneği.</span><span class="sxs-lookup"><span data-stu-id="159be-147">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="159be-148">Aşağıdaki örnek örtük olarak dönüştürülmesine kullanır <xref:System.FormattableString> kültüre özgü sonuç dizeleri oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="159be-148">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a><span data-ttu-id="159be-149">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="159be-149">Additional resources</span></span>

<span data-ttu-id="159be-150">Dize ilişkilendirme için yeni başlıyorsanız bkz [dize ilişkilendirme, C# ](../../tutorials/exploration/interpolated-strings.yml) etkileşimli öğretici.</span><span class="sxs-lookup"><span data-stu-id="159be-150">If you are new to string interpolation, see the [String interpolation in C#](../../tutorials/exploration/interpolated-strings.yml) interactive tutorial.</span></span> <span data-ttu-id="159be-151">Ya da deneyebilirsiniz [dize ilişkilendirme, C# ](../../tutorials/string-interpolation.md) makinenizde yerel olarak öğretici.</span><span class="sxs-lookup"><span data-stu-id="159be-151">Or you can try the  [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial locally on your machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="159be-152">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="159be-152">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="159be-153">Bileşik biçimlendirme</span><span class="sxs-lookup"><span data-stu-id="159be-153">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="159be-154">Sayısal sonuçlar tablosunu biçimlendirme</span><span class="sxs-lookup"><span data-stu-id="159be-154">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="159be-155">Dizeler</span><span class="sxs-lookup"><span data-stu-id="159be-155">Strings</span></span>](../../programming-guide/strings/index.md)
- [<span data-ttu-id="159be-156">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="159be-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="159be-157">C# Özel Karakterleri</span><span class="sxs-lookup"><span data-stu-id="159be-157">C# Special Characters</span></span>](index.md)
- [<span data-ttu-id="159be-158">C# Başvurusu</span><span class="sxs-lookup"><span data-stu-id="159be-158">C# Reference</span></span>](../index.md)
