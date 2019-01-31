---
title: EventWaitHandle, CountdownEvent ManualResetEvent
ms.date: 09/14/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c682fbcc09609a9a4e59b29d5c8997a5ae21d2bc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266533"
---
# <a name="eventwaithandle-countdownevent-manualresetevent"></a><span data-ttu-id="c062e-102">EventWaitHandle, CountdownEvent ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="c062e-102">EventWaitHandle, CountdownEvent, ManualResetEvent</span></span>

<span data-ttu-id="c062e-103">Olay bekleme tanıtıcıları birbirine sinyal ve birbirlerinin sinyalleri bekleyen etkinlikleri eşitlemek için iş parçacığı izin verir.</span><span class="sxs-lookup"><span data-stu-id="c062e-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="c062e-104">Bu eşitleme olaylar üzerinde işletim sistemi bekleme tanıtıcıları temel alır ve iki tür olarak ayrılabilir: sinyal olduğunda otomatik olarak sıfırlayan ve el ile Sıfırlanan.</span><span class="sxs-lookup"><span data-stu-id="c062e-104">These synchronization events are based on operating system wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
<span data-ttu-id="c062e-105">Olay bekleme tanıtıcıları, birçok aynı eşitleme senaryolarda kullanışlıdır <xref:System.Threading.Monitor> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="c062e-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="c062e-106">Olay bekleme tanıtıcıları daha kolay genellikle <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> ve <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> yöntemleri ve sinyal üzerinde daha fazla denetim sağlar.</span><span class="sxs-lookup"><span data-stu-id="c062e-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="c062e-107">İzleyicileri uygulama etki alanı için yerel ise adlandırılmış olay bekleme tanıtıcıları uygulama etki alanları ve işlemleri arasında etkinlikleri eşitlemek için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c062e-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c062e-108">Bu bölümde</span><span class="sxs-lookup"><span data-stu-id="c062e-108">In this section</span></span>

 [<span data-ttu-id="c062e-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="c062e-109">EventWaitHandle</span></span>](eventwaithandle.md)  
 <span data-ttu-id="c062e-110"><xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> Veya el ile sıfırlama olayları ve yerel ya da olaylar veya sistem olaylarını adlı sınıfı ya da otomatik temsil eder.</span><span class="sxs-lookup"><span data-stu-id="c062e-110">The <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="c062e-111">ManualResetEvent ve ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="c062e-111">ManualResetEvent and ManualResetEventSlim</span></span>](manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="c062e-112"><xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> Sınıf türetilir <xref:System.Threading.EventWaitHandle> ve el ile sıfırlamanız gerekir yerel bir olayı temsil eder.</span><span class="sxs-lookup"><span data-stu-id="c062e-112">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="c062e-113"><xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> Sınıfı, aynı işlem içinde olaylar için kullanılan basit ve hızlı bir sürümü.</span><span class="sxs-lookup"><span data-stu-id="c062e-113">The <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="c062e-114">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="c062e-114">CountdownEvent</span></span>](countdownevent.md)  
 <span data-ttu-id="c062e-115"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> Sınıfı çatal/birleştir paralellik desenleri bekleme tanıtıcıları kullanan koda uygulanması için basitleştirilmiş bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="c062e-115">The <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c062e-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c062e-116">See also</span></span>

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.Threading.Barrier?displayProperty=nameWithType>
- [<span data-ttu-id="c062e-117">İş parçacığı nesneleri ve özellikleri</span><span class="sxs-lookup"><span data-stu-id="c062e-117">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="c062e-118">Yönetilen iş parçacığı oluşturma temelleri</span><span class="sxs-lookup"><span data-stu-id="c062e-118">Managed threading basics</span></span>](managed-threading-basics.md)
