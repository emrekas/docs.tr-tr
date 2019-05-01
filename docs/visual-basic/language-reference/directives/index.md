---
title: Yönergeler (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: 38d54feae5cf7bf41a825d1f6000811e2b56f319
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797854"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="c2cba-102">Yönergeler (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2cba-102">Directives (Visual Basic)</span></span>
<span data-ttu-id="c2cba-103">Bu bölümdeki konular, Visual Basic kaynak kod derleyici yönergeleri belgeleyin.</span><span class="sxs-lookup"><span data-stu-id="c2cba-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c2cba-104">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="c2cba-104">In This Section</span></span>  
 <span data-ttu-id="c2cba-105">[#Const yönergesi](../../../visual-basic/language-reference/directives/const-directive.md) --derleyici sabiti tanımlayın</span><span class="sxs-lookup"><span data-stu-id="c2cba-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="c2cba-106">[#ExternalSource yönergesi](../../../visual-basic/language-reference/directives/externalsource-directive.md) --kaynak satırlarını ve dış kaynak metin arasındaki eşlemeyi gösterir</span><span class="sxs-lookup"><span data-stu-id="c2cba-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="c2cba-107">[#If... Then... #Else yönergesi](../../../visual-basic/language-reference/directives/if-then-else-directives.md) --seçili kod bloklarını derleyin</span><span class="sxs-lookup"><span data-stu-id="c2cba-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="c2cba-108">[#Region yönergesi](../../../visual-basic/language-reference/directives/region-directive.md) --Daralt ve Visual Studio düzenleyicisinde kod bölümlerini Gizle</span><span class="sxs-lookup"><span data-stu-id="c2cba-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="c2cba-109">**#Disable, #Enable** --devre dışı bırakın ve bölgeleri için belirli uyarıları etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="c2cba-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="c2cba-110">Devre dışı bırakabilir ve uyarı kodlarının virgülle ayrılmış bir listesi çok etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="c2cba-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c2cba-111">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="c2cba-111">Related Sections</span></span>  
 [<span data-ttu-id="c2cba-112">Visual Basic Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="c2cba-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  
 [<span data-ttu-id="c2cba-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c2cba-113">Visual Basic</span></span>](../../../visual-basic/index.md)
