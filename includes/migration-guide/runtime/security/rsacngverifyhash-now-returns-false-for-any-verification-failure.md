---
ms.openlocfilehash: acf4e8df2cef3d9ec5d123a14cc7bfcd6f1bfb8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236086"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="2184d-101">RSACng.VerifyHash için herhangi bir doğrulama hatası şimdi false değerini döndürür</span><span class="sxs-lookup"><span data-stu-id="2184d-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2184d-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="2184d-102">Details</span></span>|<span data-ttu-id="2184d-103">.NET Framework 4.6.2 ile başlayarak, bu yöntemi döndürür <strong>False</strong> imzası hatalı biçimlendirilmiş olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="2184d-103">Starting with the .NET Framework 4.6.2, this method returns <strong>False</strong> if the signature itself is badly formatted.</span></span> <span data-ttu-id="2184d-104">Artık, herhangi bir doğrulama hata için false döndürür. .NET Framework 4.6 ve 4.6.1 çağırılıyorsa yöntem bir <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> imzası hatalı biçimlendirilmiş olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="2184d-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="2184d-105">Öneri</span><span class="sxs-lookup"><span data-stu-id="2184d-105">Suggestion</span></span>|<span data-ttu-id="2184d-106">Yürütme bağlıdır işleme üzerinde herhangi bir kod <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> doğrulama başarısız olursa bunun yerine getirmesi gerekir ve yöntemi <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="2184d-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns <strong>False</strong>.</span></span>|
|<span data-ttu-id="2184d-107">Kapsam</span><span class="sxs-lookup"><span data-stu-id="2184d-107">Scope</span></span>|<span data-ttu-id="2184d-108">İkincil</span><span class="sxs-lookup"><span data-stu-id="2184d-108">Minor</span></span>|
|<span data-ttu-id="2184d-109">Sürüm</span><span class="sxs-lookup"><span data-stu-id="2184d-109">Version</span></span>|<span data-ttu-id="2184d-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="2184d-110">4.6.2</span></span>|
|<span data-ttu-id="2184d-111">Tür</span><span class="sxs-lookup"><span data-stu-id="2184d-111">Type</span></span>|<span data-ttu-id="2184d-112">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="2184d-112">Runtime</span></span>|
|<span data-ttu-id="2184d-113">Etkilenen API’ler</span><span class="sxs-lookup"><span data-stu-id="2184d-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
