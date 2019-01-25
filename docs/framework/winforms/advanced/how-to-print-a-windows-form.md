---
title: 'Nasıl yapılır: Bir Windows formunu yazdırma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 5e672f40797a90111daefed0be74c941d4cc37b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628142"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="28d99-102">Nasıl yapılır: Bir Windows formunu yazdırma</span><span class="sxs-lookup"><span data-stu-id="28d99-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="28d99-103">Geliştirme sürecinin bir parçası olarak, genellikle Windows formunuza bir kopyasını yazdırmak isteyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="28d99-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="28d99-104">Aşağıdaki kod örneği kullanarak geçerli forma bir kopyasını yazdırmak gösterilmektedir <xref:System.Drawing.Graphics.CopyFromScreen%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="28d99-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28d99-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="28d99-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="28d99-106">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="28d99-106">Compiling the Code</span></span>  
 <span data-ttu-id="28d99-107">İçeren tam bir kod örneğini budur bir `Main` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="28d99-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="28d99-108">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="28d99-108">Robust Programming</span></span>  
 <span data-ttu-id="28d99-109">Aşağıdaki koşullar özel bir duruma neden olabilir:</span><span class="sxs-lookup"><span data-stu-id="28d99-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="28d99-110">Yazıcı erişmek için izniniz yok.</span><span class="sxs-lookup"><span data-stu-id="28d99-110">You do not have permission to access the printer.</span></span>  
  
-   <span data-ttu-id="28d99-111">Yüklü yazıcı yok yoktur.</span><span class="sxs-lookup"><span data-stu-id="28d99-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="28d99-112">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="28d99-112">.NET Framework Security</span></span>  
 <span data-ttu-id="28d99-113">Bu kod örneği çalıştırmak için bilgisayarınızda kullandığınız yazıcıya erişim izni olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="28d99-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d99-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="28d99-114">See also</span></span>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="28d99-115">Nasıl yapılır: GDI + ile görüntü işleme</span><span class="sxs-lookup"><span data-stu-id="28d99-115">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
- [<span data-ttu-id="28d99-116">Nasıl yapılır: Windows Forms'ta grafik yazdırma</span><span class="sxs-lookup"><span data-stu-id="28d99-116">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
