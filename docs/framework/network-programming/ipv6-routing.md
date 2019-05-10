---
title: IPv6 Yönlendirme
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
ms.openlocfilehash: caa1f33f46d13440eab18ba321ebcd8fa4eef129
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647269"
---
# <a name="ipv6-routing"></a><span data-ttu-id="d8efc-102">IPv6 Yönlendirme</span><span class="sxs-lookup"><span data-stu-id="d8efc-102">IPv6 Routing</span></span>
<span data-ttu-id="d8efc-103">Yönlendirme için esnek bir mekanizma, IPv6'ın bir avantajdır.</span><span class="sxs-lookup"><span data-stu-id="d8efc-103">A flexible routing mechanism is a benefit of IPv6.</span></span> <span data-ttu-id="d8efc-104">IPv4 ağ kimlikleri olan ve ayrılan, büyük yönlendirme tabloları yöntemi nedeniyle üzerinde Internet omurgalarından yönlendirici tarafından saklanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d8efc-104">Due to the way in which IPv4 network IDs were and are allocated, large routing tables need to be maintained by the routers that are on the Internet backbones.</span></span> <span data-ttu-id="d8efc-105">Bu yönlendiriciler, potansiyel olarak Internet'te herhangi bir düğüme yönlendirilir paketlerini iletmek için tüm yolları bilmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="d8efc-105">These routers must know all the routes in order to forward packets that are potentially directed to any node on the Internet.</span></span> <span data-ttu-id="d8efc-106">Güncelleyebileceği toplama adreslerine IPv6 esnek adresleme sağlar ve yönlendirme tablolarını boyutunu önemli ölçüde azaltır.</span><span class="sxs-lookup"><span data-stu-id="d8efc-106">With its ability to aggregate addresses, IPv6 allows flexible addressing and drastically reduces the size of routing tables.</span></span> <span data-ttu-id="d8efc-107">Bu yeni adresleme mimaride Ara yönlendiriciler, iletilerin uygun şekilde iletmek için yalnızca yerel bölümü, ağ izlemeyi tutmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="d8efc-107">In this new addressing architecture, intermediate routers must keep track only of the local portion of their network in order to forward the messages appropriately.</span></span>  
  
## <a name="neighbor-discovery"></a><span data-ttu-id="d8efc-108">Komşu bulma</span><span class="sxs-lookup"><span data-stu-id="d8efc-108">Neighbor Discovery</span></span>  
 <span data-ttu-id="d8efc-109">Komşu Bulma tarafından sağlanan özelliklerden bazıları şunlardır:</span><span class="sxs-lookup"><span data-stu-id="d8efc-109">Some of the features provided by Neighbor Discovery are:</span></span>  
  
- <span data-ttu-id="d8efc-110">Yönlendirici bulma.</span><span class="sxs-lookup"><span data-stu-id="d8efc-110">Router discovery.</span></span> <span data-ttu-id="d8efc-111">Bu, yerel yönlendirici belirlemek için ana bilgisayarları sağlar.</span><span class="sxs-lookup"><span data-stu-id="d8efc-111">This allows hosts to identify local routers.</span></span>  
  
- <span data-ttu-id="d8efc-112">Çözüm adresi.</span><span class="sxs-lookup"><span data-stu-id="d8efc-112">Address resolution.</span></span> <span data-ttu-id="d8efc-113">Bu, karşılık gelen bir sonraki atlama adresi (Adres Çözümleme Protokolü'nü [ARP] yerine) için bir bağlantı-katman adresi çözümlemek düğümleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="d8efc-113">This allows nodes to resolve a link-layer address for a corresponding next-hop address (a replacement for Address Resolution Protocol [ARP]).</span></span>  
  
- <span data-ttu-id="d8efc-114">Otomatik yapılandırma adres.</span><span class="sxs-lookup"><span data-stu-id="d8efc-114">Address auto-configuration.</span></span> <span data-ttu-id="d8efc-115">Bu konakların otomatik olarak site-yerel ve genel adresleri yapılandırma sağlar.</span><span class="sxs-lookup"><span data-stu-id="d8efc-115">This allows hosts to automatically configure site-local and global addresses.</span></span>  
  
 <span data-ttu-id="d8efc-116">Komşu Bulma IPv6 için Internet Denetim İletisi Protokolü kullanan içerir (Icmpv6) iletileri:</span><span class="sxs-lookup"><span data-stu-id="d8efc-116">Neighbor Discovery uses Internet Control Message Protocol for IPv6 (ICMPv6) messages that include:</span></span>  
  
- <span data-ttu-id="d8efc-117">Yönlendirici Tanıtımı.</span><span class="sxs-lookup"><span data-stu-id="d8efc-117">Router advertisement.</span></span> <span data-ttu-id="d8efc-118">Yönlendirici sözde düzenli aralıklarla veya bir yönlendirici bağlantısı yanıt olarak gönderilir.</span><span class="sxs-lookup"><span data-stu-id="d8efc-118">Sent by a router on a pseudo-periodic basis or in response to a router solicitation.</span></span> <span data-ttu-id="d8efc-119">IPv6 Yönlendirici yönlendirici reklam kullanılabilirliklerini, adres ön ekleri ve diğer parametreleri bildirmek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="d8efc-119">IPv6 routers use router advertisements to advertise their availability, address prefixes, and other parameters.</span></span>  
  
- <span data-ttu-id="d8efc-120">Yönlendirici Bağlantısı.</span><span class="sxs-lookup"><span data-stu-id="d8efc-120">Router solicitation.</span></span> <span data-ttu-id="d8efc-121">Yönlendiriciler bağlantıya bir yönlendirici hemen göndermek için bir ana bilgisayar tarafından gönderilir.</span><span class="sxs-lookup"><span data-stu-id="d8efc-121">Sent by a host to request that routers on the link send a router advertisement immediately.</span></span>  
  
- <span data-ttu-id="d8efc-122">Komşu bağlantısı.</span><span class="sxs-lookup"><span data-stu-id="d8efc-122">Neighbor solicitation.</span></span> <span data-ttu-id="d8efc-123">Adres çözümlemesi için düğümleri tarafından gönderilen, yinelenen adres algılama veya bir komşu hala erişilebilir olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="d8efc-123">Sent by nodes for address resolution, duplicate address detection, or to verify that a neighbor is still reachable.</span></span>  
  
- <span data-ttu-id="d8efc-124">Komşu Tanıtımı.</span><span class="sxs-lookup"><span data-stu-id="d8efc-124">Neighbor advertisement.</span></span> <span data-ttu-id="d8efc-125">Düğümler tarafından gönderilen bir komşu bağlantısı için yanıt veya Komşuları bağlantı-katman adresi değişikliği bildirir.</span><span class="sxs-lookup"><span data-stu-id="d8efc-125">Sent by nodes to respond to a neighbor solicitation or to notify neighbors of a change in link-layer address.</span></span>  
  
- <span data-ttu-id="d8efc-126">Yeniden yönlendirme.</span><span class="sxs-lookup"><span data-stu-id="d8efc-126">Redirect.</span></span> <span data-ttu-id="d8efc-127">Belirli bir hedefe gönderen düğüm için daha iyi bir sonraki atlama adresini göstermek için yönlendiricileri tarafından gönderilir.</span><span class="sxs-lookup"><span data-stu-id="d8efc-127">Sent by routers to indicate a better next-hop address to a particular destination for a sending node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8efc-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d8efc-128">See also</span></span>

- [<span data-ttu-id="d8efc-129">İnternet Protokolü Sürüm 6</span><span class="sxs-lookup"><span data-stu-id="d8efc-129">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)
- [<span data-ttu-id="d8efc-130">Yuvalar</span><span class="sxs-lookup"><span data-stu-id="d8efc-130">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
