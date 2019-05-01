---
title: 'Hizmet: Güvenlik Doğrulama ve Kimlik Doğrulama Hataları'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: ba8da3ae6be6bd089690359f19e153da1e0b54fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998315"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="dee7f-102">Hizmet: Güvenlik Doğrulama ve Kimlik Doğrulama Hataları</span><span class="sxs-lookup"><span data-stu-id="dee7f-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="dee7f-103">Sayaç adı: Güvenlik Doğrulama ve Kimlik Doğrulama Hataları</span><span class="sxs-lookup"><span data-stu-id="dee7f-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="dee7f-104">Açıklama</span><span class="sxs-lookup"><span data-stu-id="dee7f-104">Description</span></span>  
 <span data-ttu-id="dee7f-105">Her bir ileti "Güvenlik çağrıları yetkilendirilmedi" sayacı tarafından kapsanmayan bir güvenlik sorunu nedeniyle reddedilmesi Bu sayaç artırılır.</span><span class="sxs-lookup"><span data-stu-id="dee7f-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="dee7f-106">Bu tür sorunlar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="dee7f-106">Such problems include:</span></span>  
  
- <span data-ttu-id="dee7f-107">İstemci belirteci iletiden okunamıyor.</span><span class="sxs-lookup"><span data-stu-id="dee7f-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="dee7f-108">İstemci belirteci (örneğin, hatalı parola) kimlik doğrulaması başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="dee7f-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
- <span data-ttu-id="dee7f-109">İmza doğrulaması başarısız oldu (örneğin, iletiyi oynanmadığını).</span><span class="sxs-lookup"><span data-stu-id="dee7f-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
- <span data-ttu-id="dee7f-110">İleti yeniden yürütme bir saldırı sırasında gerçekleşebilir bir önceki bir yineleniyor.</span><span class="sxs-lookup"><span data-stu-id="dee7f-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="dee7f-111">Bir şifre çözme hatası oluştu.</span><span class="sxs-lookup"><span data-stu-id="dee7f-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="dee7f-112">Gereken bazı öğeleri (örneğin, eksik bir zaman damgası veya şifrelenmiş veriler engelleme) gelen iletiyi yok.</span><span class="sxs-lookup"><span data-stu-id="dee7f-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="dee7f-113">TLSNEGO/SPNEGO anlaşması sırasında hatalar oluştu.</span><span class="sxs-lookup"><span data-stu-id="dee7f-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
