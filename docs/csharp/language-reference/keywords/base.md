---
title: Base anahtar sözcüğü - C# başvurusu
ms.custom: seodec18
description: C# türetilmiş bir sınıf içinden temel sınıfın üyelerine erişmek için kullanılan temel anahtar sözcüğü hakkında bilgi edinin.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: ef7995c9f7737d29d7e9479c3b84a25b13943be3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61662113"
---
# <a name="base-c-reference"></a>base (C# Başvurusu)

`base` Anahtar sözcüğü, türetilmiş bir sınıf içinden temel sınıfın üyelerine erişmek için kullanılır:

- Başka bir yöntem tarafından geçersiz kılınan taban sınıfta bir yöntem çağrısı.

- Hangi temel sınıf oluşturucusu, türetilmiş sınıf örnekleri oluşturulurken çağrılması gerektiğini belirtin.

Bir temel sınıf erişim, yalnızca bir oluşturucu, bir örnek yöntemi veya bir örnek özellik erişimcisi izin verilir.

Kullanılacak bir hata olduğunu `base` anahtar sözcüğü statik bir yöntem içinde.

Erişilen temel sınıf, sınıf bildiriminde belirtilenden temel sınıftır. Örneğin, belirttiğiniz `class ClassB : ClassA`, Türetilme üyelerinin Türetilme temel sınıfını ne olursa olsun, Sınıfb'den erişilir.

## <a name="example"></a>Örnek

Bu örnekte, iki temel sınıfı, `Person`hem de türetilmiş sınıf `Employee`, adında bir yöntemi olan `Getinfo`. Kullanarak `base` anahtar sözcüğü, mümkündür çağrılacak `Getinfo` içinden temel sınıf yöntemini türetilmiş sınıf.

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

Diğer örnekler için [yeni](../../../csharp/language-reference/keywords/new.md), [sanal](../../../csharp/language-reference/keywords/virtual.md), ve [geçersiz kılma](../../../csharp/language-reference/keywords/override.md).

## <a name="example"></a>Örnek

Bu örnek, türetilen bir sınıfın örneklerini oluştururken adlı temel sınıf oluşturucusu belirtmek gösterilmektedir.

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a>C# dili belirtimi

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [C# Anahtar Sözcükleri](../../../csharp/language-reference/keywords/index.md)
- [this](../../../csharp/language-reference/keywords/this.md)
