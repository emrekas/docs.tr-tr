---
title: 'Nasıl yapılır: Windows Forms BindingNavigator Denetimi ile Verilerde Gezinme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingNavigator control [Windows Forms], navigating data
- data [Windows Forms], navigating
- data navigation
- examples [Windows Forms], BindingNavigator control
ms.assetid: 0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb
ms.openlocfilehash: 81a265d13e94cb623040ad28cf279c0ec5b7887b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590965"
---
# <a name="how-to-navigate-data-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="3d6eb-102">Nasıl yapılır: Windows Forms BindingNavigator Denetimi ile Verilerde Gezinme</span><span class="sxs-lookup"><span data-stu-id="3d6eb-102">How to: Navigate Data with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="3d6eb-103">Gelişinden <xref:System.Windows.Forms.BindingNavigator> denetimini Windows Forms içinde son kullanıcılar oluşturdukları formlarında basit veri gezinti ve düzenleme kullanıcı arabirimi ile sağlamak geliştiricilerin sağlar.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-103">The advent of the <xref:System.Windows.Forms.BindingNavigator> control in Windows Forms enables developers to provide end users with a simple data navigation and manipulation user interface on the forms they create.</span></span>  
  
 <span data-ttu-id="3d6eb-104"><xref:System.Windows.Forms.BindingNavigator> Denetimi bir <xref:System.Windows.Forms.ToolStrip> denetimi düğmeleri ile önceden yapılandırılmış, ilk gezinme için son olarak, bir veri kümesinin yanı sıra ekleme ve silme kayıtlarını düğmeleri sonraki ve önceki kayıt.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-104">The <xref:System.Windows.Forms.BindingNavigator> control is a <xref:System.Windows.Forms.ToolStrip> control with buttons preconfigured for navigation to the first, last, next, and previous record in a data set, as well as buttons to add and delete records.</span></span> <span data-ttu-id="3d6eb-105">Düğmeleri ekleme <xref:System.Windows.Forms.BindingNavigator> denetim kolaydır, çünkü bu bir <xref:System.Windows.Forms.ToolStrip> denetimi.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-105">Adding buttons to the <xref:System.Windows.Forms.BindingNavigator> control is easy, because it is a <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="3d6eb-106">Örnekler için bkz [nasıl yapılır: Yükleme, kaydetme ve ekleme İptal düğmeleri Windows Forms BindingNavigator denetimi](load-save-and-cancel-bindingnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="3d6eb-106">For examples, see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](load-save-and-cancel-bindingnavigator.md).</span></span>  
  
 <span data-ttu-id="3d6eb-107">Her düğme için <xref:System.Windows.Forms.BindingNavigator> karşılık gelen bir üyesi olduğunda, Denetim <xref:System.Windows.Forms.BindingSource> programlı olarak aynı işlevselliği sağlayan bileşeni.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-107">For each button on the <xref:System.Windows.Forms.BindingNavigator> control, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically allows the same functionality.</span></span> <span data-ttu-id="3d6eb-108">Örneğin, <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> düğmesi karşılık gelen <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> yöntemi <xref:System.Windows.Forms.BindingSource> bileşeni <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> düğmesi karşılık gelen <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> yöntemi ve benzeri.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-108">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span> <span data-ttu-id="3d6eb-109">Sonuç olarak, etkinleştirme <xref:System.Windows.Forms.BindingNavigator> denetimi veri Kayıtlarda gezinmek için basit bir ayarı olarak kendi <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> özelliğini uygun <xref:System.Windows.Forms.BindingSource> formdaki bileşen.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-109">As a result, enabling the <xref:System.Windows.Forms.BindingNavigator> control to navigate data records is a simple as setting its <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the appropriate <xref:System.Windows.Forms.BindingSource> component on the form.</span></span>  
  
### <a name="to-set-up-the-bindingnavigator-control"></a><span data-ttu-id="3d6eb-110">BindingNavigator denetimi ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="3d6eb-110">To set up the BindingNavigator control</span></span>  
  
1. <span data-ttu-id="3d6eb-111">Ekleme bir <xref:System.Windows.Forms.BindingSource> bileşeninizin `bindingSource1` ve iki <xref:System.Windows.Forms.TextBox> adlarında `textBox1` ve `textBox2`.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-111">Add a <xref:System.Windows.Forms.BindingSource> component named `bindingSource1` and two <xref:System.Windows.Forms.TextBox> controls named `textBox1` and `textBox2`.</span></span>  
  
2. <span data-ttu-id="3d6eb-112">Bağlama `bindingSource1` veri ve metin denetimlerine `bindingSource1`.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-112">Bind `bindingSource1` to data, and the textbox controls to `bindingSource1`.</span></span> <span data-ttu-id="3d6eb-113">Bunu yapmak için aşağıdaki kodu, form ve çağrı yapıştırın `LoadData` formun oluşturucudan veya <xref:System.Windows.Forms.Form.Load> olay işleme yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-113">To do this, paste the following code into your form and call `LoadData` from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="3d6eb-114">Ekleme bir <xref:System.Windows.Forms.BindingNavigator> adlı Denetim `bindingNavigator1` formunuza.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-114">Add a <xref:System.Windows.Forms.BindingNavigator> control named `bindingNavigator1` to your form.</span></span>  
  
4. <span data-ttu-id="3d6eb-115">Ayarlama <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> özelliği `bindingNavigator1` için `bindingSource1`.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-115">Set the <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property for `bindingNavigator1` to `bindingSource1`.</span></span> <span data-ttu-id="3d6eb-116">Tasarımcı ile veya kod bunu yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-116">You can do this with the designer or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="3d6eb-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="3d6eb-117">Example</span></span>  
 <span data-ttu-id="3d6eb-118">Aşağıdaki kod örneği, tam bir örnek daha önce listelenen adımları için ' dir.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-118">The following code example is the complete example for the steps listed previously.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3d6eb-119">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="3d6eb-119">Compiling the Code</span></span>  
 <span data-ttu-id="3d6eb-120">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="3d6eb-120">This example requires:</span></span>  
  
- <span data-ttu-id="3d6eb-121">Sistem, System.Data System.Drawing, System.Windows.Forms ve System.Xml derlemesine ilişkin başvurular.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-121">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6eb-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3d6eb-122">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="3d6eb-123">BindingNavigator Denetimi</span><span class="sxs-lookup"><span data-stu-id="3d6eb-123">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="3d6eb-124">ToolStrip Denetimi</span><span class="sxs-lookup"><span data-stu-id="3d6eb-124">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
