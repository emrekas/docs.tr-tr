---
title: WPF Uygulama Performansını İyileştirme
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 45618e6180cbe0206eb120fc71726d0b8de5f06d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511598"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="cc66d-102">WPF Uygulama Performansını İyileştirme</span><span class="sxs-lookup"><span data-stu-id="cc66d-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="cc66d-103">Bu bölüm için bir başvuru olarak hazırlanmıştır [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] uygulama geliştiriciler ait uygulamaların performansını artırmanın yollarını arıyoruz.</span><span class="sxs-lookup"><span data-stu-id="cc66d-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="cc66d-104">Microsoft .NET Framework için yeni bir geliştirici olup olmadığını ve [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], önce her iki platform ile planladığınızdan.</span><span class="sxs-lookup"><span data-stu-id="cc66d-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="cc66d-105">Bu bölümde her ikisinde de bilgili varsayar ve uygulamalarıyla çalışmaya başlamak için bildiklerinizi programcılar için yazılmıştır.</span><span class="sxs-lookup"><span data-stu-id="cc66d-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc66d-106">Bu bölümde sağlanan performans verileri dayalı [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] RAM ve ATI Radeon 9700 2,8 GHz PC 512 ile çalışan uygulamalar grafik kartı.</span><span class="sxs-lookup"><span data-stu-id="cc66d-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc66d-107">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="cc66d-107">In This Section</span></span>  
 [<span data-ttu-id="cc66d-108">Uygulama Performansını Planlama</span><span class="sxs-lookup"><span data-stu-id="cc66d-108">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
  
 [<span data-ttu-id="cc66d-109">Donanımdan Yararlanma</span><span class="sxs-lookup"><span data-stu-id="cc66d-109">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="cc66d-110">Düzen ve Tasarım</span><span class="sxs-lookup"><span data-stu-id="cc66d-110">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="cc66d-111">2B Grafikleri ve Görüntüleme</span><span class="sxs-lookup"><span data-stu-id="cc66d-111">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="cc66d-112">Nesne Davranışı</span><span class="sxs-lookup"><span data-stu-id="cc66d-112">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="cc66d-113">Uygulama Kaynakları</span><span class="sxs-lookup"><span data-stu-id="cc66d-113">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="cc66d-114">Metin</span><span class="sxs-lookup"><span data-stu-id="cc66d-114">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
  
 [<span data-ttu-id="cc66d-115">Veri Bağlama</span><span class="sxs-lookup"><span data-stu-id="cc66d-115">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="cc66d-116">Denetimler</span><span class="sxs-lookup"><span data-stu-id="cc66d-116">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)  
  
 [<span data-ttu-id="cc66d-117">Diğer Performans Önerileri</span><span class="sxs-lookup"><span data-stu-id="cc66d-117">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="cc66d-118">Uygulama Başlangıç Zamanı</span><span class="sxs-lookup"><span data-stu-id="cc66d-118">Application Startup Time</span></span>](../../../../docs/framework/wpf/advanced/application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="cc66d-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cc66d-119">See also</span></span>
- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="cc66d-120">Grafik İşleme Katmanları</span><span class="sxs-lookup"><span data-stu-id="cc66d-120">Graphics Rendering Tiers</span></span>](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)
- [<span data-ttu-id="cc66d-121">WPF Grafik İşlemeye Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="cc66d-121">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="cc66d-122">Düzen</span><span class="sxs-lookup"><span data-stu-id="cc66d-122">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)
- [<span data-ttu-id="cc66d-123">WPF İçinde Ağaçlar</span><span class="sxs-lookup"><span data-stu-id="cc66d-123">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
- [<span data-ttu-id="cc66d-124">Çizim Nesnelerine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="cc66d-124">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="cc66d-125">DrawingVisual Nesnelerini Kullanma</span><span class="sxs-lookup"><span data-stu-id="cc66d-125">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="cc66d-126">Bağımlılık Özelliklerine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="cc66d-126">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [<span data-ttu-id="cc66d-127">Freezable Nesnelerine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="cc66d-127">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [<span data-ttu-id="cc66d-128">XAML Kaynakları</span><span class="sxs-lookup"><span data-stu-id="cc66d-128">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [<span data-ttu-id="cc66d-129">WPF'deki Belgeler</span><span class="sxs-lookup"><span data-stu-id="cc66d-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [<span data-ttu-id="cc66d-130">Biçimlendirilmiş Metin Çizme</span><span class="sxs-lookup"><span data-stu-id="cc66d-130">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
- [<span data-ttu-id="cc66d-131">WPF'de Tipografi</span><span class="sxs-lookup"><span data-stu-id="cc66d-131">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)
- [<span data-ttu-id="cc66d-132">Veri Bağlamaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="cc66d-132">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="cc66d-133">Gezintiye Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="cc66d-133">Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/navigation-overview.md)
- [<span data-ttu-id="cc66d-134">Animasyon İpuçları ve Püf Noktaları</span><span class="sxs-lookup"><span data-stu-id="cc66d-134">Animation Tips and Tricks</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="cc66d-135">İzlenecek yol: Bir WPF uygulamasında uygulama verilerini önbelleğe alma</span><span class="sxs-lookup"><span data-stu-id="cc66d-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
