---
title: UI Otomasyonu Kullanarak Denetim Çağırma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: b4ee4b4929d5aa80ccfb91d07031b4ab195d311e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654782"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="48eeb-102">UI Otomasyonu Kullanarak Denetim Çağırma</span><span class="sxs-lookup"><span data-stu-id="48eeb-102">Invoke a Control Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="48eeb-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="48eeb-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="48eeb-104">En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="48eeb-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="48eeb-105">Bu konu aşağıdaki görevlerin nasıl gerçekleştirileceğini gösterir:</span><span class="sxs-lookup"><span data-stu-id="48eeb-105">This topic demonstrates how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="48eeb-106">Denetimin görünümünü walking tarafından belirli özellik koşullara uyan bir denetimi bulmak [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] hedef uygulama için ağacı.</span><span class="sxs-lookup"><span data-stu-id="48eeb-106">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
-   <span data-ttu-id="48eeb-107">Oluşturma bir <xref:System.Windows.Automation.AutomationElement> her denetim için.</span><span class="sxs-lookup"><span data-stu-id="48eeb-107">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
-   <span data-ttu-id="48eeb-108">Elde bir <xref:System.Windows.Automation.InvokePattern> herhangi bir nesneden [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] öğe bulundu destekleyen <xref:System.Windows.Automation.InvokePattern> denetim düzeni.</span><span class="sxs-lookup"><span data-stu-id="48eeb-108">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
-   <span data-ttu-id="48eeb-109">Kullanım <xref:System.Windows.Automation.InvokePattern.Invoke%2A> istemci olay işleyicisi denetiminden çağırmak için.</span><span class="sxs-lookup"><span data-stu-id="48eeb-109">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48eeb-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="48eeb-110">Example</span></span>  
 <span data-ttu-id="48eeb-111">Bu örnekte <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> yöntemi <xref:System.Windows.Automation.AutomationElement> sınıfı oluşturmak için bir <xref:System.Windows.Automation.InvokePattern> nesne ve kullanarak denetim çağırma <xref:System.Windows.Automation.InvokePattern.Invoke%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="48eeb-111">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="48eeb-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="48eeb-112">See also</span></span>
- [<span data-ttu-id="48eeb-113">InvokePattern'ı ve ExpandCollapsePattern'ı menü öğesi örneği</span><span class="sxs-lookup"><span data-stu-id="48eeb-113">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](https://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
