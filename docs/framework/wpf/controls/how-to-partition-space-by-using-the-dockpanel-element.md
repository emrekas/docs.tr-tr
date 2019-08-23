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
ms.openlocfilehash: d22a808ce3ab95e3b351408bf4cc372a335da553
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960192"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="8ea06-102">Nasıl yapılır: DockPanel Öğesini Kullanarak Boşluğu Bölümleme</span><span class="sxs-lookup"><span data-stu-id="8ea06-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="8ea06-103">Aşağıdaki örnek, bir [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] <xref:System.Windows.Controls.DockPanel> öğesi kullanılarak basit bir çerçeve oluşturur.</span><span class="sxs-lookup"><span data-stu-id="8ea06-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="8ea06-104">Bölümler <xref:System.Windows.Controls.DockPanel> , alt öğeleri için kullanılabilir alanı.</span><span class="sxs-lookup"><span data-stu-id="8ea06-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ea06-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="8ea06-105">Example</span></span>  
 <span data-ttu-id="8ea06-106">Bu örnek, bölümlenmiş <xref:System.Windows.Controls.DockPanel.Dock%2A> alanın iki özdeş <xref:System.Windows.Controls.Border> öğesini <xref:System.Windows.Controls.Dock.Top> yerleştirmek için iliştirilmiş bir özellik olan özelliğini kullanır.</span><span class="sxs-lookup"><span data-stu-id="8ea06-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="8ea06-107">Üçüncü <xref:System.Windows.Controls.Border> bir öğe, genişliği 200 piksel <xref:System.Windows.Controls.Dock.Left>olarak ayarlanan öğesine yerleştirildi.</span><span class="sxs-lookup"><span data-stu-id="8ea06-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="8ea06-108">Dördüncü <xref:System.Windows.Controls.Border> bir, ekranda yerleşiktir <xref:System.Windows.Controls.Dock.Bottom> .</span><span class="sxs-lookup"><span data-stu-id="8ea06-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="8ea06-109">Son <xref:System.Windows.Controls.Border> öğe kalan alanı otomatik olarak doldurur.</span><span class="sxs-lookup"><span data-stu-id="8ea06-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> <span data-ttu-id="8ea06-110">Varsayılan olarak, bir <xref:System.Windows.Controls.DockPanel> öğenin son alt öğesi kalan ayrılmamış alanı doldurur.</span><span class="sxs-lookup"><span data-stu-id="8ea06-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="8ea06-111">Bu davranışı istemiyorsanız, ayarlayın `LastChildFill="False"`.</span><span class="sxs-lookup"><span data-stu-id="8ea06-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="8ea06-112">Derlenen uygulama, şuna benzeyen yeni bir kullanıcı arabirimi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="8ea06-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="8ea06-113">![Tipik bir DockPanel senaryosu.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="8ea06-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea06-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8ea06-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="8ea06-115">Panellere Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="8ea06-115">Panels Overview</span></span>](panels-overview.md)
