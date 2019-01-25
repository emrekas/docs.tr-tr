---
title: 'Nasıl yapılır: Windows Forms BindingNavigator denetimi ile DataSet Taşı'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: 62cc5598aae646c11c0e46276e2e3dca97edc335
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717824"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="c8b0d-102">Nasıl yapılır: Windows Forms BindingNavigator denetimi ile DataSet Taşı</span><span class="sxs-lookup"><span data-stu-id="c8b0d-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="c8b0d-103">Veri odaklı uygulamalar oluşturmalarını gibi genellikle veri koleksiyonlarının kullanıcılara görüntülenecek gerekir.</span><span class="sxs-lookup"><span data-stu-id="c8b0d-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="c8b0d-104"><xref:System.Windows.Forms.BindingNavigator> Birlikte denetim <xref:System.Windows.Forms.BindingSource> bileşeni, bir koleksiyon içinde taşıma ve öğeleri sıralı olarak görüntülemek için kolay ve Genişletilebilir bir çözüm sağlar.</span><span class="sxs-lookup"><span data-stu-id="c8b0d-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8b0d-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="c8b0d-105">Example</span></span>  
 <span data-ttu-id="c8b0d-106">Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir. bir <xref:System.Windows.Forms.BindingNavigator> veri taşımak için denetimi.</span><span class="sxs-lookup"><span data-stu-id="c8b0d-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="c8b0d-107">Küme içindeki bir <xref:System.Data.DataView>, bağlı bir <xref:System.Windows.Forms.TextBox> denetimini bir <xref:System.Windows.Forms.BindingSource> bileşeni.</span><span class="sxs-lookup"><span data-stu-id="c8b0d-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8b0d-108">Depolama bağlantı dizesi içinde bir parola gibi hassas bilgileri, uygulamanızın güvenliğini etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="c8b0d-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="c8b0d-109">Windows Kimlik Doğrulaması (tümleşik güvenlik olarak da bilinir) kullanılarak bir veritabanına erişimi denetlemek için daha güvenli bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="c8b0d-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="c8b0d-110">Daha fazla bilgi için [bağlantı bilgilerini koruma](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="c8b0d-110">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c8b0d-111">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="c8b0d-111">Compiling the Code</span></span>  
 <span data-ttu-id="c8b0d-112">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="c8b0d-112">This example requires:</span></span>  
  
-   <span data-ttu-id="c8b0d-113">Sistem, System.Data System.Drawing, System.Windows.Forms ve System.Xml derlemesine ilişkin başvurular.</span><span class="sxs-lookup"><span data-stu-id="c8b0d-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="c8b0d-114">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c8b0d-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c8b0d-115">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c8b0d-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="c8b0d-116">Ayrıca bkz: [nasıl yapılır: Derleme ve Visual Studio kullanarak tam bir Windows Formları kod örneği çalıştırma](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="c8b0d-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b0d-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c8b0d-117">See also</span></span>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="c8b0d-118">BindingNavigator Denetimi</span><span class="sxs-lookup"><span data-stu-id="c8b0d-118">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="c8b0d-119">BindingSource Bileşeni</span><span class="sxs-lookup"><span data-stu-id="c8b0d-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [<span data-ttu-id="c8b0d-120">Nasıl yapılır: Bir Windows Forms denetimini bir türe bağlama</span><span class="sxs-lookup"><span data-stu-id="c8b0d-120">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
