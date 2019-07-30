---
title: 'Nasıl yapılır: Uzun bir nitelik yolu (Visual Basic) ile bir nesneye erişimi hızlandırma'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: a8e50a2ed04037b48091321dc0c9ac2ea1db35f4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631091"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="3f429-102">Nasıl yapılır: Uzun bir nitelik yolu (Visual Basic) ile bir nesneye erişimi hızlandırma</span><span class="sxs-lookup"><span data-stu-id="3f429-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>

<span data-ttu-id="3f429-103">Birçok yöntem ve özellik için bir nitelik yolu gerektiren bir nesneye sık sık erişiyorsanız, nitelik yolunu tekrarlayarak kodunuzun hızını hızlandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3f429-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>

<span data-ttu-id="3f429-104">Nitelik yolunu tekrardan kaçınmanın iki yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="3f429-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="3f429-105">Nesnesini bir değişkene atayabilir veya bir `With`... içinde kullanabilirsiniz. `End With` engelle.</span><span class="sxs-lookup"><span data-stu-id="3f429-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="3f429-106">Büyük ölçüde nitelikli bir nesneye erişimi bir değişkene atayarak hızlandırmak için</span><span class="sxs-lookup"><span data-stu-id="3f429-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>

1. <span data-ttu-id="3f429-107">Sıklıkla eriştiğiniz nesnenin türünde bir değişken bildirin.</span><span class="sxs-lookup"><span data-stu-id="3f429-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="3f429-108">Bildirimin başlatma bölümünde nitelik yolunu belirtin.</span><span class="sxs-lookup"><span data-stu-id="3f429-108">Specify the qualification path in the initialization part of the declaration.</span></span>

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="3f429-109">Nesnenin üyelerine erişmek için değişkenini kullanın.</span><span class="sxs-lookup"><span data-stu-id="3f429-109">Use the variable to access the object's members.</span></span>

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="3f429-110">Ile bir Ile kullanarak bir büyük ölçüde nitelenmiş nesneye erişimi hızlandırmak için... Blokla bitir</span><span class="sxs-lookup"><span data-stu-id="3f429-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>

1. <span data-ttu-id="3f429-111">Nitelik yolunu bir `With` deyime koyun.</span><span class="sxs-lookup"><span data-stu-id="3f429-111">Put the qualification path in a `With` statement.</span></span>

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="3f429-112">Deyimden önce nesnenin `With` blok içindeki üyelerine erişin. `End With`</span><span class="sxs-lookup"><span data-stu-id="3f429-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a><span data-ttu-id="3f429-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3f429-113">See also</span></span>

- [<span data-ttu-id="3f429-114">Nesne Değişkenleri</span><span class="sxs-lookup"><span data-stu-id="3f429-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="3f429-115">With...End With Deyimi</span><span class="sxs-lookup"><span data-stu-id="3f429-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
