---
title: 'Nasıl yapılır: Öğeyi Adına Göre Bulma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: 7405f9ba8db5d4db0ce35ca250f13e456685f39b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757852"
---
# <a name="how-to-find-an-element-by-its-name"></a><span data-ttu-id="25f5e-102">Nasıl yapılır: Öğeyi Adına Göre Bulma</span><span class="sxs-lookup"><span data-stu-id="25f5e-102">How to: Find an Element by Its Name</span></span>
<span data-ttu-id="25f5e-103">Bu örnek nasıl kullanılacağını açıklar <xref:System.Windows.FrameworkElement.FindName%2A> yöntemi tarafından bir öğeyi bulmak için onun <xref:System.Windows.FrameworkElement.Name%2A> değeri.</span><span class="sxs-lookup"><span data-stu-id="25f5e-103">This example describes how to use the <xref:System.Windows.FrameworkElement.FindName%2A> method to find an element by its <xref:System.Windows.FrameworkElement.Name%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25f5e-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="25f5e-104">Example</span></span>  
 <span data-ttu-id="25f5e-105">Bu örnekte, belirli bir öğenin kendi ada göre bulma yöntemi bir düğmesi olay işleyicisi olarak yazılır.</span><span class="sxs-lookup"><span data-stu-id="25f5e-105">In this example, the method to find a particular element by its name is written as the event handler of a button.</span></span> <span data-ttu-id="25f5e-106">`stackPanel` olan <xref:System.Windows.FrameworkElement.Name%2A> kök <xref:System.Windows.FrameworkElement> Aranan ve örnek yöntemin ardından görsel olarak bulunan öğe olarak atayarak gösterir <xref:System.Windows.Controls.TextBlock> ve birini değiştirmeyi <xref:System.Windows.Controls.TextBlock> görünür [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] özellikleri.</span><span class="sxs-lookup"><span data-stu-id="25f5e-106">`stackPanel` is the <xref:System.Windows.FrameworkElement.Name%2A> of the root <xref:System.Windows.FrameworkElement> being searched, and the example method then visually indicates the found element by casting it as <xref:System.Windows.Controls.TextBlock> and changing one of the <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] properties.</span></span>  
  
 [!code-csharp[FEFindName#Find](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
