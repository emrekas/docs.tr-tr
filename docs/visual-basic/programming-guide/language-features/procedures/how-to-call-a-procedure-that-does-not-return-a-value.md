---
title: 'Nasıl yapılır: (Visual Basic) bir değer döndürmeyen bir yordam çağırma'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 899c33e6615e2979ba7abe0f537dbe05fd104beb
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965572"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="3a775-102">Nasıl yapılır: (Visual Basic) bir değer döndürmeyen bir yordam çağırma</span><span class="sxs-lookup"><span data-stu-id="3a775-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="3a775-103">A `Sub` yordamın çağrıldığı koda bir değer döndürmüyor.</span><span class="sxs-lookup"><span data-stu-id="3a775-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="3a775-104">Bunu açıkça çağıran bir tek başına deyimiyle çağırmanız.</span><span class="sxs-lookup"><span data-stu-id="3a775-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="3a775-105">Bir ifade içinde adını kullanarak çağrılamıyor.</span><span class="sxs-lookup"><span data-stu-id="3a775-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="3a775-106">Bir alt yordam çağırmak için</span><span class="sxs-lookup"><span data-stu-id="3a775-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="3a775-107">Adını `Sub` yordamı.</span><span class="sxs-lookup"><span data-stu-id="3a775-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="3a775-108">Parantez içine bağımsız değişken listesi için yordamın adıyla izleyin.</span><span class="sxs-lookup"><span data-stu-id="3a775-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="3a775-109">Hiçbir bağımsız değişken varsa, isteğe bağlı olarak ayraçları atlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3a775-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="3a775-110">Ancak, parantezler kullanarak kodunuzu okumayı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="3a775-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="3a775-111">Bağımsız değişken listesi parantezlerinin virgülle ayırarak yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="3a775-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="3a775-112">Bağımsız değişkenler aynı sırada sağladığınız emin olun, `Sub` yordamı karşılık gelen parametreleri tanımlar.</span><span class="sxs-lookup"><span data-stu-id="3a775-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="3a775-113">Aşağıdaki örnek, Visual Basic çağırır <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> uygulama penceresini etkinleştirmek için işlevi.</span><span class="sxs-lookup"><span data-stu-id="3a775-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="3a775-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> pencere başlığı tek bağımsız değişken olarak alır.</span><span class="sxs-lookup"><span data-stu-id="3a775-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="3a775-115">Çağrıldığı koda bir değer döndürmez.</span><span class="sxs-lookup"><span data-stu-id="3a775-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="3a775-116">Bir not defteri işlemi çalışmıyor, örneği oluşturur. bir <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="3a775-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="3a775-117">`Shell` Yordam uygulamalardır belirtilen yolda varsayar.</span><span class="sxs-lookup"><span data-stu-id="3a775-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="3a775-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3a775-118">See also</span></span>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="3a775-119">Yordamlar</span><span class="sxs-lookup"><span data-stu-id="3a775-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="3a775-120">Alt Yordamlar</span><span class="sxs-lookup"><span data-stu-id="3a775-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="3a775-121">Yordam Parametreleri ve Bağımsız Değişkenleri</span><span class="sxs-lookup"><span data-stu-id="3a775-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3a775-122">Sub Deyimi</span><span class="sxs-lookup"><span data-stu-id="3a775-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="3a775-123">Nasıl yapılır: Bir yordam oluşturma</span><span class="sxs-lookup"><span data-stu-id="3a775-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="3a775-124">Nasıl yapılır: Bir değer döndüren bir yordam çağırma</span><span class="sxs-lookup"><span data-stu-id="3a775-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="3a775-125">Nasıl yapılır: Visual Basic olay işleyicisi çağırma</span><span class="sxs-lookup"><span data-stu-id="3a775-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
