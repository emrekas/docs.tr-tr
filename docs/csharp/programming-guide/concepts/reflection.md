---
title: Yansıma (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: 4dfd9391407fec4bd20ac4ae05162763e909d665
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61711115"
---
# <a name="reflection-c"></a><span data-ttu-id="a225d-102">Yansıma (C#)</span><span class="sxs-lookup"><span data-stu-id="a225d-102">Reflection (C#)</span></span>
<span data-ttu-id="a225d-103">Yansıma nesneleri sağlar (tür <xref:System.Type>) derlemeler, modüller ve türler açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a225d-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="a225d-104">Yansıma, dinamik olarak bir türün bir örneğini oluşturmak, bağlama türü var olan bir nesneye veya türü mevcut bir nesneden elde ve kendi yöntemlerini çağırmak veya kendi alanlarına ve özelliklerine erişmek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a225d-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="a225d-105">Kodunuzda öznitelikler kullanıyorsanız, yansıma erişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="a225d-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="a225d-106">Daha fazla bilgi için [öznitelikleri](../../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="a225d-106">For more information, see [Attributes](../../../../docs/standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="a225d-107">Yansıma statik bir yöntemi kullanarak basit bir örnek `GetType` - tüm türleri tarafından devralınan `Object` temel sınıfı - bir değişken türü elde etmek için:</span><span class="sxs-lookup"><span data-stu-id="a225d-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 <span data-ttu-id="a225d-108">Çıktı.</span><span class="sxs-lookup"><span data-stu-id="a225d-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="a225d-109">Aşağıdaki örnek, yüklü bütünleştirilmiş kodun tam adı almak için yansıtma kullanır.</span><span class="sxs-lookup"><span data-stu-id="a225d-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```csharp  
// Using Reflection to get information of an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 <span data-ttu-id="a225d-110">Çıktı.</span><span class="sxs-lookup"><span data-stu-id="a225d-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  <span data-ttu-id="a225d-111">C# anahtar sözcükleri `protected` ve `internal` IL içinde herhangi bir anlamı yoktur ve yansıma API'leri kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="a225d-111">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="a225d-112">IL içinde karşılık gelen terimlerdir *ailesi* ve *derleme*.</span><span class="sxs-lookup"><span data-stu-id="a225d-112">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="a225d-113">Tanımlamak için bir `internal` yansıma, kullanım kullanarak yöntemi <xref:System.Reflection.MethodBase.IsAssembly%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="a225d-113">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="a225d-114">Tanımlamak için bir `protected internal` yöntemi, kullanım <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="a225d-114">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>  
  
## <a name="reflection-overview"></a><span data-ttu-id="a225d-115">Yansıma genel bakış</span><span class="sxs-lookup"><span data-stu-id="a225d-115">Reflection Overview</span></span>  
 <span data-ttu-id="a225d-116">Yansıma, aşağıdaki durumlarda kullanışlıdır:</span><span class="sxs-lookup"><span data-stu-id="a225d-116">Reflection is useful in the following situations:</span></span>  
  
- <span data-ttu-id="a225d-117">Programınızın meta veri öznitelikleri erişmeye olduğunda.</span><span class="sxs-lookup"><span data-stu-id="a225d-117">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="a225d-118">Daha fazla bilgi için [öznitelikleri depolanan alınırken bilgi](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="a225d-118">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
- <span data-ttu-id="a225d-119">İnceleme ve derlemedeki türleri örnekleme için.</span><span class="sxs-lookup"><span data-stu-id="a225d-119">For examining and instantiating types in an assembly.</span></span>  
  
- <span data-ttu-id="a225d-120">Çalışma zamanında yeni türler oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="a225d-120">For building new types at runtime.</span></span> <span data-ttu-id="a225d-121">Sınıfları kullanın <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="a225d-121">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
- <span data-ttu-id="a225d-122">Çalışma zamanında oluşturulan türlerde yöntemleri erişme geç bağlama gerçekleştirmek için.</span><span class="sxs-lookup"><span data-stu-id="a225d-122">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="a225d-123">Konusuna [dinamik olarak yükleme ve türleri kullanarak](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="a225d-123">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a225d-124">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="a225d-124">Related Sections</span></span>  
 <span data-ttu-id="a225d-125">Daha fazla bilgi için:</span><span class="sxs-lookup"><span data-stu-id="a225d-125">For more information:</span></span>  
  
- [<span data-ttu-id="a225d-126">Yansıma</span><span class="sxs-lookup"><span data-stu-id="a225d-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
- [<span data-ttu-id="a225d-127">Tür Bilgilerini Görüntüleme</span><span class="sxs-lookup"><span data-stu-id="a225d-127">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
- [<span data-ttu-id="a225d-128">Yansıma ve Genel Türler</span><span class="sxs-lookup"><span data-stu-id="a225d-128">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
- <xref:System.Reflection.Emit>  
  
- [<span data-ttu-id="a225d-129">Özniteliklerde Depolanan Bilgileri Alma</span><span class="sxs-lookup"><span data-stu-id="a225d-129">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="a225d-130">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a225d-130">See also</span></span>

- [<span data-ttu-id="a225d-131">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="a225d-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a225d-132">Ortak Dil Çalışma Zamanı Modülündeki Bütünleştirilmiş Kodlar</span><span class="sxs-lookup"><span data-stu-id="a225d-132">Assemblies in the Common Language Runtime</span></span>](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
