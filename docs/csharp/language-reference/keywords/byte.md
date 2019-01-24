---
title: byte - C# başvurusu
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
ms.openlocfilehash: fe2ef272c77b1af3a5b5a7f5bf3efb4836edcf23
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691534"
---
# <a name="byte-c-reference"></a><span data-ttu-id="aa172-102">byte (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="aa172-102">byte (C# Reference)</span></span>

<span data-ttu-id="aa172-103">`byte` Aşağıdaki tabloda gösterildiği gibi değerleri depolayan bir tamsayı türü gösterir.</span><span class="sxs-lookup"><span data-stu-id="aa172-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="aa172-104">Tür</span><span class="sxs-lookup"><span data-stu-id="aa172-104">Type</span></span>|<span data-ttu-id="aa172-105">Aralık</span><span class="sxs-lookup"><span data-stu-id="aa172-105">Range</span></span>|<span data-ttu-id="aa172-106">Boyut</span><span class="sxs-lookup"><span data-stu-id="aa172-106">Size</span></span>|<span data-ttu-id="aa172-107">.NET türü</span><span class="sxs-lookup"><span data-stu-id="aa172-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="aa172-108">0 ile 255 arasında</span><span class="sxs-lookup"><span data-stu-id="aa172-108">0 to 255</span></span>|<span data-ttu-id="aa172-109">İmzalanmamış 8 bit tam sayı</span><span class="sxs-lookup"><span data-stu-id="aa172-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="aa172-110">Sabit değerler</span><span class="sxs-lookup"><span data-stu-id="aa172-110">Literals</span></span>  

 <span data-ttu-id="aa172-111">Bildirmek ve başlatmak bir `byte` değişkenini değişmez değer ondalık, onaltılık bir sabit değer atama veya (C# 7.0 ile için sabit bir ikili başlayarak).</span><span class="sxs-lookup"><span data-stu-id="aa172-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="aa172-112">Tamsayı sabit değeri aralığının dışında ise `byte` (diğer bir deyişle, bu ise kısa <xref:System.Byte.MinValue?displayProperty=nameWithType> veya ondan <xref:System.Byte.MaxValue?displayProperty=nameWithType>), bir derleme hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="aa172-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="aa172-113">Aşağıdaki örnekte, tamsayılar ondalık, onaltılık, gösterilen 201 eşit ve ikili sabit dizeler öğesinden örtük olarak dönüştürülür [int](../../../csharp/language-reference/keywords/int.md) için `byte` değerleri.</span><span class="sxs-lookup"><span data-stu-id="aa172-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> <span data-ttu-id="aa172-114">Önek kullanın `0x` veya `0X` onaltılık bir sabit değer ve öneki belirtmek için `0b` veya `0B` ikili bir sabit belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="aa172-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="aa172-115">Ondalık değişmez değerler, önek vardır.</span><span class="sxs-lookup"><span data-stu-id="aa172-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="aa172-116">C# 7.0 ile okunabilirliği artırmak birkaç özellik eklenmiştir başlatılıyor.</span><span class="sxs-lookup"><span data-stu-id="aa172-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="aa172-117">C# 7.0, alt çizgi karakteri kullanımına izin verir `_`, basamak ayırıcı olarak.</span><span class="sxs-lookup"><span data-stu-id="aa172-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="aa172-118">C# 7.2 sağlayan `_` sonra öneki için bir ikili veya onaltılık sabit basamak ayırıcı olarak kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="aa172-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="aa172-119">Ondalık bir sabit değer, bir alt çizgi olan izin verilen değil.</span><span class="sxs-lookup"><span data-stu-id="aa172-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="aa172-120">Aşağıda bazı örnekler gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="aa172-120">Some examples are shown below.</span></span>

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a><span data-ttu-id="aa172-121">Dönüşümler</span><span class="sxs-lookup"><span data-stu-id="aa172-121">Conversions</span></span>  
 <span data-ttu-id="aa172-122">Önceden tanımlanmış bir örtük dönüştürme vardır `byte` için [kısa](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [uzun ](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [çift](../../../csharp/language-reference/keywords/double.md), veya [ondalık](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="aa172-122">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="aa172-123">Daha büyük depolama boyutu için sabit olmayan değer sayısal türleri örtülü olarak dönüştürülemiyor `byte`.</span><span class="sxs-lookup"><span data-stu-id="aa172-123">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="aa172-124">Tam sayı türleri depolama alanı boyutları hakkında daha fazla bilgi için bkz. [tam sayı türleri tablosu](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="aa172-124">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="aa172-125">Örneğin, aşağıdaki iki göz önünde bulundurun `byte` değişkenleri `x` ve `y`:</span><span class="sxs-lookup"><span data-stu-id="aa172-125">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```csharp  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="aa172-126">Atama işlecinin sağ tarafında aritmetik ifadenin değerlendirdiği çünkü aşağıdaki atama deyimi bir derleme hatası üretecektir `int` varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="aa172-126">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="aa172-127">Bu sorunu gidermek için bir tür dönüştürme kullanın:</span><span class="sxs-lookup"><span data-stu-id="aa172-127">To fix this problem, use a cast:</span></span>  
  
```csharp  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="aa172-128">Ancak, hedef değişkeni aynı depolama boyutuna veya daha büyük bir depolama boyutu sahip olduğu aşağıdaki deyimleri kullanmak mümkündür:</span><span class="sxs-lookup"><span data-stu-id="aa172-128">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="aa172-129">Ayrıca, kayan nokta türlerinden örtük dönüştürme vardır `byte`.</span><span class="sxs-lookup"><span data-stu-id="aa172-129">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="aa172-130">Örneğin, bir açık tür dönüştürme kullanılmadığı sürece aşağıdaki deyim, bir derleyici hatası oluşturur:</span><span class="sxs-lookup"><span data-stu-id="aa172-130">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="aa172-131">Aşırı yüklenmiş yöntemleri çağrılırken bir yayın kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="aa172-131">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="aa172-132">Örneğin, aşağıdaki aşırı yüklenmiş yöntem düşünün `byte` ve [int](../../../csharp/language-reference/keywords/int.md) parametreleri:</span><span class="sxs-lookup"><span data-stu-id="aa172-132">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="aa172-133">Kullanarak `byte` atama doğru tür, örneğin çağrıldığını güvence altına alır:</span><span class="sxs-lookup"><span data-stu-id="aa172-133">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="aa172-134">Karma kayan nokta türleri ve tamsayı türleri aritmetik ifadeler hakkında daha fazla bilgi için bkz: [float](../../../csharp/language-reference/keywords/float.md) ve [çift](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="aa172-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="aa172-135">Örtük sayısal dönüştürme kuralları hakkında daha fazla bilgi için bkz. [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="aa172-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="aa172-136">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="aa172-136">C# Language Specification</span></span>  

<span data-ttu-id="aa172-137">Daha fazla bilgi için [Integral türleri](~/_csharplang/spec/types.md#integral-types) içinde [ C# dil belirtimi](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="aa172-137">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="aa172-138">Dil belirtimi, C# sözdizimi ve kullanımı için kesin bir kaynaktır.</span><span class="sxs-lookup"><span data-stu-id="aa172-138">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aa172-139">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="aa172-139">See also</span></span>

- <xref:System.Byte>
- [<span data-ttu-id="aa172-140">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="aa172-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="aa172-141">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="aa172-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="aa172-142">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="aa172-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="aa172-143">Tam Sayı Türleri Tablosu</span><span class="sxs-lookup"><span data-stu-id="aa172-143">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="aa172-144">Yerleşik Türler Tablosu</span><span class="sxs-lookup"><span data-stu-id="aa172-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="aa172-145">Örtük Sayısal Dönüştürmeler Tablosu</span><span class="sxs-lookup"><span data-stu-id="aa172-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="aa172-146">Açık Sayısal Dönüştürmeler Tablosu</span><span class="sxs-lookup"><span data-stu-id="aa172-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
