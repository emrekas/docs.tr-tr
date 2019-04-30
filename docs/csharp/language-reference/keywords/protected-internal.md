---
title: İç - korumalı C# başvurusu
ms.custom: seodec18
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 090baae7fe0e49289059e060d5dcba7b037ae47a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61660924"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="b54a5-102">korumalı iç (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="b54a5-102">protected internal (C# Reference)</span></span>

<span data-ttu-id="b54a5-103">`protected internal` Anahtar sözcüğü bir üye erişim değiştiricisi oluşur.</span><span class="sxs-lookup"><span data-stu-id="b54a5-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="b54a5-104">Korumalı bir iç üye geçerli derleme veya içeren sınıfından türetilen türler erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="b54a5-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="b54a5-105">Bir karşılaştırması `protected internal` diğer erişim değiştiricileri ile bkz [erişilebilirlik düzeyleri](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b54a5-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="b54a5-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="b54a5-106">Example</span></span>

<span data-ttu-id="b54a5-107">Bir taban sınıfın korumalı bir iç üye içeren kendi derlemesi içindeki herhangi bir türü erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="b54a5-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="b54a5-108">Yalnızca türetilmiş sınıf türünde bir değişken erişim oluşması durumunda başka bir derlemede bulunan türetilen bir sınıfta da erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="b54a5-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="b54a5-109">Örneğin, aşağıdaki kod kesimi göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="b54a5-109">For example, consider the following code segment:</span></span>

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
        BaseClass baseObject = new BaseClass();
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
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

<span data-ttu-id="b54a5-110">Bu örnek iki dosyayı içeren `Assembly1.cs` ve `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="b54a5-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="b54a5-111">İlk dosyayı içeren genel bir temel sınıf `BaseClass`ve başka bir sınıf `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="b54a5-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="b54a5-112">`BaseClass` korumalı bir iç üye sahibi `myValue`, tarafından erişilen `TestAccess` türü.</span><span class="sxs-lookup"><span data-stu-id="b54a5-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="b54a5-113">İkinci dosyasında, erişme denemesi `myValue` örneği üzerinden `BaseClass` bu üyeye türetilmiş bir sınıfın bir örnek üzerinden erişim sırasında bir hata üretecektir `DerivedClass` başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="b54a5-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="b54a5-114">Yapı üyeleri olamaz `protected internal` struct devraldığından.</span><span class="sxs-lookup"><span data-stu-id="b54a5-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b54a5-115">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="b54a5-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b54a5-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b54a5-116">See also</span></span>

- [<span data-ttu-id="b54a5-117">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="b54a5-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b54a5-118">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="b54a5-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b54a5-119">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="b54a5-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b54a5-120">Erişim Değiştiricileri</span><span class="sxs-lookup"><span data-stu-id="b54a5-120">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="b54a5-121">Erişilebilirlik Düzeyleri</span><span class="sxs-lookup"><span data-stu-id="b54a5-121">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="b54a5-122">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="b54a5-122">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="b54a5-123">public</span><span class="sxs-lookup"><span data-stu-id="b54a5-123">public</span></span>](public.md)
- [<span data-ttu-id="b54a5-124">private</span><span class="sxs-lookup"><span data-stu-id="b54a5-124">private</span></span>](private.md)
- [<span data-ttu-id="b54a5-125">internal</span><span class="sxs-lookup"><span data-stu-id="b54a5-125">internal</span></span>](internal.md)
- <span data-ttu-id="b54a5-126">[İç sanal anahtar sözcükleri ile ilgili güvenlik konuları](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b54a5-126">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>