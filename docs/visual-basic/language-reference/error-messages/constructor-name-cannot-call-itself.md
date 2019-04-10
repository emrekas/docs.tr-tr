---
title: Yapıcı '<name>' kendisini çağıramaz
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 8459ee7fec6d761161a721c88ccdc88e513fc95f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324389"
---
# <a name="constructor-name-cannot-call-itself"></a><span data-ttu-id="abcb7-102">Yapıcı '\<adı >' kendisini çağıramaz</span><span class="sxs-lookup"><span data-stu-id="abcb7-102">Constructor '\<name>' cannot call itself</span></span>
<span data-ttu-id="abcb7-103">A `Sub New` bir sınıf veya yapı yordamda kendisini çağırır.</span><span class="sxs-lookup"><span data-stu-id="abcb7-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="abcb7-104">Bir sınıfın bir örneği başlatmak için bir oluşturucu amacı olan veya ilk çalıştırıldığında yapısı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="abcb7-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="abcb7-105">Sağlanan tüm farklı parametre listeleri sahip bir sınıf veya yapı birçok oluşturucuya sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="abcb7-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="abcb7-106">Bir oluşturucu kendi ek işlevselliği gerçekleştirmek için başka bir oluşturucuyu çağırmak için izin verilir.</span><span class="sxs-lookup"><span data-stu-id="abcb7-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="abcb7-107">Ancak bir oluşturucu kendi çağrılacak anlamsız olduğu ve hatta, sonsuz özyineleme durumuna yol izin veriyorsa, neden olur.</span><span class="sxs-lookup"><span data-stu-id="abcb7-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="abcb7-108">**Hata Kimliği:** BC30298</span><span class="sxs-lookup"><span data-stu-id="abcb7-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="abcb7-109">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="abcb7-109">To correct this error</span></span>  
  
1. <span data-ttu-id="abcb7-110">Çağrılan Oluşturucusu parametre listesini kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="abcb7-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="abcb7-111">Bu, çağrıyı yapan Oluşturucusu farklı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="abcb7-111">It should be different from that of the constructor making the call.</span></span>  
  
2. <span data-ttu-id="abcb7-112">Farklı bir oluşturucuyu çağırmak düşünmüyorsanız kaldırmak `Sub New` tamamen çağırın.</span><span class="sxs-lookup"><span data-stu-id="abcb7-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abcb7-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="abcb7-113">See also</span></span>

- [<span data-ttu-id="abcb7-114">Nesne Ömrü: Nesneleri Oluşturma ve Yok Etme</span><span class="sxs-lookup"><span data-stu-id="abcb7-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
