---
title: İç - korumalı C# başvurusu
ms.custom: seodec18
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: ddfefa2a0bb145aa49a60f06a40725d2706cecb5
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661650"
---
# <a name="protected-internal-c-reference"></a>korumalı iç (C# Başvurusu)

`protected internal` Anahtar sözcüğü bir üye erişim değiştiricisi oluşur. Korumalı bir iç üye geçerli derleme veya içeren sınıfından türetilen türler erişilebilir. Bir karşılaştırması `protected internal` diğer erişim değiştiricileri ile bkz [erişilebilirlik düzeyleri](accessibility-levels.md).

## <a name="example"></a>Örnek

Bir taban sınıfın korumalı bir iç üye içeren kendi derlemesi içindeki herhangi bir türü erişilebilir. Yalnızca türetilmiş sınıf türünde bir değişken erişim oluşması durumunda başka bir derlemede bulunan türetilen bir sınıfta da erişilebilir. Örneğin, aşağıdaki kod kesimi göz önünde bulundurun:

```csharp
// Assembly1.cs
// Compile with: /target:library
public class BaseClass
{
   protected internal int myValue = 0;
}

class TestAccess
{
    void Access()
    {
        var baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass : BaseClass
{
    static void Main()
    {
        var baseObject = new BaseClass();
        var derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

Bu örnek iki dosyayı içeren `Assembly1.cs` ve `Assembly2.cs`.
İlk dosyayı içeren genel bir temel sınıf `BaseClass`ve başka bir sınıf `TestAccess`. `BaseClass` korumalı bir iç üye sahibi `myValue`, tarafından erişilen `TestAccess` türü.
İkinci dosyasında, erişme denemesi `myValue` örneği üzerinden `BaseClass` bu üyeye türetilmiş bir sınıfın bir örnek üzerinden erişim sırasında bir hata üretecektir `DerivedClass` başarılı olur.

Yapı üyeleri olamaz `protected internal` struct devraldığından.

## <a name="c-language-specification"></a>C# dili belirtimi

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C# Anahtar Sözcükleri](index.md)
- [Erişim Değiştiricileri](access-modifiers.md)
- [Erişilebilirlik Düzeyleri](accessibility-levels.md)
- [Değiştiriciler](modifiers.md)
- [public](public.md)
- [private](private.md)
- [internal](internal.md)
- [İç sanal anahtar sözcükleri ile ilgili güvenlik konuları](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))
