---
title: Paylaşılan Web Barındırma için İyileştirme
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7831e383a3048523909b79ac5a4706f3c1c48371
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969318"
---
# <a name="optimization-for-shared-web-hosting"></a><span data-ttu-id="6709a-102">Paylaşılan Web Barındırma için İyileştirme</span><span class="sxs-lookup"><span data-stu-id="6709a-102">Optimization for Shared Web Hosting</span></span>
<span data-ttu-id="6709a-103">Birkaç küçük Web sitesi barındırma tarafından paylaşılan bir sunucu yöneticisiyseniz performansı iyileştirmek ve aşağıdakileri ekleyerek site kapasitesini artırmak `gcTrimCommitOnLowMemory` ayarını `runtime` .NET Aspnet.config dosyasında düğümü dizini:</span><span class="sxs-lookup"><span data-stu-id="6709a-103">If you are the administrator for a server that is shared by hosting several small Web sites, you can optimize performance and increase site capacity by adding the following `gcTrimCommitOnLowMemory` setting to the `runtime` node in the Aspnet.config file in the .NET directory:</span></span>  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  <span data-ttu-id="6709a-104">Bu ayar, yalnızca paylaşılan Web barındırma senaryolarında önerilir.</span><span class="sxs-lookup"><span data-stu-id="6709a-104">This setting is recommended only for shared Web hosting scenarios.</span></span>  
  
 <span data-ttu-id="6709a-105">Çöp toplayıcı belleği gelecekteki ayırmalar için koruyacağından, onun kaydedilmiş alan birden çok kesinlikle gerekli olabilir.</span><span class="sxs-lookup"><span data-stu-id="6709a-105">Because the garbage collector retains memory for future allocations, its committed space can be more than what is strictly needed.</span></span> <span data-ttu-id="6709a-106">Saatleri gerçekleştirmek için bu alan azaltabilir sistem belleği üzerinde ağır bir yük olduğunda.</span><span class="sxs-lookup"><span data-stu-id="6709a-106">You can reduce this space to accommodate times when there is a heavy load on system memory.</span></span> <span data-ttu-id="6709a-107">Bu taahhüt alanını azaltma, performansı geliştirir ve daha fazla siteyi barındırma kapasitesi genişletir.</span><span class="sxs-lookup"><span data-stu-id="6709a-107">Reducing this committed space improves performance and expands the capacity to host more sites.</span></span>  
  
 <span data-ttu-id="6709a-108">Zaman `gcTrimCommitOnLowMemory` ayarı etkinse, çöp toplayıcı sistem bellek yükü değerlendirir ve yük % 90'ını ulaştığında bir kesme moduna girer.</span><span class="sxs-lookup"><span data-stu-id="6709a-108">When the `gcTrimCommitOnLowMemory` setting is enabled, the garbage collector evaluates the system memory load and enters a trimming mode when the load reaches 90%.</span></span> <span data-ttu-id="6709a-109">Yük altında % 85'lik düşene kadar kesme modu tutar.</span><span class="sxs-lookup"><span data-stu-id="6709a-109">It maintains the trimming mode until the load drops under 85%.</span></span>  
  
 <span data-ttu-id="6709a-110">Koşullar izin, çöp toplayıcı, karar verebilirsiniz `gcTrimCommitOnLowMemory` ayar değil geçerli uygulamanın yardımcı olmak ve onu yok sayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6709a-110">When conditions permit, the garbage collector can decide that the `gcTrimCommitOnLowMemory` setting will not help the current application and ignore it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6709a-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="6709a-111">Example</span></span>  
 <span data-ttu-id="6709a-112">Aşağıdaki XML parçası nasıl etkinleştirileceğini göstermektedir `gcTrimCommitOnLowMemory` ayarı.</span><span class="sxs-lookup"><span data-stu-id="6709a-112">The following XML fragment shows how to enable the `gcTrimCommitOnLowMemory` setting.</span></span> <span data-ttu-id="6709a-113">Üç nokta içinde olabilecek diğer ayarları belirtmek `runtime` düğümü.</span><span class="sxs-lookup"><span data-stu-id="6709a-113">Ellipses indicate other settings that would be in the `runtime` node.</span></span>  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6709a-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6709a-114">See also</span></span>

- [<span data-ttu-id="6709a-115">Atık Toplama</span><span class="sxs-lookup"><span data-stu-id="6709a-115">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
