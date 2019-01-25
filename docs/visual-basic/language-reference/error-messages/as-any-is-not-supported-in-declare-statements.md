---
title: '&#39;Tüm&#39; desteklenmeyen &#39;Declare&#39; deyimleri'
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 560ddc8674718f98f3e1a2f6d4facdb198f5e506
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709871"
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a><span data-ttu-id="790d6-102">&#39;Tüm&#39; desteklenmeyen &#39;Declare&#39; deyimleri</span><span class="sxs-lookup"><span data-stu-id="790d6-102">&#39;As Any&#39; is not supported in &#39;Declare&#39; statements</span></span>
<span data-ttu-id="790d6-103">`Any` Veri türü ile kullanıldığında `Declare` deyimleri Visual Basic 6.0 ve önceki sürümlerinde her türden veriyi içerebilir bağımsız değişkenleri kullanımına izin vermek için.</span><span class="sxs-lookup"><span data-stu-id="790d6-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="790d6-104">Bunu yapar ve Visual Basic destekler, ancak aşırı `Any` veri türü geçersiz.</span><span class="sxs-lookup"><span data-stu-id="790d6-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="790d6-105">**Hata Kimliği:** BC30828</span><span class="sxs-lookup"><span data-stu-id="790d6-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="790d6-106">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="790d6-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="790d6-107">Kullanmak istediğiniz belirli türdeki parametreleri bildirme; Örneğin.</span><span class="sxs-lookup"><span data-stu-id="790d6-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="790d6-108">Kullanım <xref:System.Runtime.InteropServices.MarshalAsAttribute> belirtmek için özniteliği `As Any` olduğunda `Void*` çağrılan yordam tarafından beklenir.</span><span class="sxs-lookup"><span data-stu-id="790d6-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="790d6-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="790d6-109">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="790d6-110">İzlenecek yol: Windows API'lerini Çağırma</span><span class="sxs-lookup"><span data-stu-id="790d6-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="790d6-111">Declare Deyimi</span><span class="sxs-lookup"><span data-stu-id="790d6-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="790d6-112">Yönetilen Kodda Prototipler Oluşturma</span><span class="sxs-lookup"><span data-stu-id="790d6-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
