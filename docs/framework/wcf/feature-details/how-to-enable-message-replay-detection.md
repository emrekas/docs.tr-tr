---
title: 'Nasıl yapılır: İleti Yeniden Yürütme Algılamayı Etkinleştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF security
- replay detection [WCF]
- WCF, custom bindings
- WCF, security
ms.assetid: 8b847e91-69a3-49e1-9e5f-0c455e50d804
ms.openlocfilehash: a7bdfc244b0ff1c2ed625235df7e74ced026c542
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343616"
---
# <a name="how-to-enable-message-replay-detection"></a><span data-ttu-id="1866d-102">Nasıl yapılır: İleti Yeniden Yürütme Algılamayı Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="1866d-102">How to: Enable Message Replay Detection</span></span>
<span data-ttu-id="1866d-103">Yeniden yürütme saldırı bir saldırganın iki taraflar arasında iletileri akışını kopyalar ve bir veya daha fazla taraflar akışa başlayarak yeniden oynatılır oluşur.</span><span class="sxs-lookup"><span data-stu-id="1866d-103">A replay attack occurs when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties.</span></span> <span data-ttu-id="1866d-104">Azaltılabilir sürece, saldırı bilgisayarların stream yasal iletileri, sonuçta hatalı sonuçları, bir öğenin yedekli siparişler gibi bir dizi olarak işler.</span><span class="sxs-lookup"><span data-stu-id="1866d-104">Unless mitigated, the computers subject to the attack will process the stream as legitimate messages, resulting in a range of bad consequences, such as redundant orders of an item.</span></span>  
  
 <span data-ttu-id="1866d-105">İleti yeniden yürütme algılamayı hakkında daha fazla bilgi için bkz: [ileti yeniden yürütme algılamayı](https://go.microsoft.com/fwlink/?LinkId=88536).</span><span class="sxs-lookup"><span data-stu-id="1866d-105">For more information about message replay detection, see [Message Replay Detection](https://go.microsoft.com/fwlink/?LinkId=88536).</span></span>  
  
 <span data-ttu-id="1866d-106">Aşağıdaki yordam Windows Communication Foundation (WCF) kullanarak yeniden yürütme algılaması denetlemek için kullanabileceğiniz çeşitli özelliklerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="1866d-106">The following procedure demonstrates various properties that you can use to control replay detection using Windows Communication Foundation (WCF).</span></span>  
  
### <a name="to-control-replay-detection-on-the-client-using-code"></a><span data-ttu-id="1866d-107">Kod kullanılarak istemcide yeniden yürütme algılaması denetlemek için</span><span class="sxs-lookup"><span data-stu-id="1866d-107">To control replay detection on the client using code</span></span>  
  
1. <span data-ttu-id="1866d-108">Oluşturma bir <xref:System.ServiceModel.Channels.SecurityBindingElement> kullanmak için bir <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="1866d-108">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> to use in a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span> <span data-ttu-id="1866d-109">Daha fazla bilgi için [nasıl yapılır: SecurityBindingElement kullanarak özel bağlama oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="1866d-109">For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span> <span data-ttu-id="1866d-110">Aşağıdaki örnekte bir <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> ile oluşturulan <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> , <xref:System.ServiceModel.Channels.SecurityBindingElement> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="1866d-110">The following example uses a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> created with the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span>  
  
2. <span data-ttu-id="1866d-111">Kullanım <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> bir başvuru döndürmek için özellik <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> sınıfı ve aşağıdaki özellikleri uygun şekilde ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="1866d-111">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> property to return a reference to the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class and set any of the following properties, as appropriate:</span></span>  
  
    1.  `DetectReplay`<span data-ttu-id="1866d-112">biçimindeki telefon numarasıdır.</span><span class="sxs-lookup"><span data-stu-id="1866d-112">.</span></span> <span data-ttu-id="1866d-113">Bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="1866d-113">A Boolean value.</span></span> <span data-ttu-id="1866d-114">Bu, istemcinin sunucudan olumsuzlukları algılanmalıdır olmadığını yönetir.</span><span class="sxs-lookup"><span data-stu-id="1866d-114">This governs whether the client should detect replays from the server.</span></span> <span data-ttu-id="1866d-115">Varsayılan, `true` değeridir.</span><span class="sxs-lookup"><span data-stu-id="1866d-115">The default is `true`.</span></span>  
  
    2.  `MaxClockSkew`<span data-ttu-id="1866d-116">biçimindeki telefon numarasıdır.</span><span class="sxs-lookup"><span data-stu-id="1866d-116">.</span></span> <span data-ttu-id="1866d-117">A <xref:System.TimeSpan> değeri.</span><span class="sxs-lookup"><span data-stu-id="1866d-117">A <xref:System.TimeSpan> value.</span></span> <span data-ttu-id="1866d-118">Yeniden yürütme mekanizması istemci ve sunucu arasında tolere edebilen ne kadar zaman eğimi yönetir.</span><span class="sxs-lookup"><span data-stu-id="1866d-118">Governs how much time skew the replay mechanism can tolerate between the client and the server.</span></span> <span data-ttu-id="1866d-119">Güvenlik mekanizması, zaman damgası gönderilen ve bu çok kadar geri geçmişte gönderilip gönderilmediğini belirler inceler.</span><span class="sxs-lookup"><span data-stu-id="1866d-119">The security mechanism examines the time stamp sent and determines whether it was sent too far back in the past.</span></span> <span data-ttu-id="1866d-120">Varsayılan değer 5 dakikadır.</span><span class="sxs-lookup"><span data-stu-id="1866d-120">The default is 5 minutes.</span></span>  
  
    3.  `ReplayWindow`<span data-ttu-id="1866d-121">biçimindeki telefon numarasıdır.</span><span class="sxs-lookup"><span data-stu-id="1866d-121">.</span></span> <span data-ttu-id="1866d-122">A `TimeSpan` değeri.</span><span class="sxs-lookup"><span data-stu-id="1866d-122">A `TimeSpan` value.</span></span> <span data-ttu-id="1866d-123">Bu ne kadar iletiye yöneten sunucu (aracılar) üzerinden istemci ulaşmadan önce gönderdikten sonra ağdaki Canlı çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1866d-123">This governs how long a message can live in the network after the server sends it (through intermediaries) before reaching the client.</span></span> <span data-ttu-id="1866d-124">En son gönderilen iletilerin imzalarını istemci izler `ReplayWindow` yeniden yürütme algılaması amaçları için.</span><span class="sxs-lookup"><span data-stu-id="1866d-124">The client tracks the signatures of the messages sent within the latest `ReplayWindow` for the purposes of replay detection.</span></span>  
  
    4.  `ReplayCacheSize`<span data-ttu-id="1866d-125">biçimindeki telefon numarasıdır.</span><span class="sxs-lookup"><span data-stu-id="1866d-125">.</span></span> <span data-ttu-id="1866d-126">Bir tamsayı değeri.</span><span class="sxs-lookup"><span data-stu-id="1866d-126">An integer value.</span></span> <span data-ttu-id="1866d-127">İstemci, iletinin imzalarını bir önbellekte depolar.</span><span class="sxs-lookup"><span data-stu-id="1866d-127">The client stores the signatures of the message in a cache.</span></span> <span data-ttu-id="1866d-128">Bu ayar önbellekte saklayabilirsiniz kaç imzaları belirtir.</span><span class="sxs-lookup"><span data-stu-id="1866d-128">This setting specifies how many signatures the cache can store.</span></span> <span data-ttu-id="1866d-129">Son yeniden yürütme penceresine gönderilen ileti sayısını önbellek sınırı ulaşırsa, en eski önbelleğe alınmış imzaları süre ulaşana kadar yeni iletileri reddedilir.</span><span class="sxs-lookup"><span data-stu-id="1866d-129">If the number of messages sent within the last replay window reaches the cache limit, new messages are rejected until the oldest cached signatures reach the time limit.</span></span> <span data-ttu-id="1866d-130">500000 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="1866d-130">The default is 500000.</span></span>  
  
### <a name="to-control-replay-detection-on-the-service-using-code"></a><span data-ttu-id="1866d-131">Kod kullanarak hizmet yeniden yürütme algılamayı denetlemek için</span><span class="sxs-lookup"><span data-stu-id="1866d-131">To control replay detection on the service using code</span></span>  
  
1. <span data-ttu-id="1866d-132">Oluşturma bir <xref:System.ServiceModel.Channels.SecurityBindingElement> kullanmak için bir <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="1866d-132">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> to use in a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
2. <span data-ttu-id="1866d-133">Kullanım <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> bir başvuru döndürmek için özellik <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> sınıfı ve daha önce açıklandığı gibi özellikleri ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="1866d-133">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> property to return a reference to the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class, and set the properties as described previously.</span></span>  
  
### <a name="to-control-replay-detection-in-configuration-for-the-client-or-service"></a><span data-ttu-id="1866d-134">Yeniden yürütme algılaması istemci veya hizmet yapılandırmasında denetlemek için</span><span class="sxs-lookup"><span data-stu-id="1866d-134">To control replay detection in configuration for the client or service</span></span>  
  
1. <span data-ttu-id="1866d-135">Oluşturma bir [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="1866d-135">Create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
2. <span data-ttu-id="1866d-136">Oluşturma bir `<security>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="1866d-136">Create a `<security>` element.</span></span>  
  
3. <span data-ttu-id="1866d-137">Oluşturma bir [ \<localClientSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md) veya [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="1866d-137">Create a [\<localClientSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md) or [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md).</span></span>  
  
4. <span data-ttu-id="1866d-138">Aşağıdaki öznitelik değerlerini uygun şekilde ayarlayın: `detectReplays`, `maxClockSkew`, `replayWindow`, ve `replayCacheSize`.</span><span class="sxs-lookup"><span data-stu-id="1866d-138">Set the following attribute values, as appropriate: `detectReplays`, `maxClockSkew`, `replayWindow`, and `replayCacheSize`.</span></span> <span data-ttu-id="1866d-139">Aşağıdaki örnek, her iki öznitelikleri ayarlar bir `<localServiceSettings>` ve `<localClientSettings>` öğesi:</span><span class="sxs-lookup"><span data-stu-id="1866d-139">The following example sets the attributes of both a `<localServiceSettings>` and a `<localClientSettings>` element:</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="NewBinding0">  
       <textMessageEncoding />  
        <security>  
         <localClientSettings   
          replayCacheSize="800000"   
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
         <localServiceSettings   
          replayCacheSize="800000"   
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
        <secureConversationBootstrap />  
       </security>  
      <httpTransport />  
     </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="1866d-140">Örnek</span><span class="sxs-lookup"><span data-stu-id="1866d-140">Example</span></span>  
 <span data-ttu-id="1866d-141">Aşağıdaki örnek, oluşturur bir <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> kullanarak <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> yöntemi ve bağlama yeniden yürütme özelliklerini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="1866d-141">The following example creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> using the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> method, and sets the replay properties of the binding.</span></span>  
  
 [!code-csharp[c_ReplayDetection#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_replaydetection/cs/source.cs#1)]
 [!code-vb[c_ReplayDetection#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_replaydetection/vb/source.vb#1)]  
  
## <a name="scope-of-replay-message-security-only"></a><span data-ttu-id="1866d-142">Yeniden yürütme kapsamı: İleti güvenliği</span><span class="sxs-lookup"><span data-stu-id="1866d-142">Scope of Replay: Message Security Only</span></span>  
 <span data-ttu-id="1866d-143">Aşağıdaki yordamlar, yalnızca ileti güvenlik modu için geçerli olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="1866d-143">Note that the following procedures apply only to Message security mode.</span></span> <span data-ttu-id="1866d-144">Taşıma ve ileti kimlik bilgileri modları ile aktarma için taşıma mekanizmaları olumsuzlukları algılayın.</span><span class="sxs-lookup"><span data-stu-id="1866d-144">For Transport and Transport with Message Credential modes, the transport mechanisms detect replays.</span></span>  
  
## <a name="secure-conversation-notes"></a><span data-ttu-id="1866d-145">Güvenli konuşma notları</span><span class="sxs-lookup"><span data-stu-id="1866d-145">Secure Conversation Notes</span></span>  
 <span data-ttu-id="1866d-146">Güvenli konuşma etkinleştirmek için bağlamaları, hem uygulama kanalı yanı sıra güvenli konuşma başlatma bağlaması için bu ayarları ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1866d-146">For bindings that enable secure conversations, you can adjust these settings both for the application channel as well as for the secure conversation bootstrap binding.</span></span> <span data-ttu-id="1866d-147">Örneğin, uygulama kanalı olumsuzlukları kapatma ancak kuran güvenli konuşma önyükleme kanalı odaklanmalarını.</span><span class="sxs-lookup"><span data-stu-id="1866d-147">For example, you can turn off replays for the application channel but enable them for the bootstrap channel that establishes the secure conversation.</span></span>  
  
 <span data-ttu-id="1866d-148">Güvenli konuşma oturumları kullanıyorsanız değil, yeniden yürütme algılaması olumsuzlukları sunucu grubu senaryolarını ve ne zaman işlem geri dönüştürülmeden algılama garanti etmez.</span><span class="sxs-lookup"><span data-stu-id="1866d-148">If you do not use secure conversation sessions, replay detection does not guarantee detecting replays in server farm scenarios and when the process is recycled.</span></span> <span data-ttu-id="1866d-149">Bu, aşağıdaki sistem tarafından sağlanan bağlamalar için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="1866d-149">This applies to the following system-provided bindings:</span></span>  
  
-   <xref:System.ServiceModel.BasicHttpBinding><span data-ttu-id="1866d-150">biçimindeki telefon numarasıdır.</span><span class="sxs-lookup"><span data-stu-id="1866d-150">.</span></span>  
  
-   <xref:System.ServiceModel.WSHttpBinding> <span data-ttu-id="1866d-151">ile <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> özelliğini `false`.</span><span class="sxs-lookup"><span data-stu-id="1866d-151">with the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property set to `false`.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1866d-152">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="1866d-152">Compiling the Code</span></span>  
  
-   <span data-ttu-id="1866d-153">Aşağıdaki ad alanlarını, kodu derlemek için gereklidir:</span><span class="sxs-lookup"><span data-stu-id="1866d-153">The following namespaces are required to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
## <a name="see-also"></a><span data-ttu-id="1866d-154">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1866d-154">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="1866d-155">Güvenli İletişimler ve Güvenli Oturumlar</span><span class="sxs-lookup"><span data-stu-id="1866d-155">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)
- [<span data-ttu-id="1866d-156">\<localClientSettings ></span><span class="sxs-lookup"><span data-stu-id="1866d-156">\<localClientSettings></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)
- [<span data-ttu-id="1866d-157">Nasıl yapılır: SecurityBindingElement Kullanarak Özel Bağlama Oluşturma</span><span class="sxs-lookup"><span data-stu-id="1866d-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
