---
title: Öznitelikler
description: Bilgi nasıl F# bir programlama yapısı için uygulanacak meta veri öznitelikleri etkinleştirin.
ms.date: 05/16/2016
ms.openlocfilehash: fed4c549b95d6d3701ab81cf5d62add411c16038
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642023"
---
# <a name="attributes"></a><span data-ttu-id="3263e-103">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="3263e-103">Attributes</span></span>

<span data-ttu-id="3263e-104">Bir programlama yapısı için uygulanacak meta veri öznitelikleri etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="3263e-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="3263e-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3263e-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="3263e-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3263e-106">Remarks</span></span>

<span data-ttu-id="3263e-107">Önceki sözdiziminde, *hedef* isteğe bağlıdır ve varsa, öznitelik program varlık türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="3263e-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="3263e-108">İçin geçerli değerler *hedef* bu belgenin sonraki bölümlerinde görüntülenen tabloda gösterilir.</span><span class="sxs-lookup"><span data-stu-id="3263e-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="3263e-109">*Öznitelik adı* geçerli öznitelik türü ile ya da soneki olmadan (büyük olasılıkla ad alanları ile tam) adını başvurduğu `Attribute` öznitelik türü adları genellikle kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3263e-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="3263e-110">Örneğin, türü `ObsoleteAttribute` yalnızca kısalttık `Obsolete` bu bağlamda.</span><span class="sxs-lookup"><span data-stu-id="3263e-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="3263e-111">*Bağımsız değişkenleri* oluşturucusu için bağımsız değişkenler için öznitelik türü.</span><span class="sxs-lookup"><span data-stu-id="3263e-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="3263e-112">Öznitelik bir varsayılan oluşturucusu yoksa, bağımsız değişken listesi ve parantezler atlanmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="3263e-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="3263e-113">Konumsal bağımsız değişkenlere hem adlandırılmış bağımsız değişkenler öznitelikler destekler.</span><span class="sxs-lookup"><span data-stu-id="3263e-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="3263e-114">*Konumsal bağımsız değişkenlere* göründükleri sırayla kullanılan bağımsız değişkenler.</span><span class="sxs-lookup"><span data-stu-id="3263e-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="3263e-115">Genel Özellikler özniteliğine sahipse, adlandırılmış bağımsız değişkenler kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3263e-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="3263e-116">Bu bağımsız değişken listesinde aşağıdaki söz dizimini kullanarak ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3263e-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="3263e-117">Bu özellik başlatmalarının herhangi bir sırada olabilir, ancak herhangi bir konumsal bağımsız değişken izlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="3263e-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="3263e-118">Konumsal bağımsız değişkenler ve özellik başlatmalarının kullanan bir öznitelik örneği aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="3263e-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="3263e-119">Bu örnekte, bir özniteliktir `DllImportAttribute`, burada kısaltılmış içinde kullanılan.</span><span class="sxs-lookup"><span data-stu-id="3263e-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="3263e-120">İlk bağımsız değişken konumsal bir parametredir ve ikinci bir özelliktir.</span><span class="sxs-lookup"><span data-stu-id="3263e-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="3263e-121">Öznitelikleri karşılıklı olarak bilinen bir nesne sağlayan bir .NET programlama yapısı bir *özniteliği* bir türü veya başka bir program öğesi ile ilişkilendirilmiş.</span><span class="sxs-lookup"><span data-stu-id="3263e-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="3263e-122">Özniteliğin uygulandığı bir program öğesi olarak bilinen *öznitelik hedefi*.</span><span class="sxs-lookup"><span data-stu-id="3263e-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="3263e-123">Öznitelik, genellikle hedefine hakkındaki meta veriler içeriyor.</span><span class="sxs-lookup"><span data-stu-id="3263e-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="3263e-124">Bu bağlamda herhangi bir veri üyeleri ve alanları dışındaki türü hakkında meta veriler olabilir.</span><span class="sxs-lookup"><span data-stu-id="3263e-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="3263e-125">Öznitelikleri F# aşağıdaki programlama yapıları için uygulanabilir: işlevleri, yöntemleri, derlemeler, modüller, türler (sınıflar, kayıtları, yapılar, arabirimler, temsilciler, numaralandırmalar, birleşimler ve benzeri), Oluşturucular, özellikleri, alanları, Parametreler, tür parametreleri ve dönüş değerleri.</span><span class="sxs-lookup"><span data-stu-id="3263e-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="3263e-126">Öznitelikler üzerinde izin verilmez `let` sınıfları, ifadeler veya iş akışı ifadeler içinde bağlar.</span><span class="sxs-lookup"><span data-stu-id="3263e-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="3263e-127">Genellikle, öznitelik bildiriminin doğrudan özniteliği hedef bildiriminden önce görünür.</span><span class="sxs-lookup"><span data-stu-id="3263e-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="3263e-128">Birden çok öznitelik bildirimleri kullanılabilir birlikte, aşağıdaki gibi.</span><span class="sxs-lookup"><span data-stu-id="3263e-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="3263e-129">Öznitelikler, çalışma zamanında .NET yansıma kullanarak sorgulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3263e-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="3263e-130">Önceki kod örneğinde olduğu gibi tek tek birden çok öznitelik bildirebilirsiniz veya burada gösterildiği gibi noktalı tek tek öznitelikler ve Oluşturucular, ayırmak için kullanıyorsanız bunları parantez kümesi içinde bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3263e-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="3263e-131">Sık rastlanan öznitelikleri yer `Obsolete` öznitelik, öznitelikler için güvenlik konuları öznitelikleri COM desteği, kod sahipliği ilişkili öznitelikleri ve bir türü seri hale belirten öznitelikleri.</span><span class="sxs-lookup"><span data-stu-id="3263e-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="3263e-132">Aşağıdaki örnek, kullanımını gösterir `Obsolete` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="3263e-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="3263e-133">Öznitelik hedefleri için `assembly` ve `module`, öznitelik için bir en üst düzey uygulama `do` , derlemede bağlama.</span><span class="sxs-lookup"><span data-stu-id="3263e-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="3263e-134">Word içerebilir `assembly` veya `module` gösterildiği gibi öznitelik bildirimi.</span><span class="sxs-lookup"><span data-stu-id="3263e-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="3263e-135">İçin uygulanan bir öznitelik için öznitelik hedefi atlarsanız, bir `do` bağlamayı F# derleyici bu özniteliği için anlamlı öznitelik hedefi belirlemek dener.</span><span class="sxs-lookup"><span data-stu-id="3263e-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="3263e-136">Çok sayıda öznitelik sınıfları bir öznitelik türü sahip `System.AttributeUsageAttribute` bu öznitelik için desteklenen olası hedefleri hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="3263e-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="3263e-137">Varsa `System.AttributeUsageAttribute` gösterir öznitelik hedefleri olarak işlevleri destekler, öznitelik programının ana giriş noktasına uygulanacak alınır.</span><span class="sxs-lookup"><span data-stu-id="3263e-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="3263e-138">Varsa `System.AttributeUsageAttribute` gösterir öznitelik hedefleri olarak derlemelerini destekler, derleyici derlemeye uygulanacak özniteliği alır.</span><span class="sxs-lookup"><span data-stu-id="3263e-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="3263e-139">Çoğu öznitelikleri işlevleri ve derlemeler için geçerli değildir, ancak yaptıkları olduğu durumlarda, öznitelik için programın main işlevi uygulamak için alınır.</span><span class="sxs-lookup"><span data-stu-id="3263e-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="3263e-140">Öznitelik, öznitelik hedefi açıkça belirtilmediği takdirde, belirtilen hedef uygulanır.</span><span class="sxs-lookup"><span data-stu-id="3263e-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="3263e-141">Genellikle belirtmek gerekmez, ancak öznitelik hedef açıkça için geçerli değerler *hedef* öznitelik içinde kullanım örneklerinin yanı sıra aşağıdaki tabloda gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="3263e-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="3263e-142">Öznitelik hedefi</span><span class="sxs-lookup"><span data-stu-id="3263e-142">Attribute target</span></span></td>
    <th><span data-ttu-id="3263e-143">Örnek</span><span class="sxs-lookup"><span data-stu-id="3263e-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3263e-144">derleme</span><span class="sxs-lookup"><span data-stu-id="3263e-144">assembly</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3263e-145">return</span><span class="sxs-lookup"><span data-stu-id="3263e-145">return</span></span></td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3263e-146">alan</span><span class="sxs-lookup"><span data-stu-id="3263e-146">field</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3263e-147">özellik</span><span class="sxs-lookup"><span data-stu-id="3263e-147">property</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3263e-148">param</span><span class="sxs-lookup"><span data-stu-id="3263e-148">param</span></span></td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3263e-149">türü</span><span class="sxs-lookup"><span data-stu-id="3263e-149">type</span></span></td>
    <td>
        <pre lang="fsharp"><code>
        [&lt;type: StructLayout(Sequential)&gt;] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        <code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="3263e-150">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3263e-150">See also</span></span>

- [<span data-ttu-id="3263e-151">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="3263e-151">F# Language Reference</span></span>](index.md)
