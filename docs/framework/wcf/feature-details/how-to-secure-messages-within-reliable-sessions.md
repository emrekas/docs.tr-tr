---
title: 'Nasıl yapılır: Oturumlarla iletileri güvenli hale getirme'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: ee35f2a36ca08814423b5a3d0b1432bacd28c2e5
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2019
ms.locfileid: "56333059"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="07a7a-102">Nasıl yapılır: Oturumlarla iletileri güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="07a7a-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="07a7a-103">Bu konuda, bu tür bir oturumu destekleyen sistem tarafından sağlanan bağlamalar, ancak değil, varsayılan olarak kullanarak bir güvenilir oturum içinde değiştirilen iletileri için ileti düzeyi güvenliği etkinleştirmek için gereken adımlar açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="07a7a-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="07a7a-104">Kesin kod kullanarak veya bildirimli olarak yapılandırma dosyasında bir güvenli, güvenilir oturum etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="07a7a-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="07a7a-105">Bu yordam, güvenli, güvenilir oturum etkinleştirmek için hizmet ve istemci yapılandırma dosyalarını kullanır.</span><span class="sxs-lookup"><span data-stu-id="07a7a-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="07a7a-106">Bu yordam, aşağıdaki üç temel görevleri oluşur:</span><span class="sxs-lookup"><span data-stu-id="07a7a-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="07a7a-107">İstemci ve hizmet iletileri güvenilir bir oturumda exchange belirtin.</span><span class="sxs-lookup"><span data-stu-id="07a7a-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="07a7a-108">İleti düzeyi güvenliği, güvenilir oturum içinde gerektirir.</span><span class="sxs-lookup"><span data-stu-id="07a7a-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="07a7a-109">İstemci Hizmeti ile kimlik doğrulaması için kullanmanız gereken istemci kimlik bilgisi türü belirtin.</span><span class="sxs-lookup"><span data-stu-id="07a7a-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="07a7a-110">Uç nokta yapılandırma öğesi içeren ilk görevi önemli olduğu bir `bindingConfiguration` (Bu örnekte) adlı bir bağlama yapılandırmasını başvuran öznitelik `MessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="07a7a-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="07a7a-111">[  **\<Bağlama >** ](../../../../docs/framework/misc/binding.md) yapılandırma öğesi daha sonra güvenilir oturumlar etkinleştirmek için bu ada başvuran `enabled` özniteliği [  **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) öğesine `true`.</span><span class="sxs-lookup"><span data-stu-id="07a7a-111">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="07a7a-112">Sıralı teslim Güvenceleri güvenilir bir oturumda ayarlayarak kullanılabilir olmasını gerektiren `ordered` özniteliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="07a7a-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="07a7a-113">Bu yapılandırma yordamını tabanlı örnek kaynak kopyası için bkz: [WS güvenilir oturum](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="07a7a-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="07a7a-114">İkinci görev temel öğelerini ayarlayarak yapılır `mode` özniteliği  **\<Güvenlik >** içerdiği öğesi  **\<bağlama >** öğe için hizmet ve istemci `Message`.</span><span class="sxs-lookup"><span data-stu-id="07a7a-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="07a7a-115">Üçüncü görev temel öğelerini ayarlayarak yapılır `clientCredentialType` özniteliği  **\<ileti >** içerdiği öğesi  **\<Güvenlik >** öğe için hizmet ve istemci `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="07a7a-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="07a7a-116">İleti güvenliği ile güvenilir oturumlar kullanırken, bir zaman aşımı ilk başarısızlık durumunda bir özel durum atma yerine gerçekleşene kadar kimliği doğrulanmamış bir istemci kimlik doğrulaması güvenilir Mesajlaşma çalışır.</span><span class="sxs-lookup"><span data-stu-id="07a7a-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="07a7a-117">Güvenilir oturum kullanılacak WSHttpBinding hizmetini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="07a7a-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="07a7a-118">Bu yordamda açıklanan [nasıl yapılır: Oturumda ileti bir güvenilir](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="07a7a-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="07a7a-119">Güvenilir oturum kullanılacak WSHttpBinding istemciyi Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="07a7a-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="07a7a-120">Bu yordamda açıklanan [nasıl yapılır: Oturumda ileti bir güvenilir](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="07a7a-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="07a7a-121">Yapılandırma modu ve ClientCredentialType ayarlayın</span><span class="sxs-lookup"><span data-stu-id="07a7a-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="07a7a-122">Uygun bağlama öğeye ekleme [  **\<bağlamaları >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) yapılandırma dosyasının öğesi.</span><span class="sxs-lookup"><span data-stu-id="07a7a-122">Add an appropriate binding element to the [**\<bindings>**](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="07a7a-123">Aşağıdaki örnek ekler bir [  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="07a7a-123">The following example adds a [**\<wsHttpBinding>**](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="07a7a-124">Ekleme bir  **\<bağlama >** öğesi ve kümesi kendi `name` özniteliği için uygun bir değer.</span><span class="sxs-lookup"><span data-stu-id="07a7a-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="07a7a-125">Örnek adı kullanan `MessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="07a7a-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="07a7a-126">Ekleme bir  **\<Güvenlik >** öğesi ve kümesi `mode` özniteliğini `Message`.</span><span class="sxs-lookup"><span data-stu-id="07a7a-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="07a7a-127">İçinde  **\<Güvenlik >** öğe, Ekle bir  **\<ileti >** öğesi ve kümesi `clientCredentialType` özniteliğini `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="07a7a-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
