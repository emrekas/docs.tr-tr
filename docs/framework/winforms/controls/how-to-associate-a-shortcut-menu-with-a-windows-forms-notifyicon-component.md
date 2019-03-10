---
title: 'Nasıl yapılır: Bir kısayol menüsünü Windows Forms Notifyıcon bileşeniyle ilişkilendirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: e9e50aee63ec36ac005daabed27c3ac3c42a4dc9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720390"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="c4597-102">Nasıl yapılır: Bir kısayol menüsünü Windows Forms Notifyıcon bileşeniyle ilişkilendirme</span><span class="sxs-lookup"><span data-stu-id="c4597-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
>  <span data-ttu-id="c4597-103">Ancak <xref:System.Windows.Forms.MenuStrip> ve <xref:System.Windows.Forms.ContextMenuStrip> değiştirin ve işlevsellik eklemek <xref:System.Windows.Forms.MainMenu> ve <xref:System.Windows.Forms.ContextMenu> denetimleri önceki sürümlerinin <xref:System.Windows.Forms.MainMenu> ve <xref:System.Windows.Forms.ContextMenu> seçerseniz geriye dönük uyumluluk ve gelecekte kullanım için korunur.</span><span class="sxs-lookup"><span data-stu-id="c4597-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="c4597-104"><xref:System.Windows.Forms.NotifyIcon> Bileşen durumu görev çubuğu bildirim alanında bir simge görüntüler.</span><span class="sxs-lookup"><span data-stu-id="c4597-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="c4597-105">Yaygın olarak, uygulamaların komutları temsil ettiği uygulamasına göndermek için bu simgeyi sağ sağlar.</span><span class="sxs-lookup"><span data-stu-id="c4597-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="c4597-106">İlişkilendirerek bir <xref:System.Windows.Forms.ContextMenu> ile bileşen <xref:System.Windows.Forms.NotifyIcon> bileşeni, bu işlev, uygulamalarınıza ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c4597-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4597-107">Uygulamanızın bir örneğini görüntülenirken başlangıçta küçültülmesine istiyorsanız <xref:System.Windows.Forms.NotifyIcon> bileşenini görev çubuğunda, ayarlar ana formun <xref:System.Windows.Forms.Form.WindowState%2A> özelliğini <xref:System.Windows.Forms.FormWindowState.Minimized> ve mutlaka <xref:System.Windows.Forms.NotifyIcon> bileşenin <xref:System.Windows.Forms.NotifyIcon.Visible%2A> özelliği ayarlanır `true`.</span><span class="sxs-lookup"><span data-stu-id="c4597-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="c4597-108">Bir kısayol menü tasarım zamanında Notifyıcon bileşeniyle ilişkilendirme</span><span class="sxs-lookup"><span data-stu-id="c4597-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1.  <span data-ttu-id="c4597-109">Ekleme bir <xref:System.Windows.Forms.NotifyIcon> formunuza, bileşen ve önemli özellikleri ayarlamak <xref:System.Windows.Forms.NotifyIcon.Icon%2A> ve <xref:System.Windows.Forms.NotifyIcon.Visible%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="c4597-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="c4597-110">Daha fazla bilgi için [nasıl yapılır: Forms Notifyıcon bileşeniyle taskbar'a Windows uygulama simgeleri ekleme](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="c4597-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2.  <span data-ttu-id="c4597-111">Ekleme bir <xref:System.Windows.Forms.ContextMenu> Windows formunuza bileşen.</span><span class="sxs-lookup"><span data-stu-id="c4597-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="c4597-112">Çalışma zamanında kullanılabilir hale getirmek istediğiniz komutları temsil eden kısayol menüsüne menü öğeleri ekleme.</span><span class="sxs-lookup"><span data-stu-id="c4597-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="c4597-113">Bu da bu menü öğeleri, erişim anahtarları gibi menüsü geliştirmeleri eklemek için iyi bir zamandır.</span><span class="sxs-lookup"><span data-stu-id="c4597-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3.  <span data-ttu-id="c4597-114">Ayarlama <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> özelliği <xref:System.Windows.Forms.NotifyIcon> eklediğiniz kısayol menüsünü bileşeni.</span><span class="sxs-lookup"><span data-stu-id="c4597-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="c4597-115">Görev çubuğunda simge tıklandığında bu özellik kümesiyle, kısayol menüsünde görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="c4597-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="c4597-116">Kısayol menüsünü program aracılığıyla Notifyıcon bileşeniyle ilişkilendirme</span><span class="sxs-lookup"><span data-stu-id="c4597-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1.  <span data-ttu-id="c4597-117">Bir örneğini oluşturmak <xref:System.Windows.Forms.NotifyIcon> sınıfı ve <xref:System.Windows.Forms.ContextMenu> hangi özellik ayarlarını uygulama için gerekli olan sınıfı (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> ve <xref:System.Windows.Forms.NotifyIcon.Visible%2A> özelliklerini <xref:System.Windows.Forms.NotifyIcon> bileşeni, menü öğelerinin <xref:System.Windows.Forms.ContextMenu> bileşen için).</span><span class="sxs-lookup"><span data-stu-id="c4597-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2.  <span data-ttu-id="c4597-118">Ayarlama <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> özelliği <xref:System.Windows.Forms.NotifyIcon> eklediğiniz kısayol menüsünü bileşeni.</span><span class="sxs-lookup"><span data-stu-id="c4597-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="c4597-119">Görev çubuğunda simge tıklandığında bu özellik kümesiyle, kısayol menüsünde görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="c4597-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4597-120">Aşağıdaki kod örneği, bir temel menüsü yapısı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c4597-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="c4597-121">Menü seçenekleri, geliştirmekte oldukları uygulama sığdırmak için özelleştirme yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="c4597-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="c4597-122">Ayrıca, işlemek üzere kod yazmak isteyeceksiniz <xref:System.Windows.Forms.MenuItem.Click> bu menü öğeleri için olayları.</span><span class="sxs-lookup"><span data-stu-id="c4597-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _   
          (System.Environment.GetFolderPath _   
          (System.Environment.SpecialFolder.Personal)  _   
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
>  <span data-ttu-id="c4597-123">Başlatması gerekir `notifyIcon1` ve `contextMenu1,` formunuza oluşturucuda aşağıdaki ifadeleri ekleyerek yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="c4597-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4597-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c4597-124">See also</span></span>
- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="c4597-125">Nasıl yapılır: Windows Forms Notifyıcon bileşeni taskbar'na uygulama simgeleri ekleme</span><span class="sxs-lookup"><span data-stu-id="c4597-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="c4597-126">NotifyIcon Bileşeni</span><span class="sxs-lookup"><span data-stu-id="c4597-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="c4597-127">NotifyIcon Bileşenine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="c4597-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
