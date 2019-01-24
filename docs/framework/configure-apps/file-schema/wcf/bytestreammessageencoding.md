---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 92ae3dc10e0ae734a3113e22f175f4d010ca55b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541865"
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="dfe15-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="dfe15-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="dfe15-103">Bir karakter kodlamasını belirtmek için seçeneği ile bayt akışı olarak kodlamasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="dfe15-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="dfe15-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dfe15-104">\<system.serviceModel></span></span>  
<span data-ttu-id="dfe15-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="dfe15-105">\<bindings></span></span>  
<span data-ttu-id="dfe15-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="dfe15-106">\<customBinding></span></span>  
<span data-ttu-id="dfe15-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="dfe15-107">\<binding></span></span>  
<span data-ttu-id="dfe15-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="dfe15-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe15-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="dfe15-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfe15-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="dfe15-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dfe15-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="dfe15-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfe15-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="dfe15-112">Attributes</span></span>  
  
|<span data-ttu-id="dfe15-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="dfe15-113">Attribute</span></span>|<span data-ttu-id="dfe15-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="dfe15-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dfe15-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="dfe15-115">messageVersion</span></span>|<span data-ttu-id="dfe15-116">Bağlama kullanılarak gönderilen iletilerin SOAP sürümünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="dfe15-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="dfe15-117">Bu özellik yalnızca ileti sürümü değeri için ayarlanabilir <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfe15-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="dfe15-118">Bayt akışı ileti Kodlayıcı herhangi bir ileti sürümlerini desteklemez.</span><span class="sxs-lookup"><span data-stu-id="dfe15-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="dfe15-119">Bu öznitelik türünde <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="dfe15-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfe15-120">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="dfe15-120">Child Elements</span></span>  
  
|<span data-ttu-id="dfe15-121">Öğe</span><span class="sxs-lookup"><span data-stu-id="dfe15-121">Element</span></span>|<span data-ttu-id="dfe15-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="dfe15-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfe15-123">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="dfe15-123">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="dfe15-124">Bu bağlama ile yapılandırılan bir bitiş noktası tarafından işlenen SOAP iletilerinin karmaşıklığını kısıtlamalar tanımlar.</span><span class="sxs-lookup"><span data-stu-id="dfe15-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="dfe15-125">Bu öğe türünde <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="dfe15-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dfe15-126">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="dfe15-126">Parent Elements</span></span>  
  
|<span data-ttu-id="dfe15-127">Öğe</span><span class="sxs-lookup"><span data-stu-id="dfe15-127">Element</span></span>|<span data-ttu-id="dfe15-128">Açıklama</span><span class="sxs-lookup"><span data-stu-id="dfe15-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfe15-129">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="dfe15-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="dfe15-130">Özel bağlama tüm bağlama yeteneklerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="dfe15-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfe15-131">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="dfe15-131">See also</span></span>
- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="dfe15-132">İleti Kodlama</span><span class="sxs-lookup"><span data-stu-id="dfe15-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="dfe15-133">İleti Kodlayıcı Seçme</span><span class="sxs-lookup"><span data-stu-id="dfe15-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="dfe15-134">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="dfe15-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="dfe15-135">Bağlamaları Genişletme</span><span class="sxs-lookup"><span data-stu-id="dfe15-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="dfe15-136">Özel Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="dfe15-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="dfe15-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="dfe15-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
