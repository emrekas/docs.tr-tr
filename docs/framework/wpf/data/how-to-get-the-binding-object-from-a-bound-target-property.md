---
title: 'Nasıl yapılır: Bağımlı Hedef Özelliğinden Bağlama Nesnesi Alma'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: 7c7392bc11af57b2e9f27e2302f36efb59d40e9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083120"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="61a7e-102">Nasıl yapılır: Bağımlı Hedef Özelliğinden Bağlama Nesnesi Alma</span><span class="sxs-lookup"><span data-stu-id="61a7e-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="61a7e-103">Bu örnek veri bağımlı hedef özelliğinden bağlama nesnesi elde etme gösterir.</span><span class="sxs-lookup"><span data-stu-id="61a7e-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61a7e-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="61a7e-104">Example</span></span>  
 <span data-ttu-id="61a7e-105">Almak için aşağıdakileri yapabilirsiniz <xref:System.Windows.Data.Binding> nesnesi:</span><span class="sxs-lookup"><span data-stu-id="61a7e-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>  
  
 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  <span data-ttu-id="61a7e-106">Bağımlılık özelliği için birden fazla özellik hedef nesnenin veri bağlama kullanması mümkün olduğundan, istediğiniz bağlama belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="61a7e-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>  
  
 <span data-ttu-id="61a7e-107">Alternatif olarak, alabilirsiniz <xref:System.Windows.Data.BindingExpression> ve ardından değerini almak <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="61a7e-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>  
  
 <span data-ttu-id="61a7e-108">Tam bir örnek için bkz. [bağlama doğrulaması örnek](https://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="61a7e-108">For the complete example see [Binding Validation Sample](https://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61a7e-109">Bağlamanız ise bir <xref:System.Windows.Data.MultiBinding>, kullanın <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="61a7e-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span></span> <span data-ttu-id="61a7e-110">Eğer öyleyse bir <xref:System.Windows.Data.PriorityBinding>, kullanın <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="61a7e-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span></span> <span data-ttu-id="61a7e-111">Hedef özelliği kullanarak mı bağlı emin değilseniz bir <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding>, veya bir <xref:System.Windows.Data.PriorityBinding>, kullanabileceğiniz <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="61a7e-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a7e-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="61a7e-112">See also</span></span>

- [<span data-ttu-id="61a7e-113">Kod İçinde Bağlama Oluşturma</span><span class="sxs-lookup"><span data-stu-id="61a7e-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="61a7e-114">Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="61a7e-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
