---
title: Soyut sınıf tasarımı
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: KrzysztofCwalina
ms.openlocfilehash: 6eec3bb4575b89c6476e6c3410050c705141777f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550421"
---
# <a name="abstract-class-design"></a><span data-ttu-id="01619-102">Soyut sınıf tasarımı</span><span class="sxs-lookup"><span data-stu-id="01619-102">Abstract Class Design</span></span>
<span data-ttu-id="01619-103">**X DO NOT** soyut türlerinde genel ya da korumalı iç oluşturucuları tanımlama.</span><span class="sxs-lookup"><span data-stu-id="01619-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="01619-104">Oluşturucular, yalnızca kullanıcıların türünün örneğini oluşturmak gerekir, ortak olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="01619-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="01619-105">Bir soyut türün örneklerini oluşturamayacağınızdan bir public Oluşturucu ile soyut bir tür yanlış ve yanıltıcı kullanıcılar için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="01619-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="01619-106">**✓ DO** korumalı bir ya da bir iç Oluşturucusu soyut sınıflarda tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="01619-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="01619-107">Korumalı Oluşturucu daha yaygın olarak görülür ve yalnızca subtypes oluştururken kendi başlangıç yapmak temel sınıf sağlar.</span><span class="sxs-lookup"><span data-stu-id="01619-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="01619-108">Bir iç Oluşturucu somut uygulamalarını derlemesine olan sınıfı tanımlayan soyut sınıfın sınırlamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="01619-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="01619-109">**✓ DO** sevk her soyut sınıfından devralan en az bir somut türü sağlayın.</span><span class="sxs-lookup"><span data-stu-id="01619-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="01619-110">Soyut sınıf tasarımı doğrulamak için bu yardımcı yapılıyor.</span><span class="sxs-lookup"><span data-stu-id="01619-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="01619-111">Örneğin, <xref:System.IO.FileStream?displayProperty=nameWithType> uygulamasıdır <xref:System.IO.Stream?displayProperty=nameWithType> soyut sınıf.</span><span class="sxs-lookup"><span data-stu-id="01619-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="01619-112">*Kısımları © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*</span><span class="sxs-lookup"><span data-stu-id="01619-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="01619-113">*İzni Pearson eğitim, Inc. tarafından yeniden yazdırılmaları [çerçeve tasarım yönergeleri: Kuralları, deyimlerini ve yeniden kullanılabilir .NET kitaplıkları, sürüm 2 için desenler](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams, 22 Eki 2008 Addison Wesley Professional ile Microsoft Windows geliştirme serisi bir parçası olarak yayımlandı.*</span><span class="sxs-lookup"><span data-stu-id="01619-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01619-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="01619-114">See also</span></span>

- [<span data-ttu-id="01619-115">Tür Tasarımı Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="01619-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="01619-116">Çerçeve Tasarım Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="01619-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
