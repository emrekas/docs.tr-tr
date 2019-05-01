---
title: 'Uç noktası: Güvenlik Doğrulaması ve Kimlik Doğrulaması Hatası/Saniye'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: 43886f79585fb9a63eeb51360cc869365c100a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916545"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="c6ae7-102">Uç noktası: Güvenlik Doğrulaması ve Kimlik Doğrulaması Hatası/Saniye</span><span class="sxs-lookup"><span data-stu-id="c6ae7-102">Endpoint: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="c6ae7-103">Sayaç adı: Güvenlik Doğrulaması ve Kimlik Doğrulaması Hatası/Saniye</span><span class="sxs-lookup"><span data-stu-id="c6ae7-103">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="c6ae7-104">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c6ae7-104">Description</span></span>  
 <span data-ttu-id="c6ae7-105">Her bir ileti "Güvenlik çağrıları yetkilendirilmedi" sayacı tarafından kapsanmayan bir güvenlik sorunu nedeniyle reddedilmesi Bu sayaç artırılır.</span><span class="sxs-lookup"><span data-stu-id="c6ae7-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="c6ae7-106">Bu tür sorunlar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="c6ae7-106">Such problems include:</span></span>  
  
- <span data-ttu-id="c6ae7-107">İstemci belirteci iletiden okunamıyor.</span><span class="sxs-lookup"><span data-stu-id="c6ae7-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="c6ae7-108">İstemci belirteci (örneğin, hatalı parola) kimlik doğrulaması başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="c6ae7-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="c6ae7-109">İmza doğrulaması başarısız oldu (örneğin, iletiyi oynanmadığını).</span><span class="sxs-lookup"><span data-stu-id="c6ae7-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="c6ae7-110">İleti yeniden yürütme bir saldırı sırasında gerçekleşebilir bir önceki bir yineleniyor.</span><span class="sxs-lookup"><span data-stu-id="c6ae7-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="c6ae7-111">Bir şifre çözme hatası oluştu.</span><span class="sxs-lookup"><span data-stu-id="c6ae7-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="c6ae7-112">Gereken bazı öğeleri (örneğin, eksik bir zaman damgası veya şifrelenmiş veriler engelle) gelen iletiyi yok.</span><span class="sxs-lookup"><span data-stu-id="c6ae7-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="c6ae7-113">TLSNEGO/SPNEGO anlaşması sırasında hatalar oluştu.</span><span class="sxs-lookup"><span data-stu-id="c6ae7-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="c6ae7-114">Bu sayaç performans sayacı türüdür [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), değeri aşağıdaki formül kullanılarak hesaplanır:</span><span class="sxs-lookup"><span data-stu-id="c6ae7-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="c6ae7-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="c6ae7-115">(N1-N0)/((D1-D0)/F)</span></span>
