---
title: Desen Eşleştirme
description: Desenleri nasıl kullanıldığı hakkında bilgi edinin F# mantıksal yapıları verilerle karşılaştırmak, verileri bileşenlerine ayırmak veya verilerden bilgi ayıklamak.
ms.date: 05/16/2016
ms.openlocfilehash: bb6b41f6d15612e4a65abd4a3d5d7291d84a8f3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795466"
---
# <a name="pattern-matching"></a><span data-ttu-id="89e98-103">Desen Eşleştirme</span><span class="sxs-lookup"><span data-stu-id="89e98-103">Pattern Matching</span></span>

<span data-ttu-id="89e98-104">Desenler, dönüştürme giriş verileri kurallardır.</span><span class="sxs-lookup"><span data-stu-id="89e98-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="89e98-105">Genelinde kullanılan F# mantıksal bir yapıyla veya yapılarla, verileri karşılaştırmak için dil, verileri bileşenlerine ayırmak veya çeşitli şekillerde verilerden bilgi ayıklamak.</span><span class="sxs-lookup"><span data-stu-id="89e98-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="89e98-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="89e98-106">Remarks</span></span>

<span data-ttu-id="89e98-107">Desenler kullanılan birçok dil yapılarında gibi `match` ifade.</span><span class="sxs-lookup"><span data-stu-id="89e98-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="89e98-108">İşlevler için bağımsız değişkenler işlenirken kullanılır `let` bağlarında, lambda ifadeleri ve ilişkili özel durum işleyicileri `try...with` ifade.</span><span class="sxs-lookup"><span data-stu-id="89e98-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="89e98-109">Daha fazla bilgi için [eşleşme ifadeleri](match-expressions.md), [let bağlamaları](functions/let-bindings.md), [Lambda ifadeleri: `fun` Anahtar sözcüğü](functions/lambda-expressions-the-fun-keyword.md), ve [özel durumlar: `try...with` İfade](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="89e98-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="89e98-110">Örneğin, `match` ifade *deseni* ne kanal simgesini izleyen şeydir.</span><span class="sxs-lookup"><span data-stu-id="89e98-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="89e98-111">Her desen bir şekilde girişi dönüştürme için bir kural görür.</span><span class="sxs-lookup"><span data-stu-id="89e98-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="89e98-112">İçinde `match` ifadesinde her desen incelenene sırayla giriş veri girişinin desen ile uyumlu olup olmadığını görmek için.</span><span class="sxs-lookup"><span data-stu-id="89e98-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="89e98-113">Bir eşleşme bulunursa sonuç ifade yürütülür.</span><span class="sxs-lookup"><span data-stu-id="89e98-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="89e98-114">Bir eşleşme bulunmazsa sonraki desen kuralı test edilir.</span><span class="sxs-lookup"><span data-stu-id="89e98-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="89e98-115">İsteğe bağlı *koşul* bölümü içinde açıklanan [eşleşme ifadeleri](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="89e98-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="89e98-116">Desteklenen desenler aşağıdaki tabloda gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="89e98-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="89e98-117">Çalışma zamanında giriş her biri aşağıdaki tabloda listelenen sırayla desenleri karşı test edilir ve kodunuzda ve soldan sağa doğru desenleri için her satırında göründükleri gibi desenler yinelemeli olarak uygulandığından, öncelikle son arasındadır.</span><span class="sxs-lookup"><span data-stu-id="89e98-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="89e98-118">Ad</span><span class="sxs-lookup"><span data-stu-id="89e98-118">Name</span></span>|<span data-ttu-id="89e98-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="89e98-119">Description</span></span>|<span data-ttu-id="89e98-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="89e98-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="89e98-121">Sabit desen</span><span class="sxs-lookup"><span data-stu-id="89e98-121">Constant pattern</span></span>|<span data-ttu-id="89e98-122">Herhangi bir sayısal, karakter veya dize sabit değeri, numaralandırma sabiti veya tanımlı bir değişmez değer tanımlayıcısı</span><span class="sxs-lookup"><span data-stu-id="89e98-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="89e98-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="89e98-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="89e98-124">Tanımlayıcı desen</span><span class="sxs-lookup"><span data-stu-id="89e98-124">Identifier pattern</span></span>|<span data-ttu-id="89e98-125">Büyük/küçük harf değeri ayrılmış bir birleşim, özel durum etiketi veya etkin desen çalışması</span><span class="sxs-lookup"><span data-stu-id="89e98-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="89e98-126">Değişken deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-126">Variable pattern</span></span>|<span data-ttu-id="89e98-127">*tanımlayıcı*</span><span class="sxs-lookup"><span data-stu-id="89e98-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="89e98-128">`as` Düzeni</span><span class="sxs-lookup"><span data-stu-id="89e98-128">`as` pattern</span></span>|<span data-ttu-id="89e98-129">*Desen* olarak *tanımlayıcısı*</span><span class="sxs-lookup"><span data-stu-id="89e98-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="89e98-130">OR deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-130">OR pattern</span></span>|<span data-ttu-id="89e98-131">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="89e98-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="89e98-132">VE deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-132">AND pattern</span></span>|<span data-ttu-id="89e98-133">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="89e98-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="89e98-134">Olumsuz desen</span><span class="sxs-lookup"><span data-stu-id="89e98-134">Cons pattern</span></span>|<span data-ttu-id="89e98-135">*tanımlayıcı* :: *liste tanımlayıcısı*</span><span class="sxs-lookup"><span data-stu-id="89e98-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="89e98-136">Liste deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-136">List pattern</span></span>|<span data-ttu-id="89e98-137">[ *pattern_1*;...; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="89e98-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="89e98-138">Dizi deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-138">Array pattern</span></span>|<span data-ttu-id="89e98-139">[&#124; *pattern_1*;..; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="89e98-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="89e98-140">Parantezlenmiş desen</span><span class="sxs-lookup"><span data-stu-id="89e98-140">Parenthesized pattern</span></span>|<span data-ttu-id="89e98-141">( *deseni* )</span><span class="sxs-lookup"><span data-stu-id="89e98-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="89e98-142">Tanımlama grubu düzeni</span><span class="sxs-lookup"><span data-stu-id="89e98-142">Tuple pattern</span></span>|<span data-ttu-id="89e98-143">( *pattern_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="89e98-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="89e98-144">Kayıt düzeni</span><span class="sxs-lookup"><span data-stu-id="89e98-144">Record pattern</span></span>|<span data-ttu-id="89e98-145">{ *ıdentifier1* = *pattern_1*;...; *identifier_n* = *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="89e98-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="89e98-146">Joker karakter deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-146">Wildcard pattern</span></span>|<span data-ttu-id="89e98-147">\_</span><span class="sxs-lookup"><span data-stu-id="89e98-147">_</span></span>|`_`|
|<span data-ttu-id="89e98-148">Tür ek açıklaması ile birlikte desenleyin</span><span class="sxs-lookup"><span data-stu-id="89e98-148">Pattern together with type annotation</span></span>|<span data-ttu-id="89e98-149">*Desen* : *türü*</span><span class="sxs-lookup"><span data-stu-id="89e98-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="89e98-150">Test desenini yazın</span><span class="sxs-lookup"><span data-stu-id="89e98-150">Type test pattern</span></span>|<span data-ttu-id="89e98-151">:?</span><span class="sxs-lookup"><span data-stu-id="89e98-151">:?</span></span> <span data-ttu-id="89e98-152">*tür* [olarak *tanımlayıcı* ]</span><span class="sxs-lookup"><span data-stu-id="89e98-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="89e98-153">Null desen</span><span class="sxs-lookup"><span data-stu-id="89e98-153">Null pattern</span></span>|<span data-ttu-id="89e98-154">null</span><span class="sxs-lookup"><span data-stu-id="89e98-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="89e98-155">Sabit desenler</span><span class="sxs-lookup"><span data-stu-id="89e98-155">Constant Patterns</span></span>

<span data-ttu-id="89e98-156">Sabit desenler sayısal, karakter ve dize değişmez değerleri, numaralandırma sabitidir (numaralandırma türü adı dahil) var.</span><span class="sxs-lookup"><span data-stu-id="89e98-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="89e98-157">A `match` yalnızca sabit desenlere sahip ifadesi, başka dillerdeki case ifadesinden karşılaştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="89e98-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="89e98-158">Girdi değişmez değerle karşılaştırılır ve değerleri aynıysa desen eşleşir.</span><span class="sxs-lookup"><span data-stu-id="89e98-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="89e98-159">Değişmez değerin türü giriş türü ile uyumlu olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="89e98-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="89e98-160">Aşağıdaki örnek, değişmez değer desenlerinin kullanımını gösterir ve ayrıca bir değişken desen ve bir veya deseni kullanır.</span><span class="sxs-lookup"><span data-stu-id="89e98-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="89e98-161">Değişmez değer deseninin başka bir örneği, numaralandırma sabitlerini temel alan bir desendir.</span><span class="sxs-lookup"><span data-stu-id="89e98-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="89e98-162">Numaralandırma sabitlerini kullandığınızda, numaralandırma türü adı belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="89e98-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="89e98-163">Tanımlayıcı desenler</span><span class="sxs-lookup"><span data-stu-id="89e98-163">Identifier Patterns</span></span>

<span data-ttu-id="89e98-164">Desen, geçerli bir tanımlayıcı oluşturan karakter dizesi ise tanımlayıcının biçimi desen eşleştirilmesini belirler.</span><span class="sxs-lookup"><span data-stu-id="89e98-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="89e98-165">Tanımlayıcı tek bir karakterden daha uzunsa ve büyük harfli bir karakterle başlayan, derleyici tanımlayıcı desen bir eşleştirme yapmaya çalışır.</span><span class="sxs-lookup"><span data-stu-id="89e98-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="89e98-166">Bu düzen tanımlayıcısı değişmez değer özniteliği, ayrılmış bir birleşim durumu, bir özel durum tanımlayıcısı veya etkin desen çalışması ile işaretlenmiş bir değer olabilir.</span><span class="sxs-lookup"><span data-stu-id="89e98-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="89e98-167">Eşleşen hiçbir tanımlayıcı bulunmazsa, eşleştirme başarısız olur ve sonraki desen kuralı, değişken desen girdiyle karşılaştırılır.</span><span class="sxs-lookup"><span data-stu-id="89e98-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="89e98-168">Adlandırılmış çalışmalar ayrılmış birleşim desenleri basit olabilir veya bir değer ya da birden çok değer içeren bir tanımlama grubu olabilir.</span><span class="sxs-lookup"><span data-stu-id="89e98-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="89e98-169">Bir değer varsa değer için bir tanımlayıcı belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="89e98-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="89e98-170">Bir demet söz konusu olduğunda bir kayıt düzeni deseni kayıt düzeninin her öğe için bir tanımlayıcı veya bir alan adı olan bir tanımlayıcı sağlamanız gerekir veya birkaç adlandırılmış birlik alanı.</span><span class="sxs-lookup"><span data-stu-id="89e98-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="89e98-171">Kod örnekleri için bu bölümdeki örneklere bakın.</span><span class="sxs-lookup"><span data-stu-id="89e98-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="89e98-172">`option` Türüdür iki duruma sahip ayrılmış bir birleşim `Some` ve `None`.</span><span class="sxs-lookup"><span data-stu-id="89e98-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="89e98-173">Bir harf (`Some`) bir değer, ancak diğer sahiptir (`None`) sadece adlı bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="89e98-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="89e98-174">Bu nedenle, `Some` ilişkili değer için bir değişken olmalıdır `Some` büyük/küçük harf, ancak `None` tek başına görünmelidir.</span><span class="sxs-lookup"><span data-stu-id="89e98-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="89e98-175">Aşağıdaki kodda, değişken `var1` için elde edilen değeri verilir `Some` çalışması.</span><span class="sxs-lookup"><span data-stu-id="89e98-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="89e98-176">Aşağıdaki örnekte, `PersonName` birleşimdir dizeleri ve olası ad formlarını temsil eden karakterler bir karışımını içerir.</span><span class="sxs-lookup"><span data-stu-id="89e98-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="89e98-177">Ayrılmış birleşimin durumları olan `FirstOnly`, `LastOnly`, ve `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="89e98-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="89e98-178">Alanları adlı ayrılmış birleşimler, eşittir işareti (=) adlı bir alanın değerini ayıklamak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="89e98-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="89e98-179">Örneğin, aşağıdaki gibi bir bildirim ile ayrılmış bir birleşim göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="89e98-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="89e98-180">İfadeyle eşleşen desendeki adlandırılmış alanları aşağıdaki gibi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89e98-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="89e98-181">Adlandırılmış alan kullanımı isteğe bağlıdır, dolayısıyla önceki örnekte, her ikisi de `Circle(r)` ve `Circle(radius = r)` aynı etkiye sahiptir.</span><span class="sxs-lookup"><span data-stu-id="89e98-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="89e98-182">Noktalı virgül (;) kullanın, birden çok alan belirtirken, ayırıcı olarak.</span><span class="sxs-lookup"><span data-stu-id="89e98-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="89e98-183">Etkin desenler daha karmaşık özel desen eşleştirmeleri tanımlamanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="89e98-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="89e98-184">Etkin desenler hakkında daha fazla bilgi için bkz: [Etkin desenler](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="89e98-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="89e98-185">Tanımlayıcı bir özel durum olduğu durumda, özel durum işleyicilerinin bağlamında eşleşen desende kullanılır.</span><span class="sxs-lookup"><span data-stu-id="89e98-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="89e98-186">Özel Durum İşlemede desen hakkında daha fazla bilgi için bkz. [özel durumlar: `try...with` İfade](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="89e98-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="89e98-187">Değişken desenleri</span><span class="sxs-lookup"><span data-stu-id="89e98-187">Variable Patterns</span></span>

<span data-ttu-id="89e98-188">Değişken desen ardından sağındaki yürütme ifadesinde kullanılabilecek bir değişken adı, eşleştirilen değeri atar `->` simgesi.</span><span class="sxs-lookup"><span data-stu-id="89e98-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="89e98-189">Değişken desen tek başına herhangi bir girdiyle eşleşir ancak değişken desenler genellikle bu nedenle diziler ve değişkenlere ayrıştırılacak diziler gibi daha karmaşık yapıları etkinleştirme, diğer desenlerle görünür.</span><span class="sxs-lookup"><span data-stu-id="89e98-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="89e98-190">Aşağıdaki örnek, bir kayıt düzeni desen içinde değişken bir desen gösterir.</span><span class="sxs-lookup"><span data-stu-id="89e98-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="89e98-191">Deseni olarak</span><span class="sxs-lookup"><span data-stu-id="89e98-191">as Pattern</span></span>

<span data-ttu-id="89e98-192">`as` Desendir sahip bir deseni bir `as` eklenmiş yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="89e98-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="89e98-193">`as` Yan tümcesi eşleşen değeri yürütme ifadesinde kullanılabilecek bir ada bağlar bir `match` ifade veya durumda, bu düzen kullanıldığı bir `let` bağlama, ad yerel kapsama bir bağlama olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="89e98-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="89e98-194">Aşağıdaki örnekte bir `as` deseni.</span><span class="sxs-lookup"><span data-stu-id="89e98-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="89e98-195">OR deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-195">OR Pattern</span></span>

<span data-ttu-id="89e98-196">OR deseni, giriş verilerinin birden çok desen eşleştiğinde ve sonuç olarak aynı kodu yürütmek istediğiniz kullanılır.</span><span class="sxs-lookup"><span data-stu-id="89e98-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="89e98-197">VEYA deseninin her iki tarafının türleri uyumlu olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="89e98-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="89e98-198">Aşağıdaki örnek OR desenini gösterir.</span><span class="sxs-lookup"><span data-stu-id="89e98-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="89e98-199">VE deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-199">AND Pattern</span></span>

<span data-ttu-id="89e98-200">VE deseni girişin iki deseni eşleştirmesini gerektirir.</span><span class="sxs-lookup"><span data-stu-id="89e98-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="89e98-201">VE deseninin her iki tarafının türleri uyumlu olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="89e98-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="89e98-202">Aşağıdaki örnek gibi `detectZeroTuple` gösterilen [kayıt düzeni deseni](https://msdn.microsoft.com/library/#tuple) bölümde daha sonra bu konuda, ancak burada her iki `var1` ve `var2` değerler ve deseni kullanılarak elde edilir.</span><span class="sxs-lookup"><span data-stu-id="89e98-202">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="89e98-203">Olumsuz desen</span><span class="sxs-lookup"><span data-stu-id="89e98-203">Cons Pattern</span></span>

<span data-ttu-id="89e98-204">Olumsuz desen, bir listeyi ilk öğeye ayırmak için kullanılan *baş*ve kalan öğeleri içeren bir liste *tail*.</span><span class="sxs-lookup"><span data-stu-id="89e98-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="89e98-205">Liste deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-205">List Pattern</span></span>

<span data-ttu-id="89e98-206">Liste deseni listelerin çeşitli öğelere ayrıştırılmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="89e98-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="89e98-207">Liste deseninin kendisi yalnızca belirli sayıda öğelerin listesini eşleşebilir.</span><span class="sxs-lookup"><span data-stu-id="89e98-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="89e98-208">Dizi deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-208">Array Pattern</span></span>

<span data-ttu-id="89e98-209">Dizi deseni liste desenine benzer ve belirli uzunlukta diziler ayırmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="89e98-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="89e98-210">Parantezlenmiş desen</span><span class="sxs-lookup"><span data-stu-id="89e98-210">Parenthesized Pattern</span></span>

<span data-ttu-id="89e98-211">Parantez, istenen birleşimi elde etmek için desenler etrafında gruplandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="89e98-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="89e98-212">Aşağıdaki örnekte, parantezler bir AND deseni ve bir olumsuz desen arasındaki ilişkiyi denetlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="89e98-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="89e98-213">Tanımlama grubu düzeni</span><span class="sxs-lookup"><span data-stu-id="89e98-213">Tuple Pattern</span></span>

<span data-ttu-id="89e98-214">Kayıt düzeni deseni kayıt düzeni formunda bir girdiyle eşleşir ve kayıt düzenindeki her konum için değişken desen kullanarak bileşen öğelerine ayrılmasına olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="89e98-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="89e98-215">Aşağıdaki örnek, kayıt düzeni desenini gösterir ve ayrıca değişmez değer desenleri, değişken desenler ve joker karakter deseni kullanır.</span><span class="sxs-lookup"><span data-stu-id="89e98-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="89e98-216">Kayıt düzeni</span><span class="sxs-lookup"><span data-stu-id="89e98-216">Record Pattern</span></span>

<span data-ttu-id="89e98-217">Kayıt düzeni, alanların değerlerini ayıklamak üzere kayıtları ayırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="89e98-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="89e98-218">Desen, kaydın tüm alanlarını başvurmak yok; Atlanan tüm alanlar yalnızca eşleşen katılmaz ve ayıklanmaz.</span><span class="sxs-lookup"><span data-stu-id="89e98-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="89e98-219">Joker karakter deseni</span><span class="sxs-lookup"><span data-stu-id="89e98-219">Wildcard Pattern</span></span>

<span data-ttu-id="89e98-220">Joker karakter deseni alt çizgi ile temsil edilir (`_`) karakteri ve giriş yerine bir değişkene atandığında atılır dışında tıpkı değişken desen gibi herhangi bir girişle eşleşir.</span><span class="sxs-lookup"><span data-stu-id="89e98-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="89e98-221">Joker karakter deseni genellikle diğer desenler içinde yer tutucu olarak sağındaki ifadede gerekmeyen değerler için kullanılan `->` simgesi.</span><span class="sxs-lookup"><span data-stu-id="89e98-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="89e98-222">Joker karakter deseni, eşleşmeyen herhangi bir girişi eşleştirmek için Desen listesinin sonunda da sık sık kullanılır.</span><span class="sxs-lookup"><span data-stu-id="89e98-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="89e98-223">Joker karakter deseni, bu konudaki pek çok kod örneğinde gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="89e98-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="89e98-224">Bir örnek için önceki koda bakın.</span><span class="sxs-lookup"><span data-stu-id="89e98-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="89e98-225">Tür ek açıklamaları olan desenler</span><span class="sxs-lookup"><span data-stu-id="89e98-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="89e98-226">Desenler, tür ek açıklamaları olabilir.</span><span class="sxs-lookup"><span data-stu-id="89e98-226">Patterns can have type annotations.</span></span> <span data-ttu-id="89e98-227">Bunlar diğer türden ek açıklamalar gibi davranır ve diğer türden ek açıklamalar gibi çıkarım Kılavuzu.</span><span class="sxs-lookup"><span data-stu-id="89e98-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="89e98-228">Bulunan tür ek açıklamaları etrafına parantez gereklidir.</span><span class="sxs-lookup"><span data-stu-id="89e98-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="89e98-229">Aşağıdaki kod, bir tür ek açıklamasına sahip bir deseni gösterir.</span><span class="sxs-lookup"><span data-stu-id="89e98-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="89e98-230">Test desenini yazın</span><span class="sxs-lookup"><span data-stu-id="89e98-230">Type Test Pattern</span></span>

<span data-ttu-id="89e98-231">Tür sınama deseni, girişi bir türle eşleştirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="89e98-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="89e98-232">Giriş türü için bir eşleşme (veya türetilmiş bir tür) ise belirtilen desen, eşleşme başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="89e98-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="89e98-233">Aşağıdaki örnek tür testi desenini gösterir.</span><span class="sxs-lookup"><span data-stu-id="89e98-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="89e98-234">Null desen</span><span class="sxs-lookup"><span data-stu-id="89e98-234">Null Pattern</span></span>

<span data-ttu-id="89e98-235">Null desen, null değere izin türleriyle çalışırken görünebilen null değer eşleşir.</span><span class="sxs-lookup"><span data-stu-id="89e98-235">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="89e98-236">Null desenler, .NET Framework kodu ile birlikte çalışırken sıkça kullanılır.</span><span class="sxs-lookup"><span data-stu-id="89e98-236">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="89e98-237">Örneğin, bir .NET API dönüş değerini giriş olabilir bir `match` ifade.</span><span class="sxs-lookup"><span data-stu-id="89e98-237">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="89e98-238">Dönüş değerinin null olup olmadığını ve aynı zamanda döndürülen değerin diğer özelliklerini temel alan program akışını denetleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89e98-238">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="89e98-239">Null değerler, programınızın kalanına yayılmasını önlemek için null desenini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="89e98-239">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="89e98-240">Aşağıdaki örnek boş desen ve değişken deseni kullanır.</span><span class="sxs-lookup"><span data-stu-id="89e98-240">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="89e98-241">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="89e98-241">See also</span></span>

- [<span data-ttu-id="89e98-242">Eşleşme İfadeleri</span><span class="sxs-lookup"><span data-stu-id="89e98-242">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="89e98-243">Etkin Desenler</span><span class="sxs-lookup"><span data-stu-id="89e98-243">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="89e98-244">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="89e98-244">F# Language Reference</span></span>](index.md)