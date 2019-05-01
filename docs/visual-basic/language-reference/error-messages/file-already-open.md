---
title: Dosya zaten açık
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 401801c7c9072ce11f9eafdb84f2b377669ae545
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802654"
---
# <a name="file-already-open"></a><span data-ttu-id="dbf9b-102">Dosya zaten açık</span><span class="sxs-lookup"><span data-stu-id="dbf9b-102">File already open</span></span>
<span data-ttu-id="dbf9b-103">Bazen bir dosyayı başka önce kapatılması gereken `FileOpen` veya başka bir işlem ortaya çıkabilir.</span><span class="sxs-lookup"><span data-stu-id="dbf9b-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="dbf9b-104">Bu hatanın olası nedenleri arasında:</span><span class="sxs-lookup"><span data-stu-id="dbf9b-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="dbf9b-105">Bir sıralı çıkış modu `FileOpen` işlemi zaten açık olan bir dosya için yürütüldü</span><span class="sxs-lookup"><span data-stu-id="dbf9b-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
- <span data-ttu-id="dbf9b-106">Bir deyimi açık bir dosyaya.</span><span class="sxs-lookup"><span data-stu-id="dbf9b-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dbf9b-107">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="dbf9b-107">To correct this error</span></span>  
  
1. <span data-ttu-id="dbf9b-108">Deyim yürütülmeden önce dosyayı kapatın.</span><span class="sxs-lookup"><span data-stu-id="dbf9b-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf9b-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="dbf9b-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
