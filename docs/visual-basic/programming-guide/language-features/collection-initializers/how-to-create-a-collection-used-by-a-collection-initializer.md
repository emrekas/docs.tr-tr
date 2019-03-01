---
title: 'Nasıl yapılır: (Visual Basic) koleksiyon başlatıcısı tarafından kullanılan bir koleksiyon oluşturma'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: d0007ebf5f18dee5bd8448a071fe1f0f984aff1a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967457"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="eb4c3-102">Nasıl yapılır: (Visual Basic) koleksiyon başlatıcısı tarafından kullanılan bir koleksiyon oluşturma</span><span class="sxs-lookup"><span data-stu-id="eb4c3-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="eb4c3-103">Bir koleksiyon oluşturmak için bir koleksiyon Başlatıcısı kullandığınızda, Visual Basic Derleyicisi arar bir `Add` koleksiyon türü yöntemi için parametreleri `Add` koleksiyon Başlatıcısı değerleri türlerini match yöntemi.</span><span class="sxs-lookup"><span data-stu-id="eb4c3-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="eb4c3-104">Bu `Add` yöntemi koleksiyon Başlatıcısı değerlerle doldurmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="eb4c3-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb4c3-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="eb4c3-105">Example</span></span>  
 <span data-ttu-id="eb4c3-106">Aşağıdaki örnekte gösterildiği bir `OrderCollection` içeren bir genel koleksiyon `Add` koleksiyon Başlatıcısı türden nesneleri eklemek için kullanabileceğiniz yöntem `Order`.</span><span class="sxs-lookup"><span data-stu-id="eb4c3-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="eb4c3-107">`Add` Yöntemi kısaltılmış koleksiyon Başlatıcısı sözdizimi kullanmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="eb4c3-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="eb4c3-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="eb4c3-108">See also</span></span>
- [<span data-ttu-id="eb4c3-109">Öğe Başlatıcıları</span><span class="sxs-lookup"><span data-stu-id="eb4c3-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="eb4c3-110">Nasıl yapılır: Oluşturma bir koleksiyon başlatıcısı tarafından kullanılan uzantı ekleme metodu</span><span class="sxs-lookup"><span data-stu-id="eb4c3-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
