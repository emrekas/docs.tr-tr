---
title: Arabirim Tasarımı
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: KrzysztofCwalina
ms.openlocfilehash: 1f982aa37f92b7270725574d949989ca120297d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026373"
---
# <a name="interface-design"></a><span data-ttu-id="b84e8-102">Arabirim Tasarımı</span><span class="sxs-lookup"><span data-stu-id="b84e8-102">Interface Design</span></span>
<span data-ttu-id="b84e8-103">Çoğu API'ler, en iyi sınıfları ve yapıları kullanarak modellenir olsa da, arabirimler daha uygun olan veya tek seçenektir durumlar vardır.</span><span class="sxs-lookup"><span data-stu-id="b84e8-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="b84e8-104">CLR'nin birden çok devralmayı desteklemez (yani, CLR sınıflarını birden fazla temel sınıfından devralamaz), ancak bir taban sınıftan devralmayı ek olarak, bir veya daha fazla arabirimi uygulayan türleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="b84e8-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="b84e8-105">Bu nedenle, arabirimler, genellikle birden çok devralma etkiyi elde etmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="b84e8-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="b84e8-106">Örneğin, <xref:System.IDisposable> disposability, istedikleri katılmak diğer tüm Devralma Hiyerarşisi bağımsız desteklemek için türleri izin veren bir arabirimdir.</span><span class="sxs-lookup"><span data-stu-id="b84e8-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="b84e8-107">Hangi tanımlama arabirimin uygun olan diğer bazı değer türleri dahil olmak üzere çeşitli türleri tarafından desteklenen ortak bir arabirim oluştururken bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="b84e8-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="b84e8-108">Değer türleri devralamaz türlerinden dışında <xref:System.ValueType>, ancak arabirimleri uygulayabilir, bunu bir arabirimi kullanarak ortak bir taban türü sağlamak için tek seçenek.</span><span class="sxs-lookup"><span data-stu-id="b84e8-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="b84e8-109">**✓ DO** değer türleri içeren bir dizi türleri tarafından desteklenen bazı ortak API gerekiyorsa bir arabirim tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="b84e8-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="b84e8-110">**✓ CONSIDER** önceden başka bazı türünden devralan türleri işlevselliği desteklemek gereksinim duyarsanız bir arabirim tanımlama.</span><span class="sxs-lookup"><span data-stu-id="b84e8-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="b84e8-111">**X AVOID** işaret arabirimleri (hiçbir üye arabirimleriyle) kullanarak.</span><span class="sxs-lookup"><span data-stu-id="b84e8-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="b84e8-112">Genel olarak, belirli bir karakteristik (işaretçi) sahip bir sınıfı işaretlemek gerekiyorsa, bir arabirim yerine özel bir öznitelik kullanın.</span><span class="sxs-lookup"><span data-stu-id="b84e8-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="b84e8-113">**✓ DO** bir arabirim uygulaması en az bir türü sağlar.</span><span class="sxs-lookup"><span data-stu-id="b84e8-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="b84e8-114">Arabirim tasarımı doğrulamak için bu yardımcı yapılıyor.</span><span class="sxs-lookup"><span data-stu-id="b84e8-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="b84e8-115">Örneğin, <xref:System.Collections.Generic.List%601> uygulamasıdır <xref:System.Collections.Generic.IList%601> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="b84e8-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="b84e8-116">**✓ DO** tanımladığınız her bir arabirime tüketir en az bir API sağlar (bir parametre veya bir özellik arabirimi alma yöntemi yazılan arabirimi olarak).</span><span class="sxs-lookup"><span data-stu-id="b84e8-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="b84e8-117">Arabirim tasarımı doğrulamak için bu yardımcı yapılıyor.</span><span class="sxs-lookup"><span data-stu-id="b84e8-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="b84e8-118">Örneğin, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> tüketir <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="b84e8-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="b84e8-119">**X DO NOT** önceden sevk edilmiş bir arabirim üye ekleyin.</span><span class="sxs-lookup"><span data-stu-id="b84e8-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="b84e8-120">Bunun yapılması uygulamaları arabiriminin bölün.</span><span class="sxs-lookup"><span data-stu-id="b84e8-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="b84e8-121">Sürüm oluşturma sorunları önlemek için yeni bir arabirim oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b84e8-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="b84e8-122">Bu yönergelere uymanız açıklanan durumlar hariç, genel olarak, arabirimler yerine sınıfları yönetilen kod yeniden kullanılabilir kitaplıklar tasarlama seçtiğiniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b84e8-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="b84e8-123">*Kısımları © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*</span><span class="sxs-lookup"><span data-stu-id="b84e8-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b84e8-124">*İzni Pearson eğitim, Inc. tarafından yeniden yazdırılmaları [çerçeve tasarım yönergeleri: Kuralları, deyimlerini ve yeniden kullanılabilir .NET kitaplıkları, sürüm 2 için desenler](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams, 22 Eki 2008 Addison Wesley Professional ile Microsoft Windows geliştirme serisi bir parçası olarak yayımlandı.*</span><span class="sxs-lookup"><span data-stu-id="b84e8-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84e8-125">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b84e8-125">See also</span></span>

- [<span data-ttu-id="b84e8-126">Tür Tasarımı Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="b84e8-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="b84e8-127">Çerçeve Tasarım Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="b84e8-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
