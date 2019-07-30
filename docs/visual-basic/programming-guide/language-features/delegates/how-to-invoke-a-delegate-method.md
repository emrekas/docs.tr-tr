---
title: 'Nasıl yapılır: Temsilci yöntemini çağır (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c2bdb65c9d060e854db3319e4aa5b2e93b9681af
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629583"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="09b6e-102">Nasıl yapılır: Temsilci yöntemini çağır (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09b6e-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>

<span data-ttu-id="09b6e-103">Bu örnek, bir yöntemin bir temsilciyle nasıl ilişkilendirileceğini gösterir ve ardından bu yöntemi temsilci aracılığıyla çağırır.</span><span class="sxs-lookup"><span data-stu-id="09b6e-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>

### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="09b6e-104">Temsilci ve eşleştirme yordamlarını oluşturma</span><span class="sxs-lookup"><span data-stu-id="09b6e-104">Create the delegate and matching procedures</span></span>

1. <span data-ttu-id="09b6e-105">Adlı `MySubDelegate`bir temsilci oluşturun.</span><span class="sxs-lookup"><span data-stu-id="09b6e-105">Create a delegate named `MySubDelegate`.</span></span>

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. <span data-ttu-id="09b6e-106">Temsilciyle aynı imzaya sahip bir yöntem içeren bir sınıf bildirin.</span><span class="sxs-lookup"><span data-stu-id="09b6e-106">Declare a class that contains a method with the same signature as the delegate.</span></span>

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. <span data-ttu-id="09b6e-107">Temsilcinin bir örneğini oluşturan ve yerleşik `Invoke` metodu çağırarak temsilciyle ilişkili yöntemi çağıran bir yöntem tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="09b6e-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a><span data-ttu-id="09b6e-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="09b6e-108">See also</span></span>

- [<span data-ttu-id="09b6e-109">Delegate Deyimi</span><span class="sxs-lookup"><span data-stu-id="09b6e-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="09b6e-110">Temsilciler</span><span class="sxs-lookup"><span data-stu-id="09b6e-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="09b6e-111">Olaylar</span><span class="sxs-lookup"><span data-stu-id="09b6e-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="09b6e-112">Çok İş Parçacıklı Uygulamalar</span><span class="sxs-lookup"><span data-stu-id="09b6e-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
