---
title: 'Nasıl yapılır: Windows Forms DataGridView denetiminde verileri doğrulama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: 0ebecac96e110c40b1ed96ecbc5e08ab2ebe12a5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707007"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b5197-102">Nasıl yapılır: Windows Forms DataGridView denetiminde verileri doğrulama</span><span class="sxs-lookup"><span data-stu-id="b5197-102">How to: Validate Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b5197-103">Aşağıdaki kod örneği, içinde bir kullanıcı tarafından girilen verileri doğrulamak gösterilmiştir bir <xref:System.Windows.Forms.DataGridView> denetimi.</span><span class="sxs-lookup"><span data-stu-id="b5197-103">The following code example demonstrates how to validate data entered by a user into a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b5197-104">Bu örnekte, <xref:System.Windows.Forms.DataGridView> satırlardan doldurulur `Customers` Northwind örnek veritabanıyla kurulan tablosu.</span><span class="sxs-lookup"><span data-stu-id="b5197-104">In this example, the <xref:System.Windows.Forms.DataGridView> is populated with rows from the `Customers` table of the Northwind sample database.</span></span> <span data-ttu-id="b5197-105">Kullanıcı bir hücreye zaman düzenlediğini `CompanyName` sütununda, değerini test geçerliliğini, boş olmadığını kontrol ederek.</span><span class="sxs-lookup"><span data-stu-id="b5197-105">When the user edits a cell in the `CompanyName` column, its value is tested for validity by checking that it is not empty.</span></span> <span data-ttu-id="b5197-106">Varsa için olay işleyicisini <xref:System.Windows.Forms.DataGridView.CellValidating> olay bulur değeri boş bir dize olduğunu <xref:System.Windows.Forms.DataGridView> kullanıcının boş olmayan bir dize girilene kadar hücre çıkmasını engeller.</span><span class="sxs-lookup"><span data-stu-id="b5197-106">If the event handler for the <xref:System.Windows.Forms.DataGridView.CellValidating> event finds that the value is an empty string, the <xref:System.Windows.Forms.DataGridView> prevents the user from exiting the cell until a non-empty string is entered.</span></span>  
  
 <span data-ttu-id="b5197-107">Bu kod örneği tam bir açıklaması için bkz. [izlenecek yol: Doğrulama verileri Windows Forms DataGridView denetiminde](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="b5197-107">For a complete explanation of this code example, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5197-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="b5197-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b5197-109">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="b5197-109">Compiling the Code</span></span>  
 <span data-ttu-id="b5197-110">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="b5197-110">This example requires:</span></span>  
  
-   <span data-ttu-id="b5197-111">Sistem, System.Data, System.Windows.Forms ve System.XML derlemesine ilişkin başvurular.</span><span class="sxs-lookup"><span data-stu-id="b5197-111">References to the System, System.Data, System.Windows.Forms and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="b5197-112">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b5197-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b5197-113">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b5197-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b5197-114">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="b5197-114">.NET Framework Security</span></span>  
 <span data-ttu-id="b5197-115">Depolama bağlantı dizesi içinde bir parola gibi hassas bilgileri, uygulamanızın güvenliğini etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="b5197-115">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="b5197-116">Windows Kimlik Doğrulaması (tümleşik güvenlik olarak da bilinir) kullanılarak bir veritabanına erişimi denetlemek için daha güvenli bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="b5197-116">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="b5197-117">Daha fazla bilgi için [bağlantı bilgilerini koruma](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="b5197-117">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5197-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b5197-118">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="b5197-119">İzlenecek yol: Windows Forms DataGridView denetiminde verileri doğrulama</span><span class="sxs-lookup"><span data-stu-id="b5197-119">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b5197-120">Windows Forms DataGridView Denetiminde Veri Girişi</span><span class="sxs-lookup"><span data-stu-id="b5197-120">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b5197-121">İzlenecek yol: Windows Forms DataGridView denetimine veri girişi sırasında oluşan hataları ele alma</span><span class="sxs-lookup"><span data-stu-id="b5197-121">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="b5197-122">Bağlantı Bilgilerini Koruma</span><span class="sxs-lookup"><span data-stu-id="b5197-122">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
