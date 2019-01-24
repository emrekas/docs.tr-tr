---
title: 'Nasıl yapılır: DockPanel Öğesini Kullanarak Boşluğu Bölümleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: 8b79b89e512ec9da27774188aeaeed8ebd5b1153
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577665"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="520e4-102">Nasıl yapılır: DockPanel Öğesini Kullanarak Boşluğu Bölümleme</span><span class="sxs-lookup"><span data-stu-id="520e4-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="520e4-103">Aşağıdaki örnek, basit bir oluşturur [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework kullanarak bir <xref:System.Windows.Controls.DockPanel> öğesi.</span><span class="sxs-lookup"><span data-stu-id="520e4-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="520e4-104"><xref:System.Windows.Controls.DockPanel> Bölümleri alt öğeleri için kullanılabilir alanı.</span><span class="sxs-lookup"><span data-stu-id="520e4-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="520e4-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="520e4-105">Example</span></span>  
 <span data-ttu-id="520e4-106">Bu örnekte <xref:System.Windows.Controls.DockPanel.Dock%2A> iki özdeş sabitlemek için ekli özelliği, özelliğinin <xref:System.Windows.Controls.Border> öğeler <xref:System.Windows.Controls.Dock.Top> bölümlenmiş.</span><span class="sxs-lookup"><span data-stu-id="520e4-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="520e4-107">Bir üçüncü <xref:System.Windows.Controls.Border> öğesi yerleştirilmiştir <xref:System.Windows.Controls.Dock.Left>, kendi genişlikle 200 piksel olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="520e4-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="520e4-108">Dördüncü <xref:System.Windows.Controls.Border> dayandığı <xref:System.Windows.Controls.Dock.Bottom> ekran.</span><span class="sxs-lookup"><span data-stu-id="520e4-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="520e4-109">Son <xref:System.Windows.Controls.Border> öğesi kalan alanı otomatik olarak doldurur.</span><span class="sxs-lookup"><span data-stu-id="520e4-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="520e4-110">Varsayılan olarak, son alt bir <xref:System.Windows.Controls.DockPanel> öğesi doldurur kalan ayrılmamış.</span><span class="sxs-lookup"><span data-stu-id="520e4-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="520e4-111">Bu davranışı istemiyorsanız ayarlamak `LastChildFill="False"`.</span><span class="sxs-lookup"><span data-stu-id="520e4-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="520e4-112">Derlenmiş uygulama şuna benzer yeni bir kullanıcı Arabirimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="520e4-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="520e4-113">![Tipik bir DockPanel senaryo. ](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="520e4-113">![A typical DockPanel scenario.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="520e4-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="520e4-114">See also</span></span>
- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="520e4-115">Panellere Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="520e4-115">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
