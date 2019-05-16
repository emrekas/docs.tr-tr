---
title: Kısıtlamalar
description: Hakkında bilgi edinin F# bir genel tür veya işlev içinde bir tür bağımsız değişkeni için gereksinimleri belirtmek için genel tür parametreleri uygulanan kısıtlamaları.
ms.date: 05/16/2016
ms.openlocfilehash: 1bf5c6fc4df6c8f2f7f969bd13030172c6b8aab9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645278"
---
# <a name="constraints"></a>Kısıtlamalar

Bu konu başlığı altında genel için uygulayabileceğiniz kısıtlamasını açıklayan bir genel tür veya işlev içinde bir tür bağımsız değişkeni için gereksinimleri belirleme için parametre türü.

## <a name="syntax"></a>Sözdizimi

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>Açıklamalar

Genel tür içinde kullanılabilir türleri sınırlamak uygulayabileceğiniz çeşitli farklı kısıtlamaları vardır. Aşağıdaki tabloda, listeler ve bu kısıtlamaları açıklar.

|Kısıtlama|Sözdizimi|Açıklama|
|----------|------|-----------|
|Tür kısıtlaması|*tür-parametresi* :&gt; *türü*|Sağlanan türü belirtilen türünden eşit ya da bundan türetilmiş olmalıdır veya bir arabirim türü olduğundan, sağlanan türü arabirimini uygulaması gerekir.|
|Null kısıtlaması|*tür-parametresi* : null|Sağlanan türü null sabiti desteklemesi gerekir. Bu, tüm .NET nesne türlerini içerir ancak değil F# listesi, tanımlama grubu, işlevi, sınıf, kaydı veya birleşim türleri.|
|Açık bir üye kısıtlaması|[(]*tür-parametresi* [veya... veya *tür-parametresi*)]: (*üye imzası*)|Sağlanan tür bağımsız değişkenlerini en az biri belirtilen imzaya sahip bir üyesi olması gerekir; Genel kullanım için tasarlanmamıştır. Üyeleri ya da açıkça türü veya bir örtük tür uzantısı bir parçası için açık bir üye kısıtlaması geçerli hedefleri olarak tanımlanması gerekir.|
|Oluşturucu kısıtlaması|*tür-parametresi* : (yeni: birimi -&gt; ' bir)|Sağlanan türü bir varsayılan oluşturucuya sahip olmalıdır.|
|Değer türü kısıtlaması|: Yapı|Sağlanan türü, bir .NET değer türü olması gerekir.|
|Başvuru türü kısıtlaması|: Yapı değil|Sağlanan türü, bir .NET başvuru türü olması gerekir.|
|Sabit listesi türü kısıtlaması|: enum&lt;*underlying-type*&gt;|Sağlanan türü belirtilen temel türe sahip bir listeden seçimli türü olmalıdır; Genel kullanım için tasarlanmamıştır.|
|Temsilci kısıtlaması|: delegate&lt;*tuple-parameter-type*, *return-type*&gt;|Sağlanan türü belirtilen bağımsız değişkenler olan bir temsilci türü ve dönüş değeri; Genel kullanım için tasarlanmamıştır.|
|Karşılaştırma kısıtlaması|: karşılaştırma|Sağlanan türü karşılaştırma desteklemesi gerekir.|
|Eşitliği kısıtlaması|: Eşitlik|Sağlanan türü eşitlik desteklemesi gerekir.|
|Yönetilmeyen kısıtlaması|: Yönetilmeyen|Sağlanan türü, yönetilmeyen bir türü olmalıdır. Yönetilmeyen türler belirli temel türleri (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, veya `decimal`), numaralandırma türleri `nativeptr<_>`, veya alanları olmak üzere tüm yönetilmeyen tür genel olmayan yapısı.|

Genel kısıtlama türü ancak çalıştırılmadı türleri üzerinde kullanılabilir olan bir özelliği kullanmak kodunuzu sahip olduğunda bir kısıtlama eklemeniz gerekir. Örneğin, bir sınıf türünü belirtmek için tür kısıtlaması kullanırsanız, bu sınıfın genel işlev veya tür yöntemlerden birini kullanabilirsiniz.

Bir kısıtlama derleyici, kullandığınız özellikleri türü için çalışma zamanında sağlanan herhangi bir türü üzerinde kullanılabilir olacağını doğrulama yolu yoktur çünkü kısıtlamaları belirtme bazen açıkça tür parametreleri yazarken gereklidir parametre.

En yaygın kısıtlamaları, kullandığınız F# kod olan tür kısıtlamaları, temel sınıflar veya arabirimleri belirtin. Diğer kısıtlamalar da tarafından kullanılan F# İşleç aşırı yüklemesi aritmetik işleçler için uygulamak için kullanılan ya da devre dışı olduğundan, esas olarak sağlanan açık üye kısıtlaması gibi belirli işlevleri uygulamak için Kitaplık F# Ortak dil çalışma zamanı tarafından desteklenen tüm kısıtlamaları kümesini destekler.

Tür çıkarımı işlemi sırasında bazı kısıtlamalar, derleyici tarafından otomatik olarak algılanır. Örneğin, kullanırsanız `+` işleci bir işlevde, derleyici bir açık bir üye kısıtlama ifadesinde kullanılan değişken türleri algılar.

Aşağıdaki kod, bazı kısıtlaması bildirimlerini gösterir.

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a>Ayrıca bkz.

- [Genel Türler](index.md)
- [Kısıtlamalar](constraints.md)
