---
title: Byte Veri Türü (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: e1725b709c03b0d77cf7e28761396236b5ef1a00
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622437"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="a193b-102">Byte veri türü (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a193b-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="a193b-103">Değeri 0 ile 255 arasında imzalanmamış 8-bit (1-bayt) tamsayıları tutar.</span><span class="sxs-lookup"><span data-stu-id="a193b-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="a193b-104">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a193b-104">Remarks</span></span>

<span data-ttu-id="a193b-105">Kullanım `Byte` ikili veri içermesini veri türü.</span><span class="sxs-lookup"><span data-stu-id="a193b-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="a193b-106">Varsayılan değer olan `Byte` 0'dır.</span><span class="sxs-lookup"><span data-stu-id="a193b-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="a193b-107">Değişmez değer atamaları</span><span class="sxs-lookup"><span data-stu-id="a193b-107">Literal assignments</span></span>

<span data-ttu-id="a193b-108">Bildirmek ve başlatmak bir `Byte` değişkenini, bir ondalık sabit değeri, onaltılık bir sabit değer, sekizlik bir sabit değer atama ya da (ikili değişmez değer Visual Basic 2017'den itibaren).</span><span class="sxs-lookup"><span data-stu-id="a193b-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="a193b-109">Tamsayı sabit değeri aralığının dışında ise bir `Byte` (diğer bir deyişle, bu ise kısa <xref:System.Byte.MinValue?displayProperty=nameWithType> veya ondan <xref:System.Byte.MaxValue?displayProperty=nameWithType>), bir derleme hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="a193b-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="a193b-110">Aşağıdaki örnekte, tamsayılar ondalık, onaltılık, gösterilen 201 eşit ve ikili sabit dizeler öğesinden örtük olarak dönüştürülür [tamsayı](integer-data-type.md) için `byte` değerleri.</span><span class="sxs-lookup"><span data-stu-id="a193b-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="a193b-111">Önek kullanın `&h` veya `&H` önek onaltılık bir sabit belirtmek için `&b` veya `&B` ikili sabit ve öneki belirtmek için `&o` veya `&O` sekizlik bir sabit belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="a193b-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="a193b-112">Ondalık değişmez değerler, önek vardır.</span><span class="sxs-lookup"><span data-stu-id="a193b-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="a193b-113">Visual Basic 2017'den itibaren alt çizgi karakteri de kullanabilirsiniz `_`, okunabilirliği artırmak için bir basamak ayırıcı olarak, aşağıdaki örnekte görüldüğü gibi.</span><span class="sxs-lookup"><span data-stu-id="a193b-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="a193b-114">Visual Basic 15.5 ile başlayarak, alt çizgi karakteri de kullanabilirsiniz (`_`) öneki ve onaltılık, ikili veya sekizlik basamak arasında önde gelen bir ayırıcı olarak.</span><span class="sxs-lookup"><span data-stu-id="a193b-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="a193b-115">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="a193b-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="a193b-116">Programlama ipuçları</span><span class="sxs-lookup"><span data-stu-id="a193b-116">Programming tips</span></span>

- <span data-ttu-id="a193b-117">**Negatif sayılar.**</span><span class="sxs-lookup"><span data-stu-id="a193b-117">**Negative Numbers.**</span></span> <span data-ttu-id="a193b-118">Çünkü `Byte` işaretsiz bir türü, negatif bir sayıyı temsil edemez.</span><span class="sxs-lookup"><span data-stu-id="a193b-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="a193b-119">Tek işlenenli eksi işareti kullanırsanız (`-`) yazmak için değerlendirilen bir ifade işlecinin `Byte`, Visual Basic ifade dönüştürür `Short` ilk.</span><span class="sxs-lookup"><span data-stu-id="a193b-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="a193b-120">**Biçim dönüştürme.**</span><span class="sxs-lookup"><span data-stu-id="a193b-120">**Format Conversions.**</span></span> <span data-ttu-id="a193b-121">Visual Basic okur veya yazar dosyaları veya DLL'leri, yöntemleri ve özellikleri çağırdığında, otomatik olarak veri biçimleri arasında dönüştürme yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a193b-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="a193b-122">İkili verilerin depolanmasını `Byte` değişkenleri ve dizileri gibi bir biçim dönüştürmelerini sırasında korunur.</span><span class="sxs-lookup"><span data-stu-id="a193b-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="a193b-123">Kullanmamalısınız bir `String` ikili veriler için değişken içerikleri biçimlerini ANSI ve Unicode arasında dönüştürme sırasında bozuk olduğundan.</span><span class="sxs-lookup"><span data-stu-id="a193b-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="a193b-124">**Genişletme.**</span><span class="sxs-lookup"><span data-stu-id="a193b-124">**Widening.**</span></span> <span data-ttu-id="a193b-125">`Byte` Widens veri türü için `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, veya `Double`.</span><span class="sxs-lookup"><span data-stu-id="a193b-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="a193b-126">Yani dönüştürebilirsiniz `Byte` karşılaşmadan bu türlerden birine bir <xref:System.OverflowException?displayProperty=nameWithType> hata.</span><span class="sxs-lookup"><span data-stu-id="a193b-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="a193b-127">**Tür karakterleri.**</span><span class="sxs-lookup"><span data-stu-id="a193b-127">**Type Characters.**</span></span> <span data-ttu-id="a193b-128">`Byte` değişmez değer türü karakteri ya da tanımlayıcı türü karakteri var.</span><span class="sxs-lookup"><span data-stu-id="a193b-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="a193b-129">**Çerçeve türü.**</span><span class="sxs-lookup"><span data-stu-id="a193b-129">**Framework Type.**</span></span> <span data-ttu-id="a193b-130">.NET Framework içinde karşılık gelen türü <xref:System.Byte?displayProperty=nameWithType> yapısı.</span><span class="sxs-lookup"><span data-stu-id="a193b-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="a193b-131">Örnek</span><span class="sxs-lookup"><span data-stu-id="a193b-131">Example</span></span>

 <span data-ttu-id="a193b-132">Aşağıdaki örnekte, `b` olduğu bir `Byte` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="a193b-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="a193b-133">Deyimlerini değişkenin aralık ve bit düzeyinde kaydırma işleçleri, uygulamayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="a193b-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="a193b-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a193b-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="a193b-135">Veri Türleri</span><span class="sxs-lookup"><span data-stu-id="a193b-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="a193b-136">Tür Dönüştürme İşlevleri</span><span class="sxs-lookup"><span data-stu-id="a193b-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="a193b-137">Dönüştürme Özeti</span><span class="sxs-lookup"><span data-stu-id="a193b-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="a193b-138">Veri Türlerinin Etkili Kullanımı</span><span class="sxs-lookup"><span data-stu-id="a193b-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
