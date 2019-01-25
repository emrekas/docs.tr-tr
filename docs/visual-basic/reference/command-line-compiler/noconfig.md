---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: a5663fff6f7351272a78947d364458c83e5b8af1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687602"
---
# <a name="-noconfig"></a><span data-ttu-id="53437-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="53437-102">-noconfig</span></span>
<span data-ttu-id="53437-103">Derleyicinin otomatik olarak yaygın olarak kullanılan başvurmamalıdır olduğunu belirtir [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] derlemeleri veya içeri aktarma `System` ve `Microsoft.VisualBasic` ad alanları.</span><span class="sxs-lookup"><span data-stu-id="53437-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53437-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="53437-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="53437-105">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="53437-105">Remarks</span></span>  
 <span data-ttu-id="53437-106">`-noconfig` Vbc.exe dosyasıyla aynı dizinde bulunan nezahrnovat dosyası derleme değil derleyici seçeneği söyler.</span><span class="sxs-lookup"><span data-stu-id="53437-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="53437-107">Nezahrnovat dosya yaygın olarak kullanılan başvuran [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] derlemeler ve içeri aktarmalar `System` ve `Microsoft.VisualBasic` ad alanları.</span><span class="sxs-lookup"><span data-stu-id="53437-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="53437-108">Derleyici örtük olarak sürece System.dll derlemeye başvuran `-nostdlib` seçeneği belirtildi.</span><span class="sxs-lookup"><span data-stu-id="53437-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="53437-109">`-nostdlib` Seçeneği söyler derleyicinin nezahrnovat ile derleyin veya otomatik olarak System.dll derleme başvurusu değil.</span><span class="sxs-lookup"><span data-stu-id="53437-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53437-110">Mscorlib.dll'nin ve Microsoft.VisualBasic.dll'nin derlemeler her zaman başvurulur.</span><span class="sxs-lookup"><span data-stu-id="53437-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="53437-111">Her Vbc.exe derlemede dahil edilmesi gereken ek derleyici seçeneklerini belirtmek için nezahrnovat dosyasını değiştirebilirsiniz (belirtirken dışındaki `-noconfig` seçeneği).</span><span class="sxs-lookup"><span data-stu-id="53437-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="53437-112">Daha fazla bilgi için [@ (yanıt dosyası belirtme)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="53437-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="53437-113">Derleyici geçirilecek seçeneklerini işler `vbc` son komutu.</span><span class="sxs-lookup"><span data-stu-id="53437-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="53437-114">Bu nedenle, komut satırında herhangi bir seçenek nezahrnovat dosyasında aynı seçeneğinin ayarını geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="53437-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53437-115">`-noconfig` Seçeneği, Visual Studio geliştirme ortamında kullanılabilir değil; yalnızca komut satırından derleme yapılırken kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="53437-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53437-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="53437-116">See also</span></span>
- [<span data-ttu-id="53437-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53437-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="53437-118">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="53437-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="53437-119">@ (Yanıt Dosyasını Belirtin)</span><span class="sxs-lookup"><span data-stu-id="53437-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="53437-120">-başvuru (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53437-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
