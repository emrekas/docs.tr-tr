---
title: Durum Verilerinin Güvenliğini Sağlama
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c821177ca897e617885425217ac0b6659b5ea6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018560"
---
# <a name="securing-state-data"></a><span data-ttu-id="8da43-102">Durum Verilerinin Güvenliğini Sağlama</span><span class="sxs-lookup"><span data-stu-id="8da43-102">Securing State Data</span></span>
<span data-ttu-id="8da43-103">Hassas verileri işleyebilir veya herhangi bir türden güvenlik kararları olun uygulamalar bu verileri kendi denetimi altında tutmanız gerekir ve diğer kötü amaçlı olabilecek kod verilere doğrudan erişmek izin veremez.</span><span class="sxs-lookup"><span data-stu-id="8da43-103">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="8da43-104">Verileri (kapsamla aynı derlemeye sınırlı) özel veya iç olarak bildirmek için bellekteki verileri korumak için en iyi yolu olan değişkenler.</span><span class="sxs-lookup"><span data-stu-id="8da43-104">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="8da43-105">Ancak, bile bu veri bilincinde olmanız gereken erişim vardır:</span><span class="sxs-lookup"><span data-stu-id="8da43-105">However, even this data is subject to access you should be aware of:</span></span>  
  
- <span data-ttu-id="8da43-106">Nesnenizin başvurabilirsiniz yüksek derecede güvenilen kod, yansıma mekanizmalarını kullanarak, alma ve özel üyeler ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="8da43-106">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
- <span data-ttu-id="8da43-107">Serileştirme kullanarak yüksek derecede güvenilen kod etkili bir şekilde almak ve nesnesinin seri hala getirilmiş biçimini karşılık gelen verileri erişebiliyorsa özel üyeler ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="8da43-107">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
- <span data-ttu-id="8da43-108">Hata ayıklama altında bu verileri okunabilir.</span><span class="sxs-lookup"><span data-stu-id="8da43-108">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="8da43-109">Kendi yöntemlerin hiçbiri emin olun veya özellikleri bu değerleri istemeden gösterir.</span><span class="sxs-lookup"><span data-stu-id="8da43-109">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8da43-110">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8da43-110">See also</span></span>

- [<span data-ttu-id="8da43-111">Güvenli Kodlama Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="8da43-111">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
