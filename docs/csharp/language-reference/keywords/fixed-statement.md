---
title: fixed Statement - C# başvurusu
ms.custom: seodec18
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: 2c49c8517e15534121b0f8dbc04902b46a92ef20
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959368"
---
# <a name="fixed-statement-c-reference"></a>fixed Deyimi (C# Başvurusu)

`fixed` Deyimi, taşınabilir bir değişken yerini değiştirme alanından çöp toplayıcı engeller. `fixed` Deyimi izin yalnızca bir [güvenli](unsafe.md) bağlamı. Ayrıca `fixed` oluşturmak için anahtar sözcüğü [sabit boyutlu arabellekler](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).

`fixed` Deyimi ayarlar bir işaretçi yönetilen bir değişken ve "Sabitlemeleri" değişken deyimin yürütülmesi sırasında. Yalnızca taşınabilir yönetilen değişkenleri işaretçileri kullanışlıdır bir `fixed` bağlamı. Olmadan bir `fixed` bağlamı, çöp toplama dışında yeniden konumlandırmakta değişkenleri ilgilenmeye. C# derleyicisi yalnızca, bir işaretçi yönetilen bir değişkene atamanıza olanak tanır bir `fixed` deyimi.

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

Bir işaretçi, bir dizi, bir dize, bir sabit boyutlu arabellek veya değişkenin adresini kullanarak başlatabilirsiniz. Aşağıdaki örnekte, değişken adresleri, diziler ve dizeleri kullanımını gösterir:

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

C# 7.3 ile başlangıç `fixed` deyimi yerler diziler, dizeler, sabit boyutlu arabellekler veya yönetilmeyen değişkenleri ötesinde ek türleri üzerinde çalışır. Adlı bir yöntem uygulayan herhangi bir tür `GetPinnableReference` sabitlenebilir. `GetPinnableReference` Döndürmelidir bir `ref` değişken için bir yönetilmeyen türe. Üzerinde konusuna [işaretçi türleri](../../programming-guide/unsafe-code-pointers/pointer-types.md) daha fazla bilgi için. .NET türleri <xref:System.Span%601?displayProperty=nameWithType> ve <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> sunulan .NET Core 2.0 olun bu düzeni kullanın ve sabitlenebilir. Bu, aşağıdaki örnekte gösterilmiştir:

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

Bu düzende alması gereken türleri oluşturuyorsanız, bkz. <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> desenini uygulama örneği.

Aynı türde ise tek bir deyimde birden çok işaretçi başlatılabilir:

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

Farklı türlerde işaretçileri başlatmak için yalnızca içe `fixed` ifadeleri, aşağıdaki örnekte gösterildiği gibi.

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

Deyim kodda yürütüldükten sonra sabitlenmiş olan tüm değişkenler sabitlenmemiş ve çöp toplama var. Bu nedenle, bu değişkenlere dışında işaret etmeyen `fixed` deyimi. İçinde bildirilmiş değişkenlerin `fixed` deyimi bu kolaylaştıracak ifade, kapsamı:

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

İşaretçileri başlatılamadı `fixed` deyimleri olan salt okunur değişkenler. İşaretçi değeri değiştirmek istiyorsanız, ikinci işaretçi değişkeninin bildirimini ve değiştiren gerekir. İçinde bildirilen değişken `fixed` deyimi değiştirilemez:

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```

Burada tabi atık koleksiyonu olması gerekmez ve bu nedenle sabitlenmiş gerekmez yığında bellek ayırabilirsiniz. Kullanan yapmak için [ `stackalloc` işleci](stackalloc.md).

## <a name="c-language-specification"></a>C# dili belirtimi

Daha fazla bilgi için [fixed deyimi](~/_csharplang/spec/unsafe-code.md#the-fixed-statement) bölümünü [ C# dil belirtimi](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C# Anahtar Sözcükleri](index.md)
- [unsafe](unsafe.md)
- [Sabit Boyutlu Arabellekler](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
