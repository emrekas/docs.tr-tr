---
title: 'Nasıl yapılır: Win32 Konak Kapsayıcısı Kullanan Tıklama Testi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: 8dbc1a3f3d08e50aa9e98971ab340d89aa8099b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727735"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="1f25f-102">Nasıl yapılır: Win32 Konak Kapsayıcısı Kullanan Tıklama Testi</span><span class="sxs-lookup"><span data-stu-id="1f25f-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="1f25f-103">Görsel nesneler içinde oluşturduğunuz bir [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] görsel nesneler için bir konak penceresini kapsayıcı sağlayarak penceresi.</span><span class="sxs-lookup"><span data-stu-id="1f25f-103">You can create visual objects within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="1f25f-104">Olay içindeki görsel nesneler için işleme sağlamak için ana penceresi kapsayıcının İleti Filtresi döngüsüne iletileri işler.</span><span class="sxs-lookup"><span data-stu-id="1f25f-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="1f25f-105">Başvurmak [Öğreticisi: Win32 uygulamasında görsel nesneler barındırma](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) içindeki görsel nesneler barındırma hakkında daha fazla bilgi için bir [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] penceresi.</span><span class="sxs-lookup"><span data-stu-id="1f25f-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f25f-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="1f25f-106">Example</span></span>  
 <span data-ttu-id="1f25f-107">Aşağıdaki kod, fare olay işleyicilerini ayarlama işlemi gösterilmektedir bir [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] pencere konak kapsayıcısı olarak görsel nesneler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1f25f-107">The following code shows how to set up mouse event handlers for a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="1f25f-108">Aşağıdaki örnekte, belirli fare olayları yakalama yanıt isabet sınaması ayarlanacağı gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="1f25f-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="1f25f-109"><xref:System.Windows.Interop.HwndSource> Nesne sunan [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] içerik içinde bir [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] penceresi.</span><span class="sxs-lookup"><span data-stu-id="1f25f-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window.</span></span> <span data-ttu-id="1f25f-110">Değerini <xref:System.Windows.Interop.HwndSource.RootVisual%2A> özelliği <xref:System.Windows.Interop.HwndSource> nesne görsel ağaç hiyerarşisinde en üstteki düğümü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="1f25f-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="1f25f-111">Win32 Konak Kapsayıcısı kullanan isabet sınaması tam örnek nesneleri için bkz. [Win32 birlikte çalışması örnek ile isabet sınaması](https://go.microsoft.com/fwlink/?LinkID=159995).</span><span class="sxs-lookup"><span data-stu-id="1f25f-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f25f-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1f25f-112">See also</span></span>
- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="1f25f-113">Görsel Katmanda Tıklama Testi</span><span class="sxs-lookup"><span data-stu-id="1f25f-113">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="1f25f-114">Öğretici: Win32 uygulamasında görsel nesneler barındırma</span><span class="sxs-lookup"><span data-stu-id="1f25f-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
