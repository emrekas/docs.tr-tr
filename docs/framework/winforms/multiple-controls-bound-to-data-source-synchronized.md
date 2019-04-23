---
title: 'Nasıl yapılır: Aynı Veri Kaynağına Bağlanan Birden Çok Denetimin Eşitlenmiş Kalmasını Sağlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
ms.openlocfilehash: 8f7e59720420a845fa195b8c0fb078a8699a9bc3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170345"
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a><span data-ttu-id="5b911-102">Nasıl yapılır: Aynı Veri Kaynağına Bağlanan Birden Çok Denetimin Eşitlenmiş Kalmasını Sağlama</span><span class="sxs-lookup"><span data-stu-id="5b911-102">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>
<span data-ttu-id="5b911-103">Windows Forms veri bağlama ile önerilmesine çalışırken, birden çok denetim aynı veri kaynağına bağlanır.</span><span class="sxs-lookup"><span data-stu-id="5b911-103">Oftentimes when working with data binding in Windows Forms, multiple controls are bound to the same data source.</span></span> <span data-ttu-id="5b911-104">Bazı durumlarda, bağlı denetimlerin özelliklerini birbirine ve veri kaynağı ile eşitlenmiş kalmasını sağlamak için ek adımlar gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="5b911-104">In some cases, it may be necessary to take extra steps to ensure that the bound properties of the controls remain synchronized with each other and the data source.</span></span> <span data-ttu-id="5b911-105">Bu adımlar, iki durumda gereklidir:</span><span class="sxs-lookup"><span data-stu-id="5b911-105">These steps are necessary in two situations:</span></span>  
  
-   <span data-ttu-id="5b911-106">Veri kaynağı uygulamazsa <xref:System.ComponentModel.IBindingList>ve bu nedenle <xref:System.ComponentModel.IBindingList.ListChanged> türünde olayları <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span><span class="sxs-lookup"><span data-stu-id="5b911-106">If the data source does not implement <xref:System.ComponentModel.IBindingList>, and therefore generate <xref:System.ComponentModel.IBindingList.ListChanged> events of type <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span></span>  
  
-   <span data-ttu-id="5b911-107">Veri kaynağı uygulayan <xref:System.ComponentModel.IEditableObject>.</span><span class="sxs-lookup"><span data-stu-id="5b911-107">If the data source implements <xref:System.ComponentModel.IEditableObject>.</span></span>  
  
 <span data-ttu-id="5b911-108">Önceki durumda kullanabileceğiniz bir <xref:System.Windows.Forms.BindingSource> denetimleri için veri kaynağına bağlamak için.</span><span class="sxs-lookup"><span data-stu-id="5b911-108">In the former case, you can use a <xref:System.Windows.Forms.BindingSource> to bind the data source to the controls.</span></span> <span data-ttu-id="5b911-109">İkinci durumda, kullandığınız bir <xref:System.Windows.Forms.BindingSource> ve işleme <xref:System.Windows.Forms.BindingSource.BindingComplete> olay ve arama <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> ilişkili <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="5b911-109">In the latter case, you use a <xref:System.Windows.Forms.BindingSource> and handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and call <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> on the associated <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b911-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="5b911-110">Example</span></span>  
 <span data-ttu-id="5b911-111">Aşağıdaki kod örneği üç denetimlerinin nasıl bağlanacağını gösterir; iki metin kutusu denetimi ve bir <xref:System.Windows.Forms.DataGridView> denetim — aynı sütuna bir <xref:System.Data.DataSet> kullanarak bir <xref:System.Windows.Forms.BindingSource> bileşeni.</span><span class="sxs-lookup"><span data-stu-id="5b911-111">The following code example demonstrates how to bind three controls—two text-box controls and a <xref:System.Windows.Forms.DataGridView> control—to the same column in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="5b911-112">Bu örnek nasıl işleneceğini gösterir <xref:System.Windows.Forms.BindingSource.BindingComplete> olay olduğunda ek metin kutusuna bir metin kutusunun metin değeri değiştirildiğinde emin olun ve <xref:System.Windows.Forms.DataGridView> denetim doğru değeriyle güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="5b911-112">This example demonstrates how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and ensure that when the text value of one text box is changed, the additional text box and the <xref:System.Windows.Forms.DataGridView> control are updated with the correct value.</span></span>  
  
 <span data-ttu-id="5b911-113">Örnekte bir <xref:System.Windows.Forms.BindingSource> veri kaynağı ve denetimlerini bağlamak için.</span><span class="sxs-lookup"><span data-stu-id="5b911-113">The example uses a <xref:System.Windows.Forms.BindingSource> to bind the data source and the controls.</span></span> <span data-ttu-id="5b911-114">Alternatif olarak, denetimi doğrudan veri kaynağına bağlanır ve alma <xref:System.Windows.Forms.BindingManagerBase> formun bağlamayı için <xref:System.Windows.Forms.Control.BindingContext%2A> ve ardından işleme <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> olayı <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="5b911-114">Alternatively, you can bind the controls directly to the data source and retrieve the <xref:System.Windows.Forms.BindingManagerBase> for the binding from the form's <xref:System.Windows.Forms.Control.BindingContext%2A> and then handle the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event for the <xref:System.Windows.Forms.BindingManagerBase>.</span></span> <span data-ttu-id="5b911-115">Bunu yapmak nasıl bir örneği için yardım sayfasına bakın <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> olayı <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="5b911-115">For an example of how to do this, see the Help page about the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event of <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5b911-116">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="5b911-116">Compiling the Code</span></span>  
  
-   <span data-ttu-id="5b911-117">Bu kod örneği gerektirir</span><span class="sxs-lookup"><span data-stu-id="5b911-117">This code example requires</span></span>  
  
-   <span data-ttu-id="5b911-118">Başvurular <xref:System>, <xref:System.Windows.Forms>, ve <xref:System.Drawing> derlemeler.</span><span class="sxs-lookup"><span data-stu-id="5b911-118">References to the <xref:System>, <xref:System.Windows.Forms>, and <xref:System.Drawing> assemblies.</span></span>  
  
-   <span data-ttu-id="5b911-119">Bir formla <xref:System.Windows.Forms.Form.Load> işlenen olay ve çağrı `InitializeControlsAndDataSource` formun örnekten yönteminde <xref:System.Windows.Forms.Form.Load> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="5b911-119">A form with the <xref:System.Windows.Forms.Form.Load> event handled and a call to the `InitializeControlsAndDataSource` method in the example from the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b911-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5b911-120">See also</span></span>

- [<span data-ttu-id="5b911-121">Nasıl yapılır: Bağlı veri BindingSource bileşenini kullanarak formlar arasında paylaşma</span><span class="sxs-lookup"><span data-stu-id="5b911-121">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](./controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)
- [<span data-ttu-id="5b911-122">Windows Forms Veri Bağlamada Bildirimi Değiştirme</span><span class="sxs-lookup"><span data-stu-id="5b911-122">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="5b911-123">Veri Bağlama ile İlgili Arabirimler</span><span class="sxs-lookup"><span data-stu-id="5b911-123">Interfaces Related to Data Binding</span></span>](interfaces-related-to-data-binding.md)
- [<span data-ttu-id="5b911-124">Windows Forms Veri Bağlama</span><span class="sxs-lookup"><span data-stu-id="5b911-124">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
