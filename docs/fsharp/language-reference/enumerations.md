---
title: Numaralandırmalar
description: Nasıl kullanacağınızı öğrenin F# kodunuzu daha okunabilir ve sürdürülebilir hale getirmek için değişmez değerler yerine numaralandırmalar.
ms.date: 05/16/2016
ms.openlocfilehash: a8839b73de074f62606b70ffe969a53b3db753bf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921582"
---
# <a name="enumerations"></a>Numaralandırmalar

*Numaralandırmalar*olarak da bilinen *numaralandırmalar*,, etiketleri değerlerin bir alt kümesine atanmış burada integral türleridir. Kod daha okunabilir ve sürdürülebilir hale getirmek için değişmez değerler yerine bunları kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>Açıklamalar

Değerleri belirtilen hariç, bir numaralandırma gibi basit değerler, ayrılmış bir birleşim arar. Genellikle 0 veya 1 başlayan tamsayılar ya da bit konumlarını temsil eden tamsayı değerler. Bit konumlarını temsil eden bir numaralandırma hedeflediyseniz de kullanmalısınız [bayrakları](xref:System.FlagsAttribute) özniteliği.

Örneğin, bir son eki ile sabit değerleri gibi kullanabilirsiniz, böylece sabit listesinin temel alınan türü kullanılan değişmez değer belirlenir `1u`, `2u`ve benzeri işaretsiz tamsayı (`uint32`) türü.

Adlandırılmış değerler için başvurduğunuzda, numaralandırma türü adı bir niteleyici diğer bir deyişle, kullanmalısınız `enum-name.value1`, yalnızca `value1`. Bu davranış, ayrılmış birleşimler farklıdır. Her zaman Numaralandırmaların olmasıdır [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) özniteliği.

Aşağıdaki kod, bildirim ve bir numaralandırma kullanımını gösterir.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

Kolayca numaralandırma için temeldeki tür uygun işleci kullanılarak aşağıdaki kodda gösterildiği gibi dönüştürebilirsiniz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

Numaralandırılmış türler aşağıdaki temel türlerden biri olabilir: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, ve `char`. Numaralandırma türleri öğesinden devralınan türler olarak .NET Framework'teki gösterilir `System.Enum`, sırayla devralınır `System.ValueType`. Bu nedenle, yığın veya satır içeren bir nesne içinde bulunan değer türleri olduklarını ve temel türün herhangi bir değer geçerli bir numaralandırma değeridir. Sabit desen değerleri değiştiğinde, isimsiz değerler yakalayan bir desen sağlamak sahip olduğunuz için bu önemlidir.

`enum` İşlevi F# kitaplığı bir sabit listesi değeri, hatta önceden tanımlanmış, biri dışında bir değer oluşturmak için kullanılabilir değerleri adlı. Kullandığınız `enum` gibi işlev.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

Varsayılan `enum` işlev türüyle çalışır `int32`. Bu nedenle, temel alınan diğer türleri Numaralandırma türleri ile kullanılamaz. Bunun yerine, aşağıdaki kullanın.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

Ayrıca, her zaman sabit listeleri olarak gönderilir için durumlarda `public`. Bu, böylelikle C# ve .NET platformu geri kalanı ile hizalanır.

## <a name="see-also"></a>Ayrıca bkz.

- [F# Dili Başvurusu](index.md)
- [Tür Değiştirme ve Dönüştürmeler](casting-and-conversions.md)