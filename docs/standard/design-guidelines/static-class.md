---
title: Statik Sınıf Tasarımı
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: KrzysztofCwalina
ms.openlocfilehash: d0a2f11b53f50f2ec2f301f7b88df65e1cd7b811
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762052"
---
# <a name="static-class-design"></a><span data-ttu-id="c7e3e-102">Statik Sınıf Tasarımı</span><span class="sxs-lookup"><span data-stu-id="c7e3e-102">Static Class Design</span></span>
<span data-ttu-id="c7e3e-103">Bir statik sınıf yalnızca statik üyeleri içeren bir sınıfı tanımlanır (kuşkusuz devralınan örnek üyeleri yanı sıra <xref:System.Object?displayProperty=nameWithType> ve büyük olasılıkla bir private Oluşturucu).</span><span class="sxs-lookup"><span data-stu-id="c7e3e-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="c7e3e-104">Bazı diller, statik sınıflar için yerleşik destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="c7e3e-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="c7e3e-105">C# 2.0 ve sonraki sürümlerinde, bir sınıfın statik olarak bildirilmişse, korumalı, soyut olduğu ve hiç örnek üyeleri geçersiz kılınmış veya bildirildi.</span><span class="sxs-lookup"><span data-stu-id="c7e3e-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="c7e3e-106">Statik sınıflar, saf nesne yönelimli tasarım ve Basitlik arasında bir denge sınıflarıdır.</span><span class="sxs-lookup"><span data-stu-id="c7e3e-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="c7e3e-107">Bunlar genellikle diğer işlemler için kısayollar sağlamak için kullanılır (gibi <xref:System.IO.File?displayProperty=nameWithType>), genişletme yöntemleri veya tam nesne yönelimli bir sarmalayıcı olan unwarranted işlevselliği sahipleri (gibi <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="c7e3e-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="c7e3e-108">**✓ DO** statik sınıflar tutumlu kullanın.</span><span class="sxs-lookup"><span data-stu-id="c7e3e-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="c7e3e-109">Statik sınıflar yalnızca için nesne yönelimli core framework'ün destek sınıfları olarak kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="c7e3e-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="c7e3e-110">**X DO NOT** statik sınıflar çeşitli kova olarak ele alın.</span><span class="sxs-lookup"><span data-stu-id="c7e3e-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="c7e3e-111">**X DO NOT** bildirme veya statik sınıflarda örnek üyeleri geçersiz kılın.</span><span class="sxs-lookup"><span data-stu-id="c7e3e-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="c7e3e-112">**✓ DO** statik sınıflar bildirmeniz korumalı, soyut olarak ve programlama diliniz statik sınıflar için yerleşik destek yoksa özel örnek oluşturucu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="c7e3e-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="c7e3e-113">*Kısımları © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*</span><span class="sxs-lookup"><span data-stu-id="c7e3e-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c7e3e-114">*İzni Pearson eğitim, Inc. tarafından yeniden yazdırılmaları [çerçeve tasarım yönergeleri: Kuralları, deyimlerini ve yeniden kullanılabilir .NET kitaplıkları, sürüm 2 için desenler](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams, 22 Eki 2008 Addison Wesley Professional ile Microsoft Windows geliştirme serisi bir parçası olarak yayımlandı.*</span><span class="sxs-lookup"><span data-stu-id="c7e3e-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e3e-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c7e3e-115">See also</span></span>

- [<span data-ttu-id="c7e3e-116">Tür Tasarımı Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="c7e3e-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="c7e3e-117">Çerçeve Tasarım Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="c7e3e-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
