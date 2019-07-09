---
title: Özel korumalı - C# başvurusu
ms.custom: seodec18
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: c739dd0b5a5457a66c11962ed86bcd2ffbf811ab
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661684"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="a0e07-102">private protected (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="a0e07-102">private protected (C# Reference)</span></span>

<span data-ttu-id="a0e07-103">`private protected` Anahtar sözcüğü bir üye erişim değiştiricisi oluşur.</span><span class="sxs-lookup"><span data-stu-id="a0e07-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="a0e07-104">Özel bir korumalı üye, kapsayan sınıfı ancak kendi içeren bütünleştirilmiş kod içinde yalnızca türetilen türler tarafından erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="a0e07-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="a0e07-105">Bir karşılaştırması `private protected` diğer erişim değiştiricileri ile bkz [erişilebilirlik düzeyleri](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a0e07-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a0e07-106">`private protected` Erişim değiştiricisi geçerli sürümde C# 7.2 ve üzeri.</span><span class="sxs-lookup"><span data-stu-id="a0e07-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="a0e07-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="a0e07-107">Example</span></span>

<span data-ttu-id="a0e07-108">Yalnızca statik değişken türü türetilmiş sınıf türü ise bir taban sınıfın özel ve korumalı bir üye türetilen türler, içeren derlemede erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="a0e07-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="a0e07-109">Örneğin, aşağıdaki kod kesimi göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="a0e07-109">For example, consider the following code segment:</span></span>  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        var baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;  

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

<span data-ttu-id="a0e07-110">Bu örnek iki dosyayı içeren `Assembly1.cs` ve `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="a0e07-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="a0e07-111">İlk dosyayı içeren genel bir temel sınıf `BaseClass`ve bu türden türetilmiş tür `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="a0e07-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="a0e07-112">`BaseClass` özel bir korumalı üye sahibi `myValue`, hangi `DerivedClass1` iki yolla erişmeyi dener.</span><span class="sxs-lookup"><span data-stu-id="a0e07-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="a0e07-113">Erişmek için yapılan ilk girişim `myValue` örneği üzerinden `BaseClass` hataya neden olur.</span><span class="sxs-lookup"><span data-stu-id="a0e07-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="a0e07-114">Ancak, devralınan bir üyesi olarak kullanma girişimi `DerivedClass1` başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="a0e07-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="a0e07-115">İkinci dosyasında, erişme denemesi `myValue` devralınan bir üyesi olarak `DerivedClass2` yalnızca Assembly1 türetilmiş türleri tarafından erişilebilir olduğundan bir hata üretecektir.</span><span class="sxs-lookup"><span data-stu-id="a0e07-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="a0e07-116">Yapı üyeleri olamaz `private protected` struct devraldığından.</span><span class="sxs-lookup"><span data-stu-id="a0e07-116">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="a0e07-117">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="a0e07-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="a0e07-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a0e07-118">See also</span></span>

- [<span data-ttu-id="a0e07-119">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="a0e07-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a0e07-120">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="a0e07-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a0e07-121">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="a0e07-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a0e07-122">Erişim Değiştiricileri</span><span class="sxs-lookup"><span data-stu-id="a0e07-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="a0e07-123">Erişilebilirlik Düzeyleri</span><span class="sxs-lookup"><span data-stu-id="a0e07-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="a0e07-124">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="a0e07-124">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="a0e07-125">public</span><span class="sxs-lookup"><span data-stu-id="a0e07-125">public</span></span>](public.md)
- [<span data-ttu-id="a0e07-126">private</span><span class="sxs-lookup"><span data-stu-id="a0e07-126">private</span></span>](private.md)
- [<span data-ttu-id="a0e07-127">internal</span><span class="sxs-lookup"><span data-stu-id="a0e07-127">internal</span></span>](internal.md)
- <span data-ttu-id="a0e07-128">[İç sanal anahtar sözcükleri ile ilgili güvenlik konuları](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a0e07-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
