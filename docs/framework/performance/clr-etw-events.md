---
title: CLR ETW Olayları
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb7520518497b244be8be3751ca8a3063a02717a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135869"
---
# <a name="clr-etw-events"></a><span data-ttu-id="dd778-102">CLR ETW Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-102">CLR ETW Events</span></span>
<span data-ttu-id="dd778-103">Bu bölümdeki konularda, Windows (ETW) olayları için olay izleme açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="dd778-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="dd778-104">İlişkili bir anahtar sözcüğü her olayda ve düzeyi, açıklanan olduğu [CLR ETW anahtar sözcükleri ve Düzeyler](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) konu.</span><span class="sxs-lookup"><span data-stu-id="dd778-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="dd778-105">CLR olayları için iki sağlayıcıları vardır:</span><span class="sxs-lookup"><span data-stu-id="dd778-105">The CLR has two providers for the events:</span></span>  
  
-   <span data-ttu-id="dd778-106">Çalışma zamanı sağlayıcısı olayları etkin anahtar sözcüklere (olayların kategorilerini) bağlı olarak oluşturur.</span><span class="sxs-lookup"><span data-stu-id="dd778-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="dd778-107">CLR çalışma zamanı sağlayıcısı GUID e13c0d23-ccbc-4e12-931b-d9cc2eee27e4 ' dir.</span><span class="sxs-lookup"><span data-stu-id="dd778-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
-   <span data-ttu-id="dd778-108">Özel amaçlı olan Özet sağlayıcısı kullanır.</span><span class="sxs-lookup"><span data-stu-id="dd778-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="dd778-109">CLR özeti sağlayıcısının GUID a669021c-c450-4609-a035-5af59af4df18.</span><span class="sxs-lookup"><span data-stu-id="dd778-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="dd778-110">Sağlayıcılar hakkında daha fazla bilgi için bkz. [CLR ETW sağlayıcılar](../../../docs/framework/performance/clr-etw-providers.md).</span><span class="sxs-lookup"><span data-stu-id="dd778-110">For more information about the providers, see [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd778-111">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="dd778-111">In This Section</span></span>  
 [<span data-ttu-id="dd778-112">Çalışma Zamanı Bilgileri Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-112">Runtime Information Events</span></span>](../../../docs/framework/performance/runtime-information-etw-events.md)  
 <span data-ttu-id="dd778-113">SKU, sürüm numarası, hangi çalışma zamanı etkinleştirildi, şekilde dahil olmak üzere çalışma zamanı, GUID, (varsa), ile başlatıldığından komut satırı parametreleri hakkında bilgi ve diğer ilgili bilgileri yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="dd778-114">Özel Durum Thrown_V1 Olayı</span><span class="sxs-lookup"><span data-stu-id="dd778-114">Exception Thrown_V1 Event</span></span>](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="dd778-115">Oluşturulan özel durumları hakkında bilgileri yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="dd778-116">Çekişme Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-116">Contention Events</span></span>](../../../docs/framework/performance/contention-etw-events.md)  
 <span data-ttu-id="dd778-117">Çalışma zamanı kullanan İzleyici kilitler veya yerel kilit çakışması bilgilerini yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="dd778-118">İş Parçacığı Havuzu Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-118">Thread Pool Events</span></span>](../../../docs/framework/performance/thread-pool-etw-events.md)  
 <span data-ttu-id="dd778-119">Çalışan iş parçacığı havuzları ve g/ç iş parçacığı havuzları hakkındaki bilgileri yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="dd778-120">Yükleyici Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-120">Loader Events</span></span>](../../../docs/framework/performance/loader-etw-events.md)  
 <span data-ttu-id="dd778-121">Modülleri yükleme ve kaldırma uygulama etki alanları ve derlemeler hakkındaki bilgileri yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="dd778-122">Yöntem Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-122">Method Events</span></span>](../../../docs/framework/performance/method-etw-events.md)  
 <span data-ttu-id="dd778-123">Sembol çözümlemesi için CLR yöntemleri hakkında bilgi yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="dd778-124">Atık Toplama Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-124">Garbage Collection Events</span></span>](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 <span data-ttu-id="dd778-125">Çöp toplama, tanılama ve hata ayıklama amacıyla ilgili bilgileri yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="dd778-126">Olayları Tam Zamanında İzleme</span><span class="sxs-lookup"><span data-stu-id="dd778-126">JIT Tracing Events</span></span>](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 <span data-ttu-id="dd778-127">Just-in-time (JIT) satır içi kullanım ve kuyruk çağrıları hakkındaki bilgileri yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="dd778-128">Birlikte Çalışma Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-128">Interop Events</span></span>](../../../docs/framework/performance/interop-etw-events.md)  
 <span data-ttu-id="dd778-129">Microsoft Ara dili (MSIL) saplama oluşturma ve önbelleğe alma hakkında bilgi yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="dd778-130">ARM Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-130">ARM Events</span></span>](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="dd778-131">Uygulama etki alanı durumu hakkında ayrıntılı tanılama bilgileri çalışın.</span><span class="sxs-lookup"><span data-stu-id="dd778-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="dd778-132">Güvenlik Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-132">Security Events</span></span>](../../../docs/framework/performance/security-etw-events.md)  
 <span data-ttu-id="dd778-133">Tanımlayıcı ad hem de Authenticode doğrulama hakkındaki bilgileri yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="dd778-134">Yığın Olayı</span><span class="sxs-lookup"><span data-stu-id="dd778-134">Stack Event</span></span>](../../../docs/framework/performance/stack-etw-event.md)  
 <span data-ttu-id="dd778-135">Bir olay tetiklenir sonra yığın izlemelerini oluşturmak için kullanılan diğer olaylarla bilgileri yakalar.</span><span class="sxs-lookup"><span data-stu-id="dd778-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd778-136">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="dd778-136">See also</span></span>

- [<span data-ttu-id="dd778-137">Hata ayıklama artırmak ve ETW ile performans ayarlama</span><span class="sxs-lookup"><span data-stu-id="dd778-137">Improve Debugging And Performance Tuning With ETW</span></span>](https://go.microsoft.com/fwlink/?LinkId=179696)
- [<span data-ttu-id="dd778-138">Windows Performans blogu</span><span class="sxs-lookup"><span data-stu-id="dd778-138">Windows Performance Blog</span></span>](https://go.microsoft.com/fwlink/?LinkId=179509)
- [<span data-ttu-id="dd778-139">.NET Framework Günlük Kaydını Denetleme</span><span class="sxs-lookup"><span data-stu-id="dd778-139">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)
- [<span data-ttu-id="dd778-140">CLR ETW Sağlayıcılar</span><span class="sxs-lookup"><span data-stu-id="dd778-140">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)
- [<span data-ttu-id="dd778-141">CLR ETW Anahtar Sözcükleri ve Düzeyler</span><span class="sxs-lookup"><span data-stu-id="dd778-141">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="dd778-142">Ortak Dil Çalışma Zamanında ETW Olayları</span><span class="sxs-lookup"><span data-stu-id="dd778-142">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
