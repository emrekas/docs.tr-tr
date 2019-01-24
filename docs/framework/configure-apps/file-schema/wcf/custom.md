---
title: '&lt;custom&gt;'
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 5180b8866d8b0155a8683ab9cb6135c26f696929
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734993"
---
# <a name="ltcustomgt"></a><span data-ttu-id="b15b5-102">&lt;custom&gt;</span><span class="sxs-lookup"><span data-stu-id="b15b5-102">&lt;custom&gt;</span></span>
<span data-ttu-id="b15b5-103">Özel eş Çözücü hizmetinin ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="b15b5-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="b15b5-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b15b5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b15b5-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="b15b5-105">\<bindings></span></span>  
<span data-ttu-id="b15b5-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="b15b5-106">\<netPeerBinding></span></span>  
<span data-ttu-id="b15b5-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="b15b5-107">\<binding></span></span>  
<span data-ttu-id="b15b5-108">\<Çözümleyici ></span><span class="sxs-lookup"><span data-stu-id="b15b5-108">\<resolver></span></span>  
<span data-ttu-id="b15b5-109">\<Özel ></span><span class="sxs-lookup"><span data-stu-id="b15b5-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b15b5-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b15b5-110">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b15b5-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="b15b5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b15b5-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="b15b5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b15b5-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="b15b5-113">Attributes</span></span>  
  
|<span data-ttu-id="b15b5-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="b15b5-114">Attribute</span></span>|<span data-ttu-id="b15b5-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b15b5-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="b15b5-116">Özel eş çözümleyici hizmetini barındıran eş düğümün uç nokta adresini belirten bir URI.</span><span class="sxs-lookup"><span data-stu-id="b15b5-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="b15b5-117">Özel eş Çözücü hizmetinin türünü belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="b15b5-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b15b5-118">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="b15b5-118">Child Elements</span></span>  
  
|<span data-ttu-id="b15b5-119">Öğe</span><span class="sxs-lookup"><span data-stu-id="b15b5-119">Element</span></span>|<span data-ttu-id="b15b5-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b15b5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b15b5-121">\<Kimliği ></span><span class="sxs-lookup"><span data-stu-id="b15b5-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="b15b5-122">Bu öğe ile yapılandırılmış özel eş çözücüler kimliğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="b15b5-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="b15b5-123">Bu öğe türünde <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="b15b5-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="b15b5-124">\<üstbilgiler ></span><span class="sxs-lookup"><span data-stu-id="b15b5-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="b15b5-125">Özel eş çözümleyici tarafından işlenen SOAP iletileri için kullanılan adres üstbilgisi koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="b15b5-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b15b5-126">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="b15b5-126">Parent Elements</span></span>  
  
|<span data-ttu-id="b15b5-127">Öğe</span><span class="sxs-lookup"><span data-stu-id="b15b5-127">Element</span></span>|<span data-ttu-id="b15b5-128">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b15b5-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b15b5-129">\<Çözümleyici ></span><span class="sxs-lookup"><span data-stu-id="b15b5-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="b15b5-130">Bir eş çözümlemek için kullanılan bir eş çözümleyici ağ Kimliğini ağ içinde katılan çeşitli düğümleri temsil eden bir eş düğüm adresleri kümesi.</span><span class="sxs-lookup"><span data-stu-id="b15b5-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b15b5-131">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b15b5-131">Remarks</span></span>  
 <span data-ttu-id="b15b5-132">Bu öğe, hizmet ve herhangi bir özel bağlayıcı ayarları barındıran eş uç nokta adresini de dahil olmak üzere bir özel eş Çözücü hizmetinin temel ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="b15b5-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="b15b5-133">Bir özel Çözücü oluşturma hakkında daha fazla bilgi için bkz. [PeerChannel'a uygulamaya özel Çözücü ekleme](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="b15b5-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b15b5-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b15b5-134">See also</span></span>
- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="b15b5-135">Eş Çözücüler</span><span class="sxs-lookup"><span data-stu-id="b15b5-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- [<span data-ttu-id="b15b5-136">Bir özel Çözücü PeerChannel'a uygulamaya ekleme</span><span class="sxs-lookup"><span data-stu-id="b15b5-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
