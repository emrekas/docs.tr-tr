---
title: "Hiçbir erişilebilir aşırı yüklenmiş '<methodname>' bir daraltma dönüşümü olmadan bu bağımsız değişkenlerle çağrılır: <list>"
ms.date: 07/20/2015
f1_keywords:
- vbrAmbiguousCall2
ms.assetid: 13b20ffa-9f02-4971-a3cb-e08b402fd971
ms.openlocfilehash: 4ec5abcc87940434a830cb56e2e68ddb71bde99b
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58022260"
---
# <a name="no-accessible-overloaded-methodname-can-be-called-with-these-arguments-without-a-narrowing-conversion-list"></a><span data-ttu-id="536e7-102">Hiçbir erişilebilir aşırı '\<yöntemAdı >' Bu bağımsız değişken bir daraltma dönüşümü olmadan çağrılabilir: \<listesi ></span><span class="sxs-lookup"><span data-stu-id="536e7-102">No accessible overloaded '\<methodname>' can be called with these arguments without a narrowing conversion: \<list></span></span>
<span data-ttu-id="536e7-103">Aşırı yüklenmiş bir yöntemi çağrıldı, ancak yöntem bir daraltma dönüşümü olmadan sağlanan bağımsız değişken listesiyle eşleşemez.</span><span class="sxs-lookup"><span data-stu-id="536e7-103">An overloaded method was called, but the method cannot be matched with the list of provided arguments without a narrowing conversion.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="536e7-104">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="536e7-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="536e7-105">Belirtin `Option Strict Off`.</span><span class="sxs-lookup"><span data-stu-id="536e7-105">Specify `Option Strict Off`.</span></span>
  
2.  <span data-ttu-id="536e7-106">Bağımsız değişkenleri, aşırı yüklenmiş metodun imzası eşleşecek şekilde değiştirin.</span><span class="sxs-lookup"><span data-stu-id="536e7-106">Change the arguments to match a signature of the overloaded method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="536e7-107">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="536e7-107">See also</span></span>

- [<span data-ttu-id="536e7-108">Bağımsız Değişkenleri Değere ve Başvuruya Göre Geçirme</span><span class="sxs-lookup"><span data-stu-id="536e7-108">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="536e7-109">Genişletme ve Daraltma Dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="536e7-109">Widening and Narrowing Conversions</span></span>](../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
