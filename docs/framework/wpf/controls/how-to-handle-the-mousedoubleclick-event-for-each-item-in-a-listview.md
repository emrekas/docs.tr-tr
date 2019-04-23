---
title: "Nasıl yapılır: ListView'daki Her Öğe için MouseDoubleClick Olayını İşleme"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 443e5c620ef5bf240d3e317f0234aac0b29b456f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145086"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="f2f2a-102">Nasıl yapılır: ListView'daki Her Öğe için MouseDoubleClick Olayını İşleme</span><span class="sxs-lookup"><span data-stu-id="f2f2a-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="f2f2a-103">Bir öğe için bir olayı işlemek için bir <xref:System.Windows.Controls.ListView>, her bir olay işleyicisi eklemek gereken <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="f2f2a-104">Olduğunda bir <xref:System.Windows.Controls.ListView> bağlı açıkça oluşturmayın bir veri kaynağına bir <xref:System.Windows.Controls.ListViewItem>, ancak ekleyerek her öğe için olayını işleyebilirsiniz bir <xref:System.Windows.EventSetter> stili için bir <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2f2a-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="f2f2a-105">Example</span></span>  
 <span data-ttu-id="f2f2a-106">Aşağıdaki örnek, bir veri bağlama oluşturur <xref:System.Windows.Controls.ListView> ve oluşturan bir <xref:System.Windows.Style> her bir olay işleyicisi eklemek için <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="f2f2a-107">Aşağıdaki örnek tutamaçları <xref:System.Windows.Controls.Control.MouseDoubleClick> olay.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="f2f2a-108">Bağlamak için en yaygın olmasına rağmen bir <xref:System.Windows.Controls.ListView> bir veri kaynağı için her bir olay işleyicisi eklemek için bir stil kullanabilirsiniz <xref:System.Windows.Controls.ListViewItem> bir olmayan-verilere bağlı olarak <xref:System.Windows.Controls.ListView> olup olmadığını açıkça oluşturma bağımsız olarak bir <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="f2f2a-109">Hakkında daha fazla bilgi için açık ve örtük olarak oluşturulan <xref:System.Windows.Controls.ListViewItem> denetimlerini, <xref:System.Windows.Controls.ItemsControl>.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f2a-110">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="f2f2a-111">Veri Bağlamaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="f2f2a-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="f2f2a-112">Stil ve Şablon Oluşturma</span><span class="sxs-lookup"><span data-stu-id="f2f2a-112">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="f2f2a-113">XMLDataProvider ve XPath Sorgularını Kullanarak XML Verilerine Bağlama</span><span class="sxs-lookup"><span data-stu-id="f2f2a-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="f2f2a-114">ListView Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="f2f2a-114">ListView Overview</span></span>](listview-overview.md)
