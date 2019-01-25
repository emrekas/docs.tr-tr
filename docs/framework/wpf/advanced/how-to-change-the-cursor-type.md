---
title: 'Nasıl yapılır: İmleç Türünü Değiştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 2330cdd3be35dc4e4b555db6401dd55d9946ed1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745057"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="c3645-102">Nasıl yapılır: İmleç Türünü Değiştirme</span><span class="sxs-lookup"><span data-stu-id="c3645-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="c3645-103">Bu örnek nasıl değiştirileceğini gösterir <xref:System.Windows.Input.Cursor> uygulama ve belirli bir öğe için fare işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="c3645-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="c3645-104">Bu örnekte oluşan bir [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] dosyası ve bir arka plan kod dosyasında.</span><span class="sxs-lookup"><span data-stu-id="c3645-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3645-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="c3645-105">Example</span></span>  
 <span data-ttu-id="c3645-106">Kullanıcı arabirimi oluşturulur, oluşan bir <xref:System.Windows.Controls.ComboBox> istenen seçilecek <xref:System.Windows.Input.Cursor>, bir çift <xref:System.Windows.Controls.RadioButton> imleç değişiklik yalnızca tek bir öğeyi uygular veya tüm uygulama için geçerli belirlemek için nesneleri ve <xref:System.Windows.Controls.Border> Yeni imleç uygulanan bir öğenin olan.</span><span class="sxs-lookup"><span data-stu-id="c3645-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="c3645-107">Aşağıdaki kod oluşturur bir <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> İmleç türünü değiştiğinde çağrılan olay işleyicisi <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="c3645-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="c3645-108">Switch deyimi filtreler imleç adı ve kümelerini <xref:System.Windows.FrameworkElement.Cursor%2A> özelliği <xref:System.Windows.Controls.Border> olarak adlandırılmış *DisplayArea*.</span><span class="sxs-lookup"><span data-stu-id="c3645-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="c3645-109">İmleç Değiştir "Tüm uygulamaya" olarak ayarlanmışsa <xref:System.Windows.Input.Mouse.OverrideCursor%2A> özelliği <xref:System.Windows.FrameworkElement.Cursor%2A> özelliği <xref:System.Windows.Controls.Border> denetimi.</span><span class="sxs-lookup"><span data-stu-id="c3645-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="c3645-110">Bu, tüm uygulama için değiştirmek için imleç zorlar.</span><span class="sxs-lookup"><span data-stu-id="c3645-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="c3645-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c3645-111">See also</span></span>
- [<span data-ttu-id="c3645-112">Girişe Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="c3645-112">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
