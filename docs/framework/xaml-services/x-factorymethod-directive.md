---
title: x:FactoryMethod Yönergesi
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: cb78514540f5f44b07b1fdd16283d26c647a3ac4
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58034536"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="e9a74-102">x:FactoryMethod Yönergesi</span><span class="sxs-lookup"><span data-stu-id="e9a74-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="e9a74-103">XAML işlemci yedekleme türünü çözdükten sonra nesneyi başlatmak için kullanması gereken bir oluşturucu dışında bir yöntem belirtir.</span><span class="sxs-lookup"><span data-stu-id="e9a74-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="e9a74-104">XAML öznitelik kullanımı, x: Arguments</span><span class="sxs-lookup"><span data-stu-id="e9a74-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="e9a74-105">XAML öznitelik kullanımı, x: Arguments öğeyi/öğeleri olarak</span><span class="sxs-lookup"><span data-stu-id="e9a74-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="e9a74-106">XAML Değerleri</span><span class="sxs-lookup"><span data-stu-id="e9a74-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="e9a74-107">Dize olarak belirtilen örneği başlatmak için XAML işlemci çağıran bir yöntem yöntemi adını `object`.</span><span class="sxs-lookup"><span data-stu-id="e9a74-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="e9a74-108">Açıklamalara bakın.</span><span class="sxs-lookup"><span data-stu-id="e9a74-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="e9a74-109">Fabrika yöntem parametreleri belirtin nesneleri için bir veya daha fazla nesne öğeleri.</span><span class="sxs-lookup"><span data-stu-id="e9a74-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="e9a74-110">Sırası önemlidir; Bu bağımsız değişkenler için Üreteç yöntemi iletilmesi gereken sırayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="e9a74-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9a74-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e9a74-111">Remarks</span></span>  
 <span data-ttu-id="e9a74-112">Varsa `methodname` bir örnek yöntemi olduğundan koşullu olamaz.</span><span class="sxs-lookup"><span data-stu-id="e9a74-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="e9a74-113">Statik yöntemler olarak Fabrika yöntemleri desteklenir.</span><span class="sxs-lookup"><span data-stu-id="e9a74-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="e9a74-114">Varsa `methodname` statik bir yöntem `methodname` olarak sağlanan bir *typeName*. *methodName* birleşimi, burada *typeName* statik fabrika yöntemi tanımlayan sınıf adları.</span><span class="sxs-lookup"><span data-stu-id="e9a74-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="e9a74-115">*typeName* ön ek nitelikli eşlenen xmlns içerisindeki bir türe başvuran durumunda olabilir.</span><span class="sxs-lookup"><span data-stu-id="e9a74-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="e9a74-116">*typeName* farklı bir tür olabilir `typeof(object)`.</span><span class="sxs-lookup"><span data-stu-id="e9a74-116">*typeName* can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="e9a74-117">İlgili nesne öğesi yedekler türünde bildirilen genel bir yöntem Üreteç yöntemi olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e9a74-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="e9a74-118">Üreteç yöntemi ilgili nesneye atanamaz örneği döndürmelidir.</span><span class="sxs-lookup"><span data-stu-id="e9a74-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="e9a74-119">Fabrika yöntemleri hiçbir zaman null değeri döndürmelidir.</span><span class="sxs-lookup"><span data-stu-id="e9a74-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="e9a74-120">`x:Arguments` Fabrika yöntemleri imzalarını için en iyi eşleşme İlkesi çalışır.</span><span class="sxs-lookup"><span data-stu-id="e9a74-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="e9a74-121">Eşleşen ilk parametre sayısı değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="e9a74-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="e9a74-122">Parametre sayısı için birden çok olası eşleşme varsa, değerlendirilen ve en iyi eşleşme belirlenir sonra parametre türüdür.</span><span class="sxs-lookup"><span data-stu-id="e9a74-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="e9a74-123">Varsa hala belirsizlik değerlendirme sonra bu aşamayı, XAML işlemci davranış tanımsızdır.</span><span class="sxs-lookup"><span data-stu-id="e9a74-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="e9a74-124">`x:FactoryMethod` Öğesi kullanımı değil özellik öğesi kullanımı tipik anlamında yönerge biçimlendirme içeren nesne öğe türünün başvurmadığından.</span><span class="sxs-lookup"><span data-stu-id="e9a74-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="e9a74-125">Bu beklenen bu öğesi kullanımı öznitelik kullanımı daha az yaygındır.</span><span class="sxs-lookup"><span data-stu-id="e9a74-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="e9a74-126">`x:Arguments` (özniteliği veya öğenin kullanım) ile birlikte kullanılabilir `x:FactoryMethod` öğesi kullanımı, ancak bu özellikle gösterilmez kullanım bölümlerde.</span><span class="sxs-lookup"><span data-stu-id="e9a74-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="e9a74-127">`x:FactoryMethod` herhangi bir öğeyi diğer bir özelliği öğelerden önce gelmelidir gibi gelmelidir `x:Arguments` ayrıca öğeleri olarak sağlanan ve herhangi bir içeriği/iç metin/başlatma metin gelmelidir.</span><span class="sxs-lookup"><span data-stu-id="e9a74-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a74-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e9a74-128">See also</span></span>
- [<span data-ttu-id="e9a74-129">x:Arguments Yönergesi</span><span class="sxs-lookup"><span data-stu-id="e9a74-129">x:Arguments Directive</span></span>](x-arguments-directive.md)
