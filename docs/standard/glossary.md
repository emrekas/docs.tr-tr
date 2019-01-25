---
title: .NET sözlüğü
description: Seçili koşulları .NET belgelerde kullanılan anlamını öğrenin.
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.technology: dotnet-standard
ms.openlocfilehash: 3c478083a2bfde1742b114a8254bf07dff01f869
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664674"
---
# <a name="net-glossary"></a><span data-ttu-id="2ad90-103">.NET sözlüğü</span><span class="sxs-lookup"><span data-stu-id="2ad90-103">.NET Glossary</span></span>

<span data-ttu-id="2ad90-104">Bu sözlük birincil amacı, seçili terimleri ve tanımları olmadan .NET belgeleri sık görünen kısaltmalar anlamları açıklamak sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-104">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="2ad90-105">AOT</span><span class="sxs-lookup"><span data-stu-id="2ad90-105">AOT</span></span>

<span data-ttu-id="2ad90-106">Derleyici, zaman üretim.</span><span class="sxs-lookup"><span data-stu-id="2ad90-106">Ahead-of-time compiler.</span></span>

<span data-ttu-id="2ad90-107">Benzer şekilde [JIT](#jit), ayrıca bu derleyici çevirir [IL](#il) makine kodu.</span><span class="sxs-lookup"><span data-stu-id="2ad90-107">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="2ad90-108">Uygulama çalıştırılır ve genellikle farklı bir makinede gerçekleştirdiği önce JIT derlemesi aksine AOT derlemesi'olmuyor.</span><span class="sxs-lookup"><span data-stu-id="2ad90-108">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="2ad90-109">Çalışma zamanında AOT takımlarına derlenmemesi çünkü derleme harcanan zamanı en aza indirmek yok.</span><span class="sxs-lookup"><span data-stu-id="2ad90-109">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="2ad90-110">Daha fazla iyileştirme zaman harcamak anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-110">That means they can spend more time optimizing.</span></span> <span data-ttu-id="2ad90-111">AOT bağlamında tüm uygulama olduğundan, AOT derleyici zakazuje optimalizaci bağlama ve tüm başvurular izlenir ve tek bir yürütülebilir dosya oluşturulur ve tüm program analizi de gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-111">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

## <a name="aspnet"></a><span data-ttu-id="2ad90-112">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2ad90-112">ASP.NET</span></span> 

<span data-ttu-id="2ad90-113">.NET Framework ile birlikte gelen özgün ASP.NET uygulaması.</span><span class="sxs-lookup"><span data-stu-id="2ad90-113">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="2ad90-114">Bazen ASP.NET, ASP.NET Core dahil olmak üzere iki ASP.NET uygulamaları için başvuran bir genel bir terimdir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-114">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="2ad90-115">Belirtilen örnek terimi taşıyan anlamı bağlam tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-115">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="2ad90-116">Başvurmak için ASP.NET 4.x, Temizle sağlamak istediğinizde değil kullanmakta olduğunuz ASP.NET hem de uygulamaları auto'yu.</span><span class="sxs-lookup"><span data-stu-id="2ad90-116">Refer to ASP.NET 4.x when you want to make it clear that you’re not using ASP.NET to mean both implementations.</span></span> 

<span data-ttu-id="2ad90-117">Bkz: [ASP.NET belgeleri](/aspnet/#pivot=aspnet).</span><span class="sxs-lookup"><span data-stu-id="2ad90-117">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="2ad90-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2ad90-118">ASP.NET Core</span></span>

<span data-ttu-id="2ad90-119">Platformlar arası, yüksek performanslı, açık kaynaklı bir ASP.NET uygulaması üzerinde .NET Core üzerine kurulmuştur.</span><span class="sxs-lookup"><span data-stu-id="2ad90-119">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="2ad90-120">Bkz: [ASP.NET Core belgeleri](/aspnet/#pivot=core).</span><span class="sxs-lookup"><span data-stu-id="2ad90-120">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="2ad90-121">derleme</span><span class="sxs-lookup"><span data-stu-id="2ad90-121">assembly</span></span>

<span data-ttu-id="2ad90-122">A *.dll*/*.exe* API uygulamaları veya diğer derlemeler tarafından çağrılabilen bir koleksiyonunu içeren dosya.</span><span class="sxs-lookup"><span data-stu-id="2ad90-122">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by applications or other assemblies.</span></span>

<span data-ttu-id="2ad90-123">Bir bütünleştirilmiş kod arabirimleri, sınıflar, yapılar, sabit listeleri ve temsilciler gibi türlerini içerebilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-123">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="2ad90-124">Projenin derlemelerini *bin* klasör bazen denir *ikili dosyaları*.</span><span class="sxs-lookup"><span data-stu-id="2ad90-124">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="2ad90-125">Ayrıca bkz: [Kitaplığı](#library).</span><span class="sxs-lookup"><span data-stu-id="2ad90-125">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="2ad90-126">CLR</span><span class="sxs-lookup"><span data-stu-id="2ad90-126">CLR</span></span>

<span data-ttu-id="2ad90-127">Ortak dil çalışma zamanı.</span><span class="sxs-lookup"><span data-stu-id="2ad90-127">Common Language Runtime.</span></span>

<span data-ttu-id="2ad90-128">Tam anlamı bağlam üzerinde bağlıdır, ancak bu genellikle .NET Framework çalışma zamanını gösterir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-128">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="2ad90-129">CLR bellek ayırma ve management işler.</span><span class="sxs-lookup"><span data-stu-id="2ad90-129">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="2ad90-130">CLR ayrıca yalnızca uygulamaları yürütür, ancak ayrıca oluşturur ve kod üzerinde kolayca kullanarak derler bir sanal makine olduğu bir [JIT](#jit) derleyici.</span><span class="sxs-lookup"><span data-stu-id="2ad90-130">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a [JIT](#jit) compiler.</span></span> <span data-ttu-id="2ad90-131">Geçerli Microsoft CLR Windows yalnızca uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-131">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="2ad90-132">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="2ad90-132">CoreCLR</span></span>

<span data-ttu-id="2ad90-133">.NET core ortak dil çalışma zamanı.</span><span class="sxs-lookup"><span data-stu-id="2ad90-133">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="2ad90-134">Bu CLR aynı kod tabanını CLR oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="2ad90-134">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="2ad90-135">İlk olarak, CoreCLR Silverlight çalışma zamanı olan ve birden çok platformda çalışacak şekilde tasarlanmıştır, özellikle Windows ve OS x CoreCLR, artık .NET Core parçasıdır ve Basitleştirilmiş bir CLR sürümünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="2ad90-135">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="2ad90-136">Hala bir [platformlar arası](#cross-platform) artık çok sayıda Linux dağıtımları da dahil olmak üzere çalışma zamanı.</span><span class="sxs-lookup"><span data-stu-id="2ad90-136">It's still a [cross-platform](#cross-platform) runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="2ad90-137">CoreCLR, ayrıca bir sanal makine JIT ve kod yürütme özelliklere sahip olur.</span><span class="sxs-lookup"><span data-stu-id="2ad90-137">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="2ad90-138">CoreFX</span><span class="sxs-lookup"><span data-stu-id="2ad90-138">CoreFX</span></span>

<span data-ttu-id="2ad90-139">.NET core temel sınıf kitaplığı (BCL)</span><span class="sxs-lookup"><span data-stu-id="2ad90-139">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="2ad90-140">Kümesini oluşturan System.\* kitaplıkları (ve sınırlı bir ölçüde Microsoft.\*) ad alanları.</span><span class="sxs-lookup"><span data-stu-id="2ad90-140">A set of libraries that comprise the System.\* (and to a limited extent  Microsoft.\*) namespaces.</span></span> <span data-ttu-id="2ad90-141">Genel amaçlı, ASP.NET Core gibi daha üst düzey uygulama çerçeveleri yapı üzerinde düşük düzeyli framework BCL olur.</span><span class="sxs-lookup"><span data-stu-id="2ad90-141">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="2ad90-142">.NET Core BCL kaynak kodunu bulunan [Corefx'te depo](https://github.com/dotnet/corefx).</span><span class="sxs-lookup"><span data-stu-id="2ad90-142">The source code of the .NET Core BCL is contained in the [CoreFX repository](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="2ad90-143">Ancak, .NET Core API'ları çoğunu de mevcuttur .NET Framework şekilde Corefx'te .NET Framework BCL çatal olarak düşünebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ad90-143">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="2ad90-144">CoreRT</span><span class="sxs-lookup"><span data-stu-id="2ad90-144">CoreRT</span></span>

<span data-ttu-id="2ad90-145">.NET core çalışma zamanı.</span><span class="sxs-lookup"><span data-stu-id="2ad90-145">.NET Core runtime.</span></span>

<span data-ttu-id="2ad90-146">CLR/CoreCLR aksine CoreRT oluşturmak ve bunu içermez çünkü kod üzerinde kolayca çalıştırmak için özellikleri içermez anlamına gelir. bir sanal makine, değil bir [JIT](#jit).</span><span class="sxs-lookup"><span data-stu-id="2ad90-146">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="2ad90-147">Ancak, dahil [GC](#gc) ve çalışma zamanı türü tanımı (RTTI) ve yansıma olanağı.</span><span class="sxs-lookup"><span data-stu-id="2ad90-147">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="2ad90-148">Böylece meta verilerini yansıma için gerekli değildir, ancak kendi tür sistemi tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-148">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="2ad90-149">Böylece sahip bir [AOT](#aot) aracının koyma gereksiz meta verileri bağlama ve uygulama kullanmayan kod (daha da önemlisi) tanımlamak zinciri.</span><span class="sxs-lookup"><span data-stu-id="2ad90-149">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="2ad90-150">CoreRT geliştirme aşamasında olan.</span><span class="sxs-lookup"><span data-stu-id="2ad90-150">CoreRT is in development.</span></span>

<span data-ttu-id="2ad90-151">Bkz: [.NET Native ve CoreRT giriş](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span><span class="sxs-lookup"><span data-stu-id="2ad90-151">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="cross-platform"></a><span data-ttu-id="2ad90-152">platformlar arası</span><span class="sxs-lookup"><span data-stu-id="2ad90-152">cross-platform</span></span>

<span data-ttu-id="2ad90-153">Geliştirin ve Linux, Windows ve iOS gibi birden çok farklı işletim sistemlerinde özellikle her biri için yeniden yazmak zorunda kalmadan kullanılabilir bir uygulama yürüttüklerinde yeteneği.</span><span class="sxs-lookup"><span data-stu-id="2ad90-153">The ability to develop and execute an application that can be used on multiple different operating systems, such as Linux, Windows and iOS, without having to re-write specifically for each one.</span></span> <span data-ttu-id="2ad90-154">Bu kod yeniden kullanımı ve farklı platformlarda uygulamalar arasında tutarlılık sağlar.</span><span class="sxs-lookup"><span data-stu-id="2ad90-154">This enables code re-use and consistency between applications on different platforms.</span></span>

## <a name="ecosystem"></a><span data-ttu-id="2ad90-155">ekosistemi</span><span class="sxs-lookup"><span data-stu-id="2ad90-155">ecosystem</span></span>

<span data-ttu-id="2ad90-156">Tüm çalışma zamanı yazılım, geliştirme araçlarını ve topluluk kaynakları, derlemek ve çalıştırmak için belirli bir teknoloji uygulamalar için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-156">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="2ad90-157">".NET ekosisteminin" terimi benzer terimleri ".NET yığını" gibi üçüncü taraf uygulamaları ve kitaplıkları edilme farklıdır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-157">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="2ad90-158">Bir tümcedeki bir örnek aşağıdadır:</span><span class="sxs-lookup"><span data-stu-id="2ad90-158">Here's an example in a sentence:</span></span>

- <span data-ttu-id="2ad90-159">"Hacktivism arkasında [.NET Standard](#net-standard) .NET ekosisteminde büyük gerekmemesi oluşturmaktır."</span><span class="sxs-lookup"><span data-stu-id="2ad90-159">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="2ad90-160">çerçeve</span><span class="sxs-lookup"><span data-stu-id="2ad90-160">framework</span></span>

<span data-ttu-id="2ad90-161">Genel olarak, kapsamlı bir API koleksiyonudur, geliştirme ve belirli teknolojiye dayalı uygulamaların dağıtımı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-161">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="2ad90-162">Bu genel olarak, ASP.NET Core ve Windows Forms uygulama çerçeveleri örnekleridir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-162">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="2ad90-163">Ayrıca bkz: [Kitaplığı](#library).</span><span class="sxs-lookup"><span data-stu-id="2ad90-163">See also [library](#library).</span></span>

<span data-ttu-id="2ad90-164">"Framework" sözcüğü aşağıdaki koşulları'nda daha ayrıntılı bir teknik anlamı:</span><span class="sxs-lookup"><span data-stu-id="2ad90-164">The word "framework" has a more specific technical meaning in the following terms:</span></span>
* [<span data-ttu-id="2ad90-165">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ad90-165">.NET Framework</span></span>](#net-framework)
* [<span data-ttu-id="2ad90-166">Hedef Çerçeve</span><span class="sxs-lookup"><span data-stu-id="2ad90-166">target framework</span></span>](#target-framework)
* [<span data-ttu-id="2ad90-167">TFM (hedef çerçeve adı)</span><span class="sxs-lookup"><span data-stu-id="2ad90-167">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="2ad90-168">Mevcut belgelerde başvurduğu bazen "framework" bir [.NET uygulaması](#implementation-of-net).</span><span class="sxs-lookup"><span data-stu-id="2ad90-168">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="2ad90-169">Örneğin, bir makale, bir çerçeve .NET Core çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-169">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="2ad90-170">Bu karmaşık kullanım belgelerinden ortadan kaldırmayı planlıyoruz.</span><span class="sxs-lookup"><span data-stu-id="2ad90-170">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="2ad90-171">GC</span><span class="sxs-lookup"><span data-stu-id="2ad90-171">GC</span></span>

<span data-ttu-id="2ad90-172">Çöp toplayıcı.</span><span class="sxs-lookup"><span data-stu-id="2ad90-172">Garbage collector.</span></span>

<span data-ttu-id="2ad90-173">Çöp toplayıcı otomatik bellek yönetimi uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-173">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="2ad90-174">GC artık kullanımda olmayan nesneler tarafından kapladığı bellek serbest bırakır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-174">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="2ad90-175">Bkz: [çöp toplama](garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ad90-175">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="2ad90-176">IL</span><span class="sxs-lookup"><span data-stu-id="2ad90-176">IL</span></span>

<span data-ttu-id="2ad90-177">Ara dili.</span><span class="sxs-lookup"><span data-stu-id="2ad90-177">Intermediate language.</span></span>

<span data-ttu-id="2ad90-178">C# gibi daha üst düzey .NET dilleri Ara dil (IL) olarak adlandırılır ve Donanım sorun yaşamaz yönerge kümesi aşağı derleyin.</span><span class="sxs-lookup"><span data-stu-id="2ad90-178">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="2ad90-179">IL bazen MSIL (Microsoft IL) veya CIL (ortak IL) adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-179">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="2ad90-180">JIT</span><span class="sxs-lookup"><span data-stu-id="2ad90-180">JIT</span></span>

<span data-ttu-id="2ad90-181">Tam zamanında derleyici.</span><span class="sxs-lookup"><span data-stu-id="2ad90-181">Just-in-time compiler.</span></span>

<span data-ttu-id="2ad90-182">Benzer şekilde [AOT](#aot), bu derleyici çevirir [IL](#il) işlemci anlayan bir makine kodu.</span><span class="sxs-lookup"><span data-stu-id="2ad90-182">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="2ad90-183">AOT, aksine JIT derlemesi isteğe bağlı olur ve kodu çalıştırmak için gereken aynı makineye gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-183">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="2ad90-184">JIT derlemesi uygulamanın yürütülmesi sırasında gerçekleşir olduğundan, derleme zamanında bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-184">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="2ad90-185">Bu nedenle, JIT derleyicileri harcanan zamanı en iyi duruma getirme kodu elde edilen kod üretebilirsiniz tasarruf karşı dengelemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-185">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="2ad90-186">Ancak bir JIT gerçek donanım bilir ve farklı uygulamalar gönderin zorunda geliştiriciler boşaltabilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-186">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="2ad90-187">.NET uygulaması</span><span class="sxs-lookup"><span data-stu-id="2ad90-187">implementation of .NET</span></span>

<span data-ttu-id="2ad90-188">.NET uygulaması şunları içerir:</span><span class="sxs-lookup"><span data-stu-id="2ad90-188">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="2ad90-189">Bir veya daha fazla çalışma zamanları.</span><span class="sxs-lookup"><span data-stu-id="2ad90-189">One or more runtimes.</span></span> <span data-ttu-id="2ad90-190">Örnekler: CLR, CoreCLR, CoreRT.</span><span class="sxs-lookup"><span data-stu-id="2ad90-190">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="2ad90-191">.NET Standard'ın bir sürümünü uygular ve ek API'ler dahil edebilirsiniz bir sınıf kitaplığı.</span><span class="sxs-lookup"><span data-stu-id="2ad90-191">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="2ad90-192">Örnekler: .NET Framework temel sınıf kitaplığı, .NET Core temel sınıf kitaplığı.</span><span class="sxs-lookup"><span data-stu-id="2ad90-192">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="2ad90-193">İsteğe bağlı olarak, bir veya daha fazla uygulama çerçeveleri.</span><span class="sxs-lookup"><span data-stu-id="2ad90-193">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="2ad90-194">Örnekler: ASP.NET, Windows Forms ve WPF, .NET Framework'teki dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-194">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="2ad90-195">İsteğe bağlı olarak, geliştirme araçları.</span><span class="sxs-lookup"><span data-stu-id="2ad90-195">Optionally, development tools.</span></span> <span data-ttu-id="2ad90-196">Bazı geliştirme araçları, birden çok uygulama arasında paylaşılır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-196">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="2ad90-197">.NET uygulamaları örnekleri:</span><span class="sxs-lookup"><span data-stu-id="2ad90-197">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="2ad90-198">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ad90-198">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="2ad90-199">.NET Core</span><span class="sxs-lookup"><span data-stu-id="2ad90-199">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="2ad90-200">Evrensel Windows Platformu (UWP)</span><span class="sxs-lookup"><span data-stu-id="2ad90-200">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="2ad90-201">kitaplık</span><span class="sxs-lookup"><span data-stu-id="2ad90-201">library</span></span>

<span data-ttu-id="2ad90-202">Uygulamaları veya diğer kitaplıkları tarafından çağrılabilen bir API koleksiyonudur.</span><span class="sxs-lookup"><span data-stu-id="2ad90-202">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="2ad90-203">Bir veya daha fazla .NET kitaplığı oluşur [derlemeleri](#assembly).</span><span class="sxs-lookup"><span data-stu-id="2ad90-203">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="2ad90-204">Sözcükleri kitaplığı ve [framework](#framework) genellikle maliyetle aynı anlamda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-204">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="2ad90-205">metapackage</span><span class="sxs-lookup"><span data-stu-id="2ad90-205">metapackage</span></span>

<span data-ttu-id="2ad90-206">Kendi ancak hiçbir kitaplığı olan bir NuGet paketi yalnızca bağımlılıkları bir listesidir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-206">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="2ad90-207">Eklenen paketler, isteğe bağlı olarak bir hedef çerçeve için API bağlantı kurabilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-207">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="2ad90-208">Bkz: [paketler, meta paketler ve çerçeveler](../core/packages.md)</span><span class="sxs-lookup"><span data-stu-id="2ad90-208">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="2ad90-209">Mono</span><span class="sxs-lookup"><span data-stu-id="2ad90-209">Mono</span></span>

<span data-ttu-id="2ad90-210">Mono, bir açık kaynak [platformlar arası](#cross-platform) küçük bir çalışma zamanı gerektiğinde .NET uygulamasında, esas olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-210">Mono is an open source, [cross-platform](#cross-platform) .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="2ad90-211">Bu, Android, Mac, iOS, tvOS ve watchOS Xamarin uygulamalarını çalıştırır ve öncelikli olarak küçük ayak izine gerektiren uygulamaları üzerinde odaklanmıştır çalışma zamanıdır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-211">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="2ad90-212">Tüm şu anda yayımlanan .NET Standard sürümlerini destekler.</span><span class="sxs-lookup"><span data-stu-id="2ad90-212">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="2ad90-213">Tarihsel olarak, Mono .NET Framework'ün daha büyük API uygulanan ve bazı UNIX üzerinde en popüler özelliklerini benzetilmiş.</span><span class="sxs-lookup"><span data-stu-id="2ad90-213">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="2ad90-214">Bazen UNIX bu özellikleri kullanan .NET uygulamaları çalıştırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-214">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="2ad90-215">Mono genellikle bir tam zamanında derleyici ile kullanılır, ancak ayrıca iOS gibi platformlarda kullanılan tam statik bir derleyici (, zamanında tamamlanan derleme) sahiptir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-215">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="2ad90-216">Mono hakkında daha fazla bilgi için bkz: [Mono belgeleri](https://www.mono-project.com/docs/).</span><span class="sxs-lookup"><span data-stu-id="2ad90-216">To learn more about Mono, see the [Mono documentation](https://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="2ad90-217">.NET</span><span class="sxs-lookup"><span data-stu-id="2ad90-217">.NET</span></span>

<span data-ttu-id="2ad90-218">Genel terimi [.NET Standard](#net-standard) ve tüm [.NET uygulamaları](#implementation-of-net) ve iş yükleri.</span><span class="sxs-lookup"><span data-stu-id="2ad90-218">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="2ad90-219">Her zaman büyük harfe, hiçbir zaman ".Net".</span><span class="sxs-lookup"><span data-stu-id="2ad90-219">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="2ad90-220">Bkz: [.NET Kılavuzu](index.md)</span><span class="sxs-lookup"><span data-stu-id="2ad90-220">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="2ad90-221">.NET Core</span><span class="sxs-lookup"><span data-stu-id="2ad90-221">.NET Core</span></span> 

<span data-ttu-id="2ad90-222">.NET bir platformlar arası, yüksek performanslı, açık kaynak uygulaması.</span><span class="sxs-lookup"><span data-stu-id="2ad90-222">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="2ad90-223">Çekirdek ortak dil çalışma zamanı (CoreCLR), çekirdek AOT çalışma zamanı'nı (geliştirme, CoreRT), çekirdek temel sınıf kitaplığı ve Core SDK'sı içerir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-223">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="2ad90-224">Bkz: [.NET Core](../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ad90-224">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="2ad90-225">.NET core CLI</span><span class="sxs-lookup"><span data-stu-id="2ad90-225">.NET Core CLI</span></span>

<span data-ttu-id="2ad90-226">.NET Core uygulamaları geliştirmek için bir çoklu platform araç zinciri.</span><span class="sxs-lookup"><span data-stu-id="2ad90-226">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="2ad90-227">Bkz: [.NET Core komut satırı arabirimi (CLI) araçlarını](../core/tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ad90-227">See [.NET Core command-line interface (CLI) tools](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="2ad90-228">.NET core SDK'sı</span><span class="sxs-lookup"><span data-stu-id="2ad90-228">.NET Core SDK</span></span>

<span data-ttu-id="2ad90-229">Kitaplıklar ve geliştiricilerin, .NET Core uygulamaları ve kitaplıkları oluşturmak araçlar kümesi.</span><span class="sxs-lookup"><span data-stu-id="2ad90-229">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="2ad90-230">İçerir [.NET Core CLI](#net-core-cli) uygulamaları, .NET Core kitaplıkları ve oluşturmak ve çalışan uygulamalar ve dotnet yürütülebilir için çalışma zamanı oluşturmak için (*dotnet.exe*) CLI komutları çalıştırır ve uygulamaları çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-230">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="2ad90-231">Bkz: [.NET Core SDK'ya genel bakış](../core/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="2ad90-231">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="2ad90-232">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ad90-232">.NET Framework</span></span>

<span data-ttu-id="2ad90-233">Yalnızca Windows üzerinde çalışan .NET uygulaması.</span><span class="sxs-lookup"><span data-stu-id="2ad90-233">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="2ad90-234">Ortak dil çalışma zamanı (CLR), temel sınıf kitaplığı ve ASP.NET, Windows Forms ve WPF gibi uygulama framework kitaplıkları içerir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-234">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="2ad90-235">Bkz: [.NET Framework Kılavuzu](../framework/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ad90-235">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="2ad90-236">.NET Yerel</span><span class="sxs-lookup"><span data-stu-id="2ad90-236">.NET Native</span></span>

<span data-ttu-id="2ad90-237">Yerel kod tamamlanan-'ın-time (AOT), just-in-time (JIT) aksine üretir derleyici araç zinciri.</span><span class="sxs-lookup"><span data-stu-id="2ad90-237">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="2ad90-238">Derleme, bir C++ Derleyici ve bağlayıcı çalıştığı benzer şekilde Geliştirici makinesinde gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-238">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="2ad90-239">Kullanılmayan kod kaldırır ve iyileştirmeye daha fazla zaman harcadığını.</span><span class="sxs-lookup"><span data-stu-id="2ad90-239">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="2ad90-240">Bu kod kitaplıklarından ayıklar ve yürütülebilir dosyada birleştirir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-240">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="2ad90-241">Sonuç, tüm uygulamayı temsil eden tek bir modüldür.</span><span class="sxs-lookup"><span data-stu-id="2ad90-241">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="2ad90-242">UWP .NET Native tarafından desteklenen ilk uygulama çerçevesi oluştu.</span><span class="sxs-lookup"><span data-stu-id="2ad90-242">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="2ad90-243">Şimdi, Windows, macOS ve Linux için yerel konsol uygulamaları oluşturmayı destekler.</span><span class="sxs-lookup"><span data-stu-id="2ad90-243">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="2ad90-244">Bkz: [.NET Native ve CoreRT giriş](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span><span class="sxs-lookup"><span data-stu-id="2ad90-244">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="2ad90-245">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="2ad90-245">.NET Standard</span></span>

<span data-ttu-id="2ad90-246">Bir resmi belirtimi .NET API'leri, her bir .NET uygulamasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-246">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="2ad90-247">.NET Standard belirtimi, belge kitaplığında adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-247">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="2ad90-248">API uygulamaları, yalnızca belirtimleri (arabirimleri), bir kitaplık içerdiği için "kitaplık.".NET Standard çağrılacak yanıltıcı</span><span class="sxs-lookup"><span data-stu-id="2ad90-248">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="2ad90-249">.NET Standard metapackage adını yalnızca söz konusu kullanım için belgelerinde dışında ortadan kaldırmak planlıyoruz (`NETStandard.Library`).</span><span class="sxs-lookup"><span data-stu-id="2ad90-249">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="2ad90-250">Bkz: [.NET Standard](net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="2ad90-250">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="2ad90-251">NGEN</span><span class="sxs-lookup"><span data-stu-id="2ad90-251">NGEN</span></span>

<span data-ttu-id="2ad90-252">Yerel (görüntü) oluşturma.</span><span class="sxs-lookup"><span data-stu-id="2ad90-252">Native (image) generation.</span></span>

<span data-ttu-id="2ad90-253">Bu teknoloji kalıcı bir JIT derleyicisi düşünebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ad90-253">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="2ad90-254">Genellikle, burada kod yürütülür, ancak derleme, genellikle yükleme zamanında oluşuyor makine kodu derler.</span><span class="sxs-lookup"><span data-stu-id="2ad90-254">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="2ad90-255">Paket</span><span class="sxs-lookup"><span data-stu-id="2ad90-255">package</span></span>

<span data-ttu-id="2ad90-256">Bir NuGet paketi &mdash; veya yalnızca bir paketi &mdash; olduğu bir *.zip* dosyasıyla birlikte ek meta verileri yazar adı gibi aynı ada sahip bir veya daha fazla derlemeleri.</span><span class="sxs-lookup"><span data-stu-id="2ad90-256">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="2ad90-257">*.Zip* dosyasının bir *.nupkg* uzantısı ve varlıklar gibi içerebilir *.dll* dosyaları ve *.xml* dosyaları, birden çok hedef ile kullanmak için çerçeveler ve sürümleri.</span><span class="sxs-lookup"><span data-stu-id="2ad90-257">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="2ad90-258">Bir uygulama veya kitaplık yüklendiğinde, uygulama veya kitaplık tarafından belirtilen hedef Framework'ü temel uygun varlıkları seçilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-258">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="2ad90-259">Arabirim tanımlayan varlıkları bulunan *ref* klasörü ve uygulanması tanımlamak varlıkları bulunduğunuz *LIB* klasör.</span><span class="sxs-lookup"><span data-stu-id="2ad90-259">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="2ad90-260">platform</span><span class="sxs-lookup"><span data-stu-id="2ad90-260">platform</span></span>

<span data-ttu-id="2ad90-261">Bir işletim sistemi ve Windows, macOS, Linux, iOS ve Android gibi üzerinde çalıştığı donanım.</span><span class="sxs-lookup"><span data-stu-id="2ad90-261">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="2ad90-262">Cümleleri kullanımı örnekleri aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="2ad90-262">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="2ad90-263">".NET core bir çoklu platform .NET uygulamasıdır."</span><span class="sxs-lookup"><span data-stu-id="2ad90-263">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="2ad90-264">".NET Standard platformu belirsiz modundayken PCL profilleri Microsoft platformları gösterir."</span><span class="sxs-lookup"><span data-stu-id="2ad90-264">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="2ad90-265">.NET belgeleri ".NET platformu" sık kullandığı .NET uygulaması ya da dahil tüm uygulamaları .NET yığını auto'yu.</span><span class="sxs-lookup"><span data-stu-id="2ad90-265">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="2ad90-266">Bu kullanımları belgelerinden ortadan kaldırmak planlıyoruz için birincil (işletim sistemi/donanım) anlamı kafanız almak için bu kullanımları her ikisi de eğilimindedir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-266">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="2ad90-267">çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="2ad90-267">runtime</span></span>

<span data-ttu-id="2ad90-268">Yönetilen bir program yürütme ortamı.</span><span class="sxs-lookup"><span data-stu-id="2ad90-268">The execution environment for a managed program.</span></span>

<span data-ttu-id="2ad90-269">İşletim Sisteminin çalışma zamanı ortamının parçası olan ancak .NET çalışma zamanı bir parçası değil.</span><span class="sxs-lookup"><span data-stu-id="2ad90-269">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="2ad90-270">.NET çalışma zamanları bazı örnekleri aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="2ad90-270">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="2ad90-271">Ortak Dil Çalışma Zamanı (CLR)</span><span class="sxs-lookup"><span data-stu-id="2ad90-271">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="2ad90-272">Çekirdek ortak dil çalışma zamanı (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="2ad90-272">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="2ad90-273">(UWP için) .NET native</span><span class="sxs-lookup"><span data-stu-id="2ad90-273">.NET Native (for UWP)</span></span>
- <span data-ttu-id="2ad90-274">Mono çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="2ad90-274">Mono runtime</span></span>

<span data-ttu-id="2ad90-275">.NET belgeleri bazen "çalışma zamanı".NET uygulaması birlikte kullanıldığı senaryolar için kullanır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-275">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="2ad90-276">Örneğin, aşağıdaki cümlelerde, "uygulama" ile "çalışma zamanı" değiştirilmelidir:</span><span class="sxs-lookup"><span data-stu-id="2ad90-276">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="2ad90-277">"Çeşitli .NET çalışma zamanları .NET Standard belirli sürümlerini uygulayın."</span><span class="sxs-lookup"><span data-stu-id="2ad90-277">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="2ad90-278">"Birden çok çalışma zamanları üzerinde çalışması amaçlanmıştır kitaplıkları bu framework hedeflemesi gereken."</span><span class="sxs-lookup"><span data-stu-id="2ad90-278">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="2ad90-279">(.NET Standard başvuran)</span><span class="sxs-lookup"><span data-stu-id="2ad90-279">(referring to .NET Standard)</span></span>
- <span data-ttu-id="2ad90-280">".NET Standard belirli sürümlerini çeşitli .NET çalışma zamanları uygulayın.</span><span class="sxs-lookup"><span data-stu-id="2ad90-280">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="2ad90-281">…</span><span class="sxs-lookup"><span data-stu-id="2ad90-281">…</span></span> <span data-ttu-id="2ad90-282">Her .NET çalışma zamanı sürümünü destekleyen... en yüksek .NET Standard sürümünü bildirir."</span><span class="sxs-lookup"><span data-stu-id="2ad90-282">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="2ad90-283">Bu tutarsız kullanım ortadan kaldırmayı planlıyoruz.</span><span class="sxs-lookup"><span data-stu-id="2ad90-283">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="2ad90-284">yığın</span><span class="sxs-lookup"><span data-stu-id="2ad90-284">stack</span></span>

<span data-ttu-id="2ad90-285">Programlama birlikte oluşturmak ve uygulamaları çalıştırmak için kullanılan teknolojileri kümesi.</span><span class="sxs-lookup"><span data-stu-id="2ad90-285">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="2ad90-286">".NET yığını".NET Standard ve tüm .NET uygulamaları için ifade eder.</span><span class="sxs-lookup"><span data-stu-id="2ad90-286">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="2ad90-287">".NET yığını" tümceciği için bir .NET uygulaması başvurabilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-287">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="2ad90-288">Hedef Çerçeve</span><span class="sxs-lookup"><span data-stu-id="2ad90-288">target framework</span></span>

<span data-ttu-id="2ad90-289">.NET uygulama veya kitaplık dayanan bir API koleksiyonudur.</span><span class="sxs-lookup"><span data-stu-id="2ad90-289">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="2ad90-290">Bir uygulama veya kitaplık belirtimi için standartlaştırılmış bir API kümesi genelinde tüm .NET uygulamalarında olduğu (örneğin, .NET Standard 2.0), .NET Standard'ın bir sürümünü hedefleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ad90-290">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="2ad90-291">Bir uygulama veya kitaplık Ayrıca belirli bir .NET uygulaması sürümü, uygulamaya özel API'lerine erişimi alır durumda hedefleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ad90-291">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="2ad90-292">Örneğin, Xamarin.iOS hedefleyen bir uygulama erişimi için sağlanan Xamarin iOS API sarmalayıcıları alır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-292">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="2ad90-293">Kullanılabilir API'ler, bir .NET uygulamasını yükleyen bir sistemde derlemeler tarafından tanımlanan bazı hedef çerçeveleri için (örneğin, .NET Framework), uygulama çerçevesi API'leri (örneğin, ASP.NET, WinForms) içerebilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-293">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="2ad90-294">(Örneğin, .NET Standard ve .NET Core) paket tabanlı hedef çerçeve için framework API uygulama veya kitaplık yüklü paketleri tarafından tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-294">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="2ad90-295">Bu durumda, hedef Framework'ü örtük olarak birlikte framework yaptığınız tüm paketleri başvuran bir metapackage belirtir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-295">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="2ad90-296">Bkz: [hedef çerçeveyi](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2ad90-296">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="2ad90-297">TFM</span><span class="sxs-lookup"><span data-stu-id="2ad90-297">TFM</span></span>

<span data-ttu-id="2ad90-298">Hedef Çerçeve adı.</span><span class="sxs-lookup"><span data-stu-id="2ad90-298">Target framework moniker.</span></span>

<span data-ttu-id="2ad90-299">Bir .NET uygulaması veya kitaplığı hedef Framework'ü belirtmek için standartlaştırılmış bir belirteci biçimi.</span><span class="sxs-lookup"><span data-stu-id="2ad90-299">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="2ad90-300">Hedef Çerçeve genellikle başvuru kısa bir ad tarafından gibi `net462`.</span><span class="sxs-lookup"><span data-stu-id="2ad90-300">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="2ad90-301">Uzun biçimli Tfm'ler (örn. NETFramework, sürüm 4.6.2 =) var, ancak genellikle bir hedef Framework'ü belirtmek için kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="2ad90-301">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="2ad90-302">Bkz: [hedef çerçeveyi](frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="2ad90-302">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="2ad90-303">UWP</span><span class="sxs-lookup"><span data-stu-id="2ad90-303">UWP</span></span>

<span data-ttu-id="2ad90-304">Evrensel Windows platformu.</span><span class="sxs-lookup"><span data-stu-id="2ad90-304">Universal Windows Platform.</span></span>

<span data-ttu-id="2ad90-305">Windows uygulamaları ve yazılım modern ve Dokunmatik kullanıma nesnelerin interneti için (IOT) oluşturmak için kullanılan bir .NET uygulaması.</span><span class="sxs-lookup"><span data-stu-id="2ad90-305">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="2ad90-306">Bunu hedeflemek isteyebilirsiniz cihazlar farklı türde buluşturulan PC'ler, tabletler, phablets, telefonlar ve bile Xbox dahil olmak üzere tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-306">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="2ad90-307">UWP, merkezi bir mağazaya, Yürütme Ortamı (AppContainer) ve bir dizi yerine Win32 kullanmak için Windows API gibi birçok hizmetleri sunar (WinRT).</span><span class="sxs-lookup"><span data-stu-id="2ad90-307">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="2ad90-308">Uygulamaları, C++, C#, VB.NET ve JavaScript içinde yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="2ad90-308">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="2ad90-309">C# ve vb.NET'TE kullanırken, .NET API'lerini .NET Core tarafından sağlanır.</span><span class="sxs-lookup"><span data-stu-id="2ad90-309">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ad90-310">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2ad90-310">See also</span></span>

- [<span data-ttu-id="2ad90-311">.NET Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="2ad90-311">.NET Guide</span></span>](index.md)
- [<span data-ttu-id="2ad90-312">.NET Framework Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="2ad90-312">.NET Framework Guide</span></span>](../framework/index.md)
- [<span data-ttu-id="2ad90-313">.NET Core</span><span class="sxs-lookup"><span data-stu-id="2ad90-313">.NET Core</span></span>](../core/index.md)
- [<span data-ttu-id="2ad90-314">ASP.NET genel bakış</span><span class="sxs-lookup"><span data-stu-id="2ad90-314">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)
- [<span data-ttu-id="2ad90-315">ASP.NET Core genel bakış</span><span class="sxs-lookup"><span data-stu-id="2ad90-315">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)
