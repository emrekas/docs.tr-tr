---
title: 'Nasıl yapılır: Windows Forms ListView denetimine sütun ekleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: eed032ec0bacd50666c30979b33362dabf00d565
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700201"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="bd010-102">Nasıl yapılır: Windows Forms ListView denetimine sütun ekleme</span><span class="sxs-lookup"><span data-stu-id="bd010-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="bd010-103">Ayrıntılar görünümünde <xref:System.Windows.Forms.ListView> denetimi, her bir liste öğesi için birden fazla sütun görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bd010-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="bd010-104">Her liste öğesi hakkında bilgi türlerinden kullanıcıya görüntülenecek sütunları kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bd010-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="bd010-105">Örneğin, dosya adı, dosya türü, boyutu ve dosyanın en son değiştirildiği tarih dosyaların listesini görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bd010-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="bd010-106">Oluşturulduktan sonra sütun doldurma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Görüntü denetimiyle Windows sütunlardaki alt öğeleri Forms ListView denetiminde](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="bd010-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="bd010-107">Program aracılığıyla sütunlar eklemek için</span><span class="sxs-lookup"><span data-stu-id="bd010-107">To add columns programmatically</span></span>  
  
1.  <span data-ttu-id="bd010-108">Denetimin ayarlamak <xref:System.Windows.Forms.ListView.View%2A> özelliğini <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="bd010-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2.  <span data-ttu-id="bd010-109">Kullanım <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> liste görünümünün yöntemi <xref:System.Windows.Forms.ListView.Columns%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="bd010-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="bd010-110">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="bd010-110">See also</span></span>
- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="bd010-111">ListView Denetimi</span><span class="sxs-lookup"><span data-stu-id="bd010-111">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
- [<span data-ttu-id="bd010-112">ListView Denetimine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="bd010-112">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
