---
title: <transport> / <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 9b6f548515afbba5068659bd5c6f7f2b33f80cda
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076009"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="b843d-102">\<Aktarım >, \<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="b843d-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="b843d-103">Bu bağlama ile yapılandırılan eşleri tarafından gönderilen güvenli iletiler için aktarım türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="b843d-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="b843d-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b843d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b843d-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="b843d-105">\<bindings></span></span>  
<span data-ttu-id="b843d-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b843d-106">\<customBinding></span></span>  
<span data-ttu-id="b843d-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="b843d-107">\<binding></span></span>  
<span data-ttu-id="b843d-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="b843d-108">\<peerTransport></span></span>  
<span data-ttu-id="b843d-109">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="b843d-109">\<security></span></span>  
<span data-ttu-id="b843d-110">\<taşıma ></span><span class="sxs-lookup"><span data-stu-id="b843d-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b843d-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b843d-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b843d-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="b843d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b843d-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="b843d-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b843d-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="b843d-114">Attributes</span></span>  
  
|<span data-ttu-id="b843d-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="b843d-115">Attribute</span></span>|<span data-ttu-id="b843d-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b843d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b843d-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="b843d-117">credentialType</span></span>|<span data-ttu-id="b843d-118">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="b843d-118">Optional.</span></span> <span data-ttu-id="b843d-119">Eş ile gönderilen iletileri doğrulamak için kullanılan kimlik bilgileri türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="b843d-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="b843d-120">Bu öznitelik türünde <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="b843d-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="b843d-121">credentialType özniteliği</span><span class="sxs-lookup"><span data-stu-id="b843d-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="b843d-122">Değer</span><span class="sxs-lookup"><span data-stu-id="b843d-122">Value</span></span>|<span data-ttu-id="b843d-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b843d-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b843d-124">Sertifika</span><span class="sxs-lookup"><span data-stu-id="b843d-124">Certificate</span></span>|<span data-ttu-id="b843d-125">Eş kanal kimlik doğrulaması gerektiren x X509 sertifika.</span><span class="sxs-lookup"><span data-stu-id="b843d-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="b843d-126">Parola</span><span class="sxs-lookup"><span data-stu-id="b843d-126">Password</span></span>|<span data-ttu-id="b843d-127">Eş kanal kimlik doğrulaması için doğru parola gereklidir.</span><span class="sxs-lookup"><span data-stu-id="b843d-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b843d-128">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="b843d-128">Child Elements</span></span>  
 <span data-ttu-id="b843d-129">Yok.</span><span class="sxs-lookup"><span data-stu-id="b843d-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b843d-130">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="b843d-130">Parent Elements</span></span>  
  
|<span data-ttu-id="b843d-131">Öğe</span><span class="sxs-lookup"><span data-stu-id="b843d-131">Element</span></span>|<span data-ttu-id="b843d-132">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b843d-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b843d-133">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="b843d-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="b843d-134">Bir eş için güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="b843d-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b843d-135">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b843d-135">Remarks</span></span>  
 <span data-ttu-id="b843d-136">Bu öğe yalnızca ayarlama modu öznitelik [ \<Güvenlik >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) ayarlanır `Transport` veya `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="b843d-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b843d-137">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b843d-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b843d-138">Aktarım Güvenliği</span><span class="sxs-lookup"><span data-stu-id="b843d-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="b843d-139">Taşımalar</span><span class="sxs-lookup"><span data-stu-id="b843d-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="b843d-140">Taşıma Seçme</span><span class="sxs-lookup"><span data-stu-id="b843d-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="b843d-141">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="b843d-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b843d-142">Bağlamaları Genişletme</span><span class="sxs-lookup"><span data-stu-id="b843d-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b843d-143">Özel Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="b843d-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b843d-144">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b843d-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
