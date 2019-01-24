---
title: WCF Tarafından Gerektirilen İşletim Sistemi Kaynakları
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 759ab099066e300484860cf3f91d6d084ba1d339
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527087"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="efed8-102">WCF Tarafından Gerektirilen İşletim Sistemi Kaynakları</span><span class="sxs-lookup"><span data-stu-id="efed8-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="efed8-103">Windows Communication Foundation (WCF), işlev işletim sistemi tarafından sağlanan çeşitli kaynaklar bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="efed8-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="efed8-104">Aşağıdaki tabloda, bu kaynakları listeler.</span><span class="sxs-lookup"><span data-stu-id="efed8-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="efed8-105">Kaynak</span><span class="sxs-lookup"><span data-stu-id="efed8-105">Resource</span></span>|<span data-ttu-id="efed8-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="efed8-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="efed8-107">Microsoft Dağıtılmış İşlem Düzenleyicisi (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="efed8-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="efed8-108">OleTx işlemleri desteklemek için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="efed8-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="efed8-109">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="efed8-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="efed8-110">IIS uygulamanızı barındırmak için kullanmak istiyorsanız gereklidir.</span><span class="sxs-lookup"><span data-stu-id="efed8-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="efed8-111">Windows İşlem Etkinleştirme Hizmeti (WAS)</span><span class="sxs-lookup"><span data-stu-id="efed8-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="efed8-112">WAS uygulamanızı barındırmak için kullanmak istiyorsanız gereklidir.</span><span class="sxs-lookup"><span data-stu-id="efed8-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efed8-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="efed8-113">See also</span></span>
- [<span data-ttu-id="efed8-114">Sistem Gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="efed8-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
