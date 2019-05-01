---
title: 'Nasıl yapılır: Windows Forms DataGridView Denetimine Veri Girişi Sırasında Oluşan Hataları Ele Alma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: e5ba42c2ff86f46e2722d0f4455c10ab7b85af1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971255"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1eb75-102">Nasıl yapılır: Windows Forms DataGridView Denetimine Veri Girişi Sırasında Oluşan Hataları Ele Alma</span><span class="sxs-lookup"><span data-stu-id="1eb75-102">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1eb75-103">Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir <xref:System.Windows.Forms.DataGridView> rapor veri girişi sırasında oluşan hataları kullanıcı denetimi.</span><span class="sxs-lookup"><span data-stu-id="1eb75-103">The following code example demonstrates how to use the <xref:System.Windows.Forms.DataGridView> control to report data entry errors to the user.</span></span>  
  
 <span data-ttu-id="1eb75-104">Bu kod örneği tam bir açıklaması için bkz. [izlenecek yol: Windows veri girişi sırasında oluşan hataları ele alma Forms DataGridView denetiminde](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="1eb75-104">For a complete explanation of this code example, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eb75-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="1eb75-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1eb75-106">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="1eb75-106">Compiling the Code</span></span>  
 <span data-ttu-id="1eb75-107">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="1eb75-107">This example requires:</span></span>  
  
- <span data-ttu-id="1eb75-108">Sistem, System.Data, System.Windows.Forms ve System.XML derlemesine ilişkin başvurular.</span><span class="sxs-lookup"><span data-stu-id="1eb75-108">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="1eb75-109">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1eb75-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1eb75-110">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1eb75-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1eb75-111">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="1eb75-111">.NET Framework Security</span></span>  
 <span data-ttu-id="1eb75-112">Depolama bağlantı dizesi içinde bir parola gibi hassas bilgileri, uygulamanızın güvenliğini etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="1eb75-112">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="1eb75-113">Windows Kimlik Doğrulaması (tümleşik güvenlik olarak da bilinir) kullanılarak bir veritabanına erişimi denetlemek için daha güvenli bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="1eb75-113">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="1eb75-114">Daha fazla bilgi için [bağlantı bilgilerini koruma](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="1eb75-114">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb75-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1eb75-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="1eb75-116">İzlenecek yol: Windows Forms DataGridView denetimine veri girişi sırasında oluşan hataları ele alma</span><span class="sxs-lookup"><span data-stu-id="1eb75-116">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="1eb75-117">Windows Forms DataGridView Denetiminde Veri Girişi</span><span class="sxs-lookup"><span data-stu-id="1eb75-117">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1eb75-118">İzlenecek yol: Windows Forms DataGridView denetiminde verileri doğrulama</span><span class="sxs-lookup"><span data-stu-id="1eb75-118">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1eb75-119">Bağlantı Bilgilerini Koruma</span><span class="sxs-lookup"><span data-stu-id="1eb75-119">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
