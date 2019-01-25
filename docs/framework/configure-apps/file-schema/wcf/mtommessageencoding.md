---
title: '&lt;mtomMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: b9fe4a9eb0176c97920c0dde5cb003c8ca1ae989
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697445"
---
# <a name="ltmtommessageencodinggt"></a><span data-ttu-id="1dae3-102">&lt;mtomMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="1dae3-102">&lt;mtomMessageEncoding&gt;</span></span>
<span data-ttu-id="1dae3-103">SOAP ileti aktarım en iyi duruma getirme mekanizması (temel MTOM) iletiler için kullanılan kodlama ve ileti sürüm oluşturmayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="1dae3-103">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="1dae3-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1dae3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1dae3-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="1dae3-105">\<bindings></span></span>  
<span data-ttu-id="1dae3-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1dae3-106">\<customBinding></span></span>  
<span data-ttu-id="1dae3-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="1dae3-107">\<binding></span></span>  
<span data-ttu-id="1dae3-108">\<mtomMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="1dae3-108">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dae3-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="1dae3-109">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dae3-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="1dae3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1dae3-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="1dae3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dae3-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="1dae3-112">Attributes</span></span>  
  
|<span data-ttu-id="1dae3-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="1dae3-113">Attribute</span></span>|<span data-ttu-id="1dae3-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="1dae3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1dae3-115">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="1dae3-115">maxBufferSize</span></span>|<span data-ttu-id="1dae3-116">Kullanılabilir arabelleğinin en büyük boyutunu belirten bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="1dae3-116">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="1dae3-117">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="1dae3-117">maxReadPoolSize</span></span>|<span data-ttu-id="1dae3-118">İleti sayısını belirten bir tamsayı yeni okuyucu ayırmadan aynı anda okuyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1dae3-118">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="1dae3-119">Daha büyük havuz boyutları sistemi daha büyük bir çalışma kümesi, etkinlik artışlarını daha dayanıklı hale getirmek.</span><span class="sxs-lookup"><span data-stu-id="1dae3-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1dae3-120">64 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="1dae3-120">The default is 64.</span></span>|  
|<span data-ttu-id="1dae3-121">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="1dae3-121">maxWritePoolSize</span></span>|<span data-ttu-id="1dae3-122">İleti sayısını belirten bir tamsayı, yeni yazıcı ayırmadan aynı anda gönderilebilecek.</span><span class="sxs-lookup"><span data-stu-id="1dae3-122">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="1dae3-123">Daha büyük havuz boyutları sistemi daha büyük bir çalışma kümesi, etkinlik artışlarını daha dayanıklı hale getirmek.</span><span class="sxs-lookup"><span data-stu-id="1dae3-123">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1dae3-124">Varsayılan değer 16'dır.</span><span class="sxs-lookup"><span data-stu-id="1dae3-124">The default is 16.</span></span>|  
|<span data-ttu-id="1dae3-125">messageVersion</span><span class="sxs-lookup"><span data-stu-id="1dae3-125">messageVersion</span></span>|<span data-ttu-id="1dae3-126">Bağlama kullanılarak gönderilen iletilerin SOAP sürümünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="1dae3-126">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="1dae3-127">Geçerli değerler:</span><span class="sxs-lookup"><span data-stu-id="1dae3-127">Valid values are</span></span><br /><br /> <span data-ttu-id="1dae3-128">-Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="1dae3-128">-   Soap11Addressing1</span></span><br /><span data-ttu-id="1dae3-129">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="1dae3-129">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="1dae3-130">Soap12Addressing10 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="1dae3-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="1dae3-131">Bu öznitelik türünde <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="1dae3-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="1dae3-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="1dae3-132">writeEncoding</span></span>|<span data-ttu-id="1dae3-133">Bağlamadaki yayma iletileri için kullanılacak kodlama karakter kümesini belirtir.</span><span class="sxs-lookup"><span data-stu-id="1dae3-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="1dae3-134">Geçerli değerler:</span><span class="sxs-lookup"><span data-stu-id="1dae3-134">Valid values are</span></span><br /><br /> <span data-ttu-id="1dae3-135">-   UnicodeFffeTextEncoding: Unicode kodlama BigEndian</span><span class="sxs-lookup"><span data-stu-id="1dae3-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="1dae3-136">-   Utf16TextEncoding: Unicode kodlama</span><span class="sxs-lookup"><span data-stu-id="1dae3-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="1dae3-137">-   Utf8TextEncoding: 8-bit kodlama</span><span class="sxs-lookup"><span data-stu-id="1dae3-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="1dae3-138">Utf8TextEncoding varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="1dae3-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="1dae3-139">Bu öznitelik türünde <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="1dae3-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dae3-140">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="1dae3-140">Child Elements</span></span>  
  
|<span data-ttu-id="1dae3-141">Öğe</span><span class="sxs-lookup"><span data-stu-id="1dae3-141">Element</span></span>|<span data-ttu-id="1dae3-142">Açıklama</span><span class="sxs-lookup"><span data-stu-id="1dae3-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dae3-143">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="1dae3-143">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="1dae3-144">Bu bağlama ile yapılandırılan bir bitiş noktası tarafından işlenen SOAP iletilerinin karmaşıklığını kısıtlamalar tanımlar.</span><span class="sxs-lookup"><span data-stu-id="1dae3-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="1dae3-145">Bu öğe türünde <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="1dae3-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1dae3-146">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="1dae3-146">Parent Elements</span></span>  
  
|<span data-ttu-id="1dae3-147">Öğe</span><span class="sxs-lookup"><span data-stu-id="1dae3-147">Element</span></span>|<span data-ttu-id="1dae3-148">Açıklama</span><span class="sxs-lookup"><span data-stu-id="1dae3-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dae3-149">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="1dae3-149">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="1dae3-150">Özel bağlama tüm bağlama yeteneklerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="1dae3-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dae3-151">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1dae3-151">Remarks</span></span>  
 <span data-ttu-id="1dae3-152">Kodlama bir ileti bir dizi bayta dönüştürme işlemidir.</span><span class="sxs-lookup"><span data-stu-id="1dae3-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="1dae3-153">Kod çözme ters işlemidir.</span><span class="sxs-lookup"><span data-stu-id="1dae3-153">Decoding is the reverse process.</span></span> <span data-ttu-id="1dae3-154">Windows Communication Foundation (WCF) için SOAP iletilerini kodlama üç türlerini içerir: Metin, ikili ve ileti aktarım en iyi duruma getirme mekanizması (MTOM).</span><span class="sxs-lookup"><span data-stu-id="1dae3-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="1dae3-155">`MtomMessageEncoding` Öğesi, karakter kodlamasını ve ileti sürüm oluşturmayı ve bir ileti aktarım en iyi duruma getirme mekanizması (MTOM) kodlaması kullanarak iletiler için kullanılan diğer ayarları belirtir.</span><span class="sxs-lookup"><span data-stu-id="1dae3-155">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="1dae3-156">MTOM WCF iletilerinde ikili veri aktarımı için verimli bir teknolojidir.</span><span class="sxs-lookup"><span data-stu-id="1dae3-156">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="1dae3-157">MTOM Kodlayıcısı verimliliği ve birlikte çalışabilirlik arasında bir denge oluşturmaya çalışır.</span><span class="sxs-lookup"><span data-stu-id="1dae3-157">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="1dae3-158">MTOM kodlama çoğu XML metin biçiminde aktarır, ancak büyük ikili veri blokları olarak ileterek iyileştirir-base64 kodlu biçimlerini dönüştürme olmadan olduğu.</span><span class="sxs-lookup"><span data-stu-id="1dae3-158">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dae3-159">Örnek</span><span class="sxs-lookup"><span data-stu-id="1dae3-159">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="1dae3-160">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1dae3-160">See also</span></span>
- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="1dae3-161">İleti Kodlama</span><span class="sxs-lookup"><span data-stu-id="1dae3-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="1dae3-162">İleti Kodlayıcı Seçme</span><span class="sxs-lookup"><span data-stu-id="1dae3-162">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="1dae3-163">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="1dae3-163">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="1dae3-164">Bağlamaları Genişletme</span><span class="sxs-lookup"><span data-stu-id="1dae3-164">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1dae3-165">Özel Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="1dae3-165">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="1dae3-166">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1dae3-166">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
