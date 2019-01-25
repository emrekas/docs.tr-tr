---
title: Güvenilir oturumlar
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 1d87f6f4d94763dc8f6ac7e929c22b17940097ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735431"
---
# <a name="reliable-sessions"></a><span data-ttu-id="28773-102">Güvenilir oturumlar</span><span class="sxs-lookup"><span data-stu-id="28773-102">Reliable Sessions</span></span>

<span data-ttu-id="28773-103">Bu bölümde, hangi bir Windows Communication Foundation (güvenilir oturum WCF), ne, nasıl kullanıldığı ve ne zaman kullanmak için hangi bağlama yapılandırmaları destekliyorsa ve işaretçilerde en iyi uygulamalar açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="28773-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="28773-104">Önemli noktaları ve bu bölümdeki ilgili konular hakkında ayrıntıları aşağıdaki tabloda özetlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="28773-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="28773-105">Güvenilir oturum WCF uç noktaları arasında gönderilen iletilerin SOAP veya aktarım aracılar arasında aktarılır ve yalnızca bir kez ve isteğe bağlı olarak, hangi gönderildikleri sırayla dağıtılır featrues sağlar.</span><span class="sxs-lookup"><span data-stu-id="28773-105">The reliable session WCF provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="28773-106">Güvenilir oturum WCF uygulamayla kullanmak için varsayılan olarak veya isteğe bağlı olarak bir güvenilir oturum destekleyen sistem tarafından sağlanan bağlamalar wcf'de birini kullanın veya oturumu destekler, kendi özel bağlama oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="28773-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="28773-107">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="28773-107">In This Section</span></span>

<span data-ttu-id="28773-108">[Güvenilir oturumlar genel bakış](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="28773-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="28773-109">Güvenilir oturumlar açıklar bunların güvenilir oturumları destekleyen farklı bağlamaları ne zaman kullanılacağı ve nasıl çalıştıkları.</span><span class="sxs-lookup"><span data-stu-id="28773-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="28773-110">[Nasıl yapılır: Güvenilir oturum içinde Exchange ileti](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="28773-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="28773-111">Yapılandırmada belirtilen özel bir bağlama kullanarak HTTP üzerinden bir güvenilir oturum oluşturmayı açıklar.</span><span class="sxs-lookup"><span data-stu-id="28773-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="28773-112">[Nasıl yapılır: Oturumlarla iletileri güvenli hale getirme](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="28773-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="28773-113">Güvenilir oturum güvenliğinin nasıl sağlanacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="28773-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="28773-114">[Nasıl yapılır: HTTPS ile özel bir güvenilir oturum bağlama oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="28773-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="28773-115">HTTPS üzerinden bir güvenilir oturum oluşturmayı açıklar.</span><span class="sxs-lookup"><span data-stu-id="28773-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="28773-116">[Güvenli oturumlar için en iyi uygulamalar](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="28773-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="28773-117">Güvenilir oturum kullanmayla ilişkili en iyi bazılarını açıklar.</span><span class="sxs-lookup"><span data-stu-id="28773-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="28773-118">Başvuru</span><span class="sxs-lookup"><span data-stu-id="28773-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="28773-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="28773-119">See also</span></span>

- [<span data-ttu-id="28773-120">Kuyruklar ve Güvenilir Oturumlar</span><span class="sxs-lookup"><span data-stu-id="28773-120">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [<span data-ttu-id="28773-121">Oturumlar, Örnek Oluşturma ve Eşzamanlılık</span><span class="sxs-lookup"><span data-stu-id="28773-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
