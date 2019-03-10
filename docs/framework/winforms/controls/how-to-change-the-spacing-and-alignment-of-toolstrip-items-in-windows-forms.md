---
title: "Nasıl yapılır: Aralık ve Windows Forms'ta ToolStrip öğeleri hizalamasını değiştirme"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 954087fa893baf3aa623c912efb081491304d3fb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719448"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="1b158-102">Nasıl yapılır: Aralık ve Windows Forms'ta ToolStrip öğeleri hizalamasını değiştirme</span><span class="sxs-lookup"><span data-stu-id="1b158-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="1b158-103"><xref:System.Windows.Forms.ToolStrip> Denetimi boyutlandırma, aralıkları gibi düzen özellikleri tam olarak destekler <xref:System.Windows.Forms.ToolStripItem> denetimleri birbirine göre denetimlerin düzenlemesini üzerinde <xref:System.Windows.Forms.ToolStrip>ve denetimleri göreli aralığını <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="1b158-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="1b158-104">Çünkü varsayılan değerini <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> özelliği `true`, denetimleri boyutta otomatik olarak ayarlamadığınız sürece <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> özelliğini `false`.</span><span class="sxs-lookup"><span data-stu-id="1b158-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="1b158-105">El ile ToolStripItem boyutlandırmak için</span><span class="sxs-lookup"><span data-stu-id="1b158-105">To manually size a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="1b158-106">Ayarlama <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> özelliğini `false` ilişkili denetimi.</span><span class="sxs-lookup"><span data-stu-id="1b158-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  <span data-ttu-id="1b158-107">Ayarlama <xref:System.Windows.Forms.ToolStripItem.Size%2A> özelliği ilişkili için istediğiniz şekilde <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="1b158-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="1b158-108">ToolStripItem aralığını ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="1b158-108">To set the spacing of a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="1b158-109">Piksel cinsinden istenen değerleri eklemek <xref:System.Windows.Forms.ToolStripItem.Margin%2A> ilişkili denetiminin özelliği.</span><span class="sxs-lookup"><span data-stu-id="1b158-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="1b158-110">Değerlerini <xref:System.Windows.Forms.ToolStripItem.Margin%2A> özelliği şu sırayla bitişik öğelerin ve öğe aralığını belirtin: Sol, üst, sağ ve alt.</span><span class="sxs-lookup"><span data-stu-id="1b158-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="1b158-111">ToolStrip sağ tarafına ToolStripItem hizalamak için</span><span class="sxs-lookup"><span data-stu-id="1b158-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1.  <span data-ttu-id="1b158-112">Ayarlama <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> özelliğini <xref:System.Windows.Forms.ToolStripItemAlignment.Right> ilişkili denetimi.</span><span class="sxs-lookup"><span data-stu-id="1b158-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="1b158-113">Varsayılan olarak, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> ayarlanır <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, denetimleri sol tarafıyla hizalar <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="1b158-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="1b158-114">ToolStrip öğeler şeridindeki düzenlemek için</span><span class="sxs-lookup"><span data-stu-id="1b158-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
-   <span data-ttu-id="1b158-115">Ayarlama <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> değere <xref:System.Windows.Forms.ToolStripLayoutStyle> istediğiniz.</span><span class="sxs-lookup"><span data-stu-id="1b158-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1b158-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1b158-116">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="1b158-117">ToolStrip Denetimine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="1b158-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="1b158-118">ToolStrip Denetim, Mimarisi</span><span class="sxs-lookup"><span data-stu-id="1b158-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="1b158-119">ToolStrip Teknoloji Özeti</span><span class="sxs-lookup"><span data-stu-id="1b158-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
