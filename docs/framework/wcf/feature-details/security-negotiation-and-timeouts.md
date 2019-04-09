---
title: Güvenlik Görüşmeleri ve Zaman Aşımları
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: a02c9d7b42eadf9a5ce9af8022fe292d6c23249c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180654"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="7a954-102">Güvenlik Görüşmeleri ve Zaman Aşımları</span><span class="sxs-lookup"><span data-stu-id="7a954-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="7a954-103">İstemciler ve hizmetler kimlik doğrulaması sırasında Windows Communication Foundation (WCF) hizmet kimlik bilgisi kimlik doğrulaması bir parçası olarak nerede anlaşılan bir modu destekler.</span><span class="sxs-lookup"><span data-stu-id="7a954-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="7a954-104">Böyle senaryolarda, büyük olasılıkla çok oluşturan exchange istemci ve hizmet için hizmet kimlik bilgilerini istemci yayılması arasında gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="7a954-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="7a954-105"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> Özellik denetler çok oluşturan exchange tamamlanması ne kadar sürebilir.</span><span class="sxs-lookup"><span data-stu-id="7a954-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="7a954-106">Exchange gerçekten daha fazla sürer ancak, bu zaman aşımı yalnızca geçerlidir, tek bir istek-yanıt.</span><span class="sxs-lookup"><span data-stu-id="7a954-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="7a954-107">Burada anlaşma tek bir gidiş dönüş tamamlandıktan durumlarda, zaman aşımı geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="7a954-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a954-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7a954-108">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="7a954-109">Nasıl yapılır: Maksimum Saat Eğriltme Ayarlama</span><span class="sxs-lookup"><span data-stu-id="7a954-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
