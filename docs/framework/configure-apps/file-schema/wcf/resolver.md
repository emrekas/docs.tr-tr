---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 39dcb868bd3ff25451509616e1dac7d41f94cfa1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075885"
---
# <a name="resolver"></a><span data-ttu-id="01da4-101">\<Çözümleyici ></span><span class="sxs-lookup"><span data-stu-id="01da4-101">\<resolver></span></span>
<span data-ttu-id="01da4-102">Ağ içinde katılan çeşitli düğümleri temsil eden bir eş düğüm adresleri kümesi bir eş çözümlemek için kullanılan bir eş çözümleyici ağ Kimliğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="01da4-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="01da4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="01da4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="01da4-104">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="01da4-104">\<bindings></span></span>  
<span data-ttu-id="01da4-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="01da4-105">\<netPeerBinding></span></span>  
<span data-ttu-id="01da4-106">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="01da4-106">\<binding></span></span>  
<span data-ttu-id="01da4-107">\<Çözümleyici ></span><span class="sxs-lookup"><span data-stu-id="01da4-107">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01da4-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="01da4-108">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01da4-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="01da4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01da4-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="01da4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01da4-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="01da4-111">Attributes</span></span>  
  
|<span data-ttu-id="01da4-112">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="01da4-112">Attribute</span></span>|<span data-ttu-id="01da4-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01da4-113">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="01da4-114">Bu hizmetle ilişkili eş Çözücü örneğinin ya da PNRP belirli bir özel Çözücü olup olmadığını belirtir ya da otomatik olarak belirlenen bir dize.</span><span class="sxs-lookup"><span data-stu-id="01da4-114">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="01da4-115">Bu öznitelik türünde <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="01da4-115">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="01da4-116">Eşler arasında paylaşılan yol başvurularını belirleyen bir dize.</span><span class="sxs-lookup"><span data-stu-id="01da4-116">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="01da4-117">Bu öznitelik türünde <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="01da4-117">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01da4-118">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="01da4-118">Child Elements</span></span>  
  
|<span data-ttu-id="01da4-119">Öğe</span><span class="sxs-lookup"><span data-stu-id="01da4-119">Element</span></span>|<span data-ttu-id="01da4-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01da4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01da4-121">\<üstbilgiler ></span><span class="sxs-lookup"><span data-stu-id="01da4-121">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="01da4-122">Özel eş Çözücü hizmetinin ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="01da4-122">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01da4-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="01da4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="01da4-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="01da4-124">Element</span></span>|<span data-ttu-id="01da4-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="01da4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01da4-126">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="01da4-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="01da4-127">Tüm bağlama yeteneklerini tanımlar [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="01da4-127">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01da4-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="01da4-128">Remarks</span></span>  
 <span data-ttu-id="01da4-129">Bir eş ad çözümleyici eş bir eş ağ içinde katılan düğümleri bulmak için eş kanallar tarafından kullanılan bir bulma hizmetidir.</span><span class="sxs-lookup"><span data-stu-id="01da4-129">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="01da4-130">Ayrıca, "bir düğüm olarak Eş düğüm eş kafes bilinen ve kullanılabilir hale gelir mekanizması bir eş kafes kaydetmek için" kullanılır.</span><span class="sxs-lookup"><span data-stu-id="01da4-130">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="01da4-131">Eş çözücüler hakkında daha fazla bilgi için bkz. [eş çözücüler](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="01da4-131">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01da4-132">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="01da4-132">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="01da4-133">Eş Çözücüler</span><span class="sxs-lookup"><span data-stu-id="01da4-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- [<span data-ttu-id="01da4-134">Bir özel Çözücü PeerChannel'a uygulamaya ekleme</span><span class="sxs-lookup"><span data-stu-id="01da4-134">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))
