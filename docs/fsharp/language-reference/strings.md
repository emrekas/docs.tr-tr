---
title: Dizeler
description: Bilgi nasıl F# 'string' türü sabit metin Unicode karakter dizisi olarak temsil eder.
ms.date: 05/16/2016
ms.openlocfilehash: c2fda4d936abab5bc3f4653613991a7f5471d81d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642079"
---
# <a name="strings"></a><span data-ttu-id="14169-103">Dizeler</span><span class="sxs-lookup"><span data-stu-id="14169-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="14169-104">Bu makaledeki API başvuru bağlantıları için MSDN sürer.</span><span class="sxs-lookup"><span data-stu-id="14169-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="14169-105">Docs.microsoft.com API başvuru tamamlanmadı.</span><span class="sxs-lookup"><span data-stu-id="14169-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="14169-106">`string` Türü sabit metin Unicode karakter dizisi olarak temsil eder.</span><span class="sxs-lookup"><span data-stu-id="14169-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="14169-107">`string` için bir diğer addır `System.String` .NET Framework'teki.</span><span class="sxs-lookup"><span data-stu-id="14169-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="14169-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="14169-108">Remarks</span></span>

<span data-ttu-id="14169-109">Dize değişmez değerleri tırnak işareti (") karakteriyle ayrılır.</span><span class="sxs-lookup"><span data-stu-id="14169-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="14169-110">Ters eğik çizgi karakteri ( \\ ) özel karakterleri kodlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="14169-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="14169-111">Ters eğik çizgi ve birlikte sonraki karakteri olarak bilinen bir *kaçış dizisi*.</span><span class="sxs-lookup"><span data-stu-id="14169-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="14169-112">Kaçış dizileri desteklenen F# dize değişmez değerleri aşağıdaki tabloda gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="14169-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="14169-113">Karakter</span><span class="sxs-lookup"><span data-stu-id="14169-113">Character</span></span>|<span data-ttu-id="14169-114">Kaçış sırası</span><span class="sxs-lookup"><span data-stu-id="14169-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="14169-115">Geri Al tuşu</span><span class="sxs-lookup"><span data-stu-id="14169-115">Backspace</span></span>|`\b`|
|<span data-ttu-id="14169-116">Yeni satır</span><span class="sxs-lookup"><span data-stu-id="14169-116">Newline</span></span>|`\n`|
|<span data-ttu-id="14169-117">satır başı</span><span class="sxs-lookup"><span data-stu-id="14169-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="14169-118">Tab</span><span class="sxs-lookup"><span data-stu-id="14169-118">Tab</span></span>|`\t`|
|<span data-ttu-id="14169-119">Ters eğik çizgi</span><span class="sxs-lookup"><span data-stu-id="14169-119">Backslash</span></span>|`\\`|
|<span data-ttu-id="14169-120">Tırnak işareti</span><span class="sxs-lookup"><span data-stu-id="14169-120">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="14169-121">Kesme işareti</span><span class="sxs-lookup"><span data-stu-id="14169-121">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="14169-122">Unicode karakter</span><span class="sxs-lookup"><span data-stu-id="14169-122">Unicode character</span></span>|<span data-ttu-id="14169-123">`\uXXXX` veya `\UXXXX` (burada `X` onaltılık basamak gösterir)</span><span class="sxs-lookup"><span data-stu-id="14169-123">`\uXXXX` or `\UXXXX` (where `X` indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="14169-124">Öncesinde, @ sembolü, değişmez değer verbatim bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="14169-124">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="14169-125">İki tırnak karakteri tek tırnak işareti karakteri yorumlanır dışında bu, herhangi bir kaçış dizileri göz ardı, anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="14169-125">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="14169-126">Ayrıca, bir dize Üçlü tırnak işareti içine alınabilir.</span><span class="sxs-lookup"><span data-stu-id="14169-126">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="14169-127">Bu durumda, çift tırnak işareti karakterleri dahil olmak üzere tüm kaçış dizileri yoksayılır.</span><span class="sxs-lookup"><span data-stu-id="14169-127">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="14169-128">Sınırlandırılmış bir katıştırılmış içeren bir dize belirtmek için ya da bir harfi harfine veya bir Üçlü alıntılanmış dize kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="14169-128">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="14169-129">Verbatim dizesi kullanıyorsanız, iki tırnak karakteri tek tırnak işareti karakteri belirtmek için belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="14169-129">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="14169-130">Üçlü tırnak içine bir dize kullanmak, bunları dize sonu Ayrıştırılmakta olmadan tek tırnak işareti karakter kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="14169-130">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="14169-131">Bu teknik, XML veya katıştırılmış tırnak işaretleri dahil diğer yapılar çalışırken yararlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="14169-131">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="14169-132">Kodda satır sonları olan dizeleri kabul edilir ve son karakter satır sonundan önce bir ters eğik çizgi karakteri olmadığı sürece satır sonları tam anlamıyla yeni satırlardan yorumlanır.</span><span class="sxs-lookup"><span data-stu-id="14169-132">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="14169-133">Ters eğik çizgi karakteri kullanıldığında sonraki satıra önde gelen boşluk yoksayılır.</span><span class="sxs-lookup"><span data-stu-id="14169-133">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="14169-134">Aşağıdaki kod bir dize üretir `str1` değeri olan `"abc\ndef"` ve bir dize `str2` değeri olan `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="14169-134">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="14169-135">Aşağıdaki gibi bir dizi benzeri sözdizimi kullanarak, bir dizedeki karakterlerin tek tek erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="14169-135">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="14169-136">Çıktı `b`.</span><span class="sxs-lookup"><span data-stu-id="14169-136">The output is `b`.</span></span>

<span data-ttu-id="14169-137">Veya, alt dizeler dizisi dilim söz dizimini kullanarak aşağıdaki kodda gösterildiği gibi ayıklayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="14169-137">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="14169-138">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="14169-138">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="14169-139">ASCII dizelerinde işaretsiz bayt sayısı, türü bir dizi temsil edebilen `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="14169-139">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="14169-140">Sonek Ekle `B` için bir ASCII dizesi olduğunu belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="14169-140">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="14169-141">Bayt dizileri ile kullanılan ASCII dize değişmez değerleri, Unicode kaçış dizileri dışında Unicode dize olarak aynı kaçış dizileri destekler.</span><span class="sxs-lookup"><span data-stu-id="14169-141">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="14169-142">Dize İşleçleri</span><span class="sxs-lookup"><span data-stu-id="14169-142">String Operators</span></span>

<span data-ttu-id="14169-143">Dizeleri birleştirmek için iki yolu vardır: kullanarak `+` işleci kullanarak veya `^` işleci.</span><span class="sxs-lookup"><span data-stu-id="14169-143">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="14169-144">`+` İşleci özellikleri işleme .NET Framework dize ile uyumluluk sağlar.</span><span class="sxs-lookup"><span data-stu-id="14169-144">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="14169-145">Aşağıdaki örnekte, dize birleştirme gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="14169-145">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="14169-146">Dize sınıfı</span><span class="sxs-lookup"><span data-stu-id="14169-146">String Class</span></span>

<span data-ttu-id="14169-147">Çünkü dize türü içinde F# aslında bir .NET Framework `System.String` yazın, tümünü `System.String` üyeleri kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="14169-147">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="14169-148">Bu içerir `+` dizeyi birleştirmek için kullanılır, operatör `Length` özelliği ve `Chars` dize Unicode karakter dizisi olarak döndüren özellik.</span><span class="sxs-lookup"><span data-stu-id="14169-148">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="14169-149">Dizeleri hakkında daha fazla bilgi için bkz. `System.String`.</span><span class="sxs-lookup"><span data-stu-id="14169-149">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="14169-150">Kullanarak `Chars` özelliği `System.String`, aşağıdaki kodda gösterildiği gibi bir dizin belirterek, bir dizedeki karakterlerin tek tek erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="14169-150">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="14169-151">String modülü</span><span class="sxs-lookup"><span data-stu-id="14169-151">String Module</span></span>

<span data-ttu-id="14169-152">Dize işleme için ek işlevler dahil `String` modülünde `FSharp.Core` ad alanı.</span><span class="sxs-lookup"><span data-stu-id="14169-152">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="14169-153">Daha fazla bilgi için [Core.String modülü](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="14169-153">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="14169-154">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="14169-154">See also</span></span>

- [<span data-ttu-id="14169-155">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="14169-155">F# Language Reference</span></span>](index.md)
