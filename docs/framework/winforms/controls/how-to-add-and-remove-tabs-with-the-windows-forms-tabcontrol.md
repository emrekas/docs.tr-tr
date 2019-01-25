---
title: 'Nasıl yapılır: Windows Forms TabControl ile sekme ekleyip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: eb3c59a29c9539bcba8827e1a1e9ea807ed44826
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640751"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="2fcfd-102">Nasıl yapılır: Windows Forms TabControl ile sekme ekleyip</span><span class="sxs-lookup"><span data-stu-id="2fcfd-102">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="2fcfd-103">Varsayılan olarak, bir <xref:System.Windows.Forms.TabControl> denetimi içeren iki <xref:System.Windows.Forms.TabPage> kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="2fcfd-103">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="2fcfd-104">Bu sekmeler aracılığıyla erişebileceğiniz <xref:System.Windows.Forms.TabControl.TabPages%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="2fcfd-104">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="2fcfd-105">Program aracılığıyla sekme eklemek için</span><span class="sxs-lookup"><span data-stu-id="2fcfd-105">To add a tab programmatically</span></span>  
  
-   <span data-ttu-id="2fcfd-106">Kullanım <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> yöntemi <xref:System.Windows.Forms.TabControl.TabPages%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="2fcfd-106">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="2fcfd-107">Bir sekme programlı bir şekilde kaldırmak için</span><span class="sxs-lookup"><span data-stu-id="2fcfd-107">To remove a tab programmatically</span></span>  
  
-   <span data-ttu-id="2fcfd-108">Seçili sekmeleri kaldırmak için <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> yöntemi <xref:System.Windows.Forms.TabControl.TabPages%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="2fcfd-108">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="2fcfd-109">-veya-</span><span class="sxs-lookup"><span data-stu-id="2fcfd-109">-or-</span></span>  
  
-   <span data-ttu-id="2fcfd-110">Tüm sekmeler kaldırmak için <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> yöntemi <xref:System.Windows.Forms.TabControl.TabPages%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="2fcfd-110">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2fcfd-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2fcfd-111">See also</span></span>
- [<span data-ttu-id="2fcfd-112">TabControl Denetimine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="2fcfd-112">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="2fcfd-113">Nasıl yapılır: Sekme sayfasına denetim ekleme</span><span class="sxs-lookup"><span data-stu-id="2fcfd-113">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="2fcfd-114">Nasıl yapılır: Sekme sayfalarını devre dışı bırak</span><span class="sxs-lookup"><span data-stu-id="2fcfd-114">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)
- [<span data-ttu-id="2fcfd-115">Nasıl yapılır: Windows Forms Tabcontrol'un görünüşünü değiştirme</span><span class="sxs-lookup"><span data-stu-id="2fcfd-115">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
