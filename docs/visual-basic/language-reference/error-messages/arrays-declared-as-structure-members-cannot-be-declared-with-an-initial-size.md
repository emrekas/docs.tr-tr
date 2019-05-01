---
title: Yapı üyeleri olarak bildirilen diziler için başlangıç boyutu bildirilemez
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 5d58b531b670715716e849cd37227bc899195df6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935375"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="8a185-102">Yapı üyeleri olarak bildirilen diziler için başlangıç boyutu bildirilemez</span><span class="sxs-lookup"><span data-stu-id="8a185-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="8a185-103">Bir yapıdaki dizi başlangıç boyutuyla bildirilir.</span><span class="sxs-lookup"><span data-stu-id="8a185-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="8a185-104">Herhangi bir yapı öğe başlatılamıyor ve bir dizi boyutu bildirme bir başlatma biçimidir.</span><span class="sxs-lookup"><span data-stu-id="8a185-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="8a185-105">**Hata Kimliği:** BC31043</span><span class="sxs-lookup"><span data-stu-id="8a185-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8a185-106">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="8a185-106">To correct this error</span></span>  
  
1. <span data-ttu-id="8a185-107">Dizi, yapısında (ilk boyut) dinamik tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="8a185-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2. <span data-ttu-id="8a185-108">Belirli bir dizinin boyutunu gerekiyorsa, dinamik bir dizi ile redimension bir [ReDim deyimi](../../../visual-basic/language-reference/statements/redim-statement.md) kodunuz çalışırken.</span><span class="sxs-lookup"><span data-stu-id="8a185-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="8a185-109">Aşağıdaki örnek bunu göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="8a185-109">The following example illustrates this.</span></span>  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8a185-110">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8a185-110">See also</span></span>

- [<span data-ttu-id="8a185-111">Diziler</span><span class="sxs-lookup"><span data-stu-id="8a185-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="8a185-112">Nasıl yapılır: Yapıyı Bildirme</span><span class="sxs-lookup"><span data-stu-id="8a185-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
