---
title: DLL yüklenirken hata (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: c3f88a5a3c37c89d23055aa413957b2add38ed67
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803473"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="48cce-102">DLL yüklenirken hata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48cce-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="48cce-103">Bir dinamik bağlantı kitaplığı (DLL) belirtilen bir kitaplıktır `Lib` yan tümcesi bir `Declare` deyimi.</span><span class="sxs-lookup"><span data-stu-id="48cce-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="48cce-104">Bu hata için olası nedenler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="48cce-104">Possible causes for this error include:</span></span>  
  
- <span data-ttu-id="48cce-105">DLL yürütülebilir dosya değil.</span><span class="sxs-lookup"><span data-stu-id="48cce-105">The file is not DLL executable.</span></span>  
  
- <span data-ttu-id="48cce-106">Dosya, Microsoft Windows DLL değil.</span><span class="sxs-lookup"><span data-stu-id="48cce-106">The file is not a Microsoft Windows DLL.</span></span>  
  
- <span data-ttu-id="48cce-107">DLL mevcut değilse başka bir DLL başvurusu.</span><span class="sxs-lookup"><span data-stu-id="48cce-107">The DLL references another DLL that is not present.</span></span>  
  
- <span data-ttu-id="48cce-108">DLL veya başvurulan DLL belirtilen yolda bir dizin değil.</span><span class="sxs-lookup"><span data-stu-id="48cce-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="48cce-109">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="48cce-109">To correct this error</span></span>  
  
- <span data-ttu-id="48cce-110">Dosya bir kaynak metin dosyası ve bu nedenle DLL çalıştırılabilir değil ise, derlenmiş ve gerekir DLL yürütülebilir dosya biçimine bağlı.</span><span class="sxs-lookup"><span data-stu-id="48cce-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
- <span data-ttu-id="48cce-111">Microsoft Windows DLL dosyası değil, eşdeğer Microsoft Windows edinin.</span><span class="sxs-lookup"><span data-stu-id="48cce-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
- <span data-ttu-id="48cce-112">DLL mevcut değilse başka bir DLL başvuruyorsa, başvurulan DLL edinin ve kullanılabilir hale getirmek.</span><span class="sxs-lookup"><span data-stu-id="48cce-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
- <span data-ttu-id="48cce-113">DLL veya başvurulan DLL yolu tarafından belirtilen bir dizinde değilse DLL başvurulan bir dizinine taşıyın.</span><span class="sxs-lookup"><span data-stu-id="48cce-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48cce-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="48cce-114">See also</span></span>

- [<span data-ttu-id="48cce-115">Declare Deyimi</span><span class="sxs-lookup"><span data-stu-id="48cce-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
