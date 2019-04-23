---
title: TreeWalker ile UI Otomasyon Öğeleri Arasında Gezinme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: aed8c624a75364dcc97c73ae7ebd6331275ceff4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182877"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="1f294-102">TreeWalker ile UI Otomasyon Öğeleri Arasında Gezinme</span><span class="sxs-lookup"><span data-stu-id="1f294-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
>  <span data-ttu-id="1f294-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="1f294-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="1f294-104">En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="1f294-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="1f294-105">Bu konuda gezinme gösteren örnek kodu içeren [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] kullanarak öğeleri <xref:System.Windows.Automation.TreeWalker> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="1f294-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f294-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="1f294-106">Example</span></span>  
 <span data-ttu-id="1f294-107">Aşağıdaki örnekte <xref:System.Windows.Automation.TreeWalker.GetParent%2A> gitmeye [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] kök öğe veya Masaüstü bulana kadar ağaç.</span><span class="sxs-lookup"><span data-stu-id="1f294-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="1f294-108">Yalnızca aşağıda belirtilen öğenin üst pencere öğesidir.</span><span class="sxs-lookup"><span data-stu-id="1f294-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="1f294-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="1f294-109">Example</span></span>  
 <span data-ttu-id="1f294-110">Aşağıdaki örnekte <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> ve <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> oluşturmak için bir <xref:System.Windows.Forms.TreeView> tamamını bir alt ağacı gösteren [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] , etkin ve denetim görünümünde olan öğeler.</span><span class="sxs-lookup"><span data-stu-id="1f294-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="1f294-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1f294-111">See also</span></span>

- [<span data-ttu-id="1f294-112">UI Otomasyonu Öğelerini Alma</span><span class="sxs-lookup"><span data-stu-id="1f294-112">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
