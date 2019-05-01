---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764063"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="fd714-101">WCF MsmqSecureHashAlgorithm varsayılan değer SHA256 şimdi:</span><span class="sxs-lookup"><span data-stu-id="fd714-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fd714-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="fd714-102">Details</span></span>|<span data-ttu-id="fd714-103">.NET Framework 4.7.1 ile başlayarak, imza algoritması wcf'de Msmq iletileri için varsayılan SHA256 iletisidir.</span><span class="sxs-lookup"><span data-stu-id="fd714-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="fd714-104">.NET Framework 4.7 ve önceki sürümleri, imza algoritması varsayılan ileti SHA1 ' dir.</span><span class="sxs-lookup"><span data-stu-id="fd714-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="fd714-105">Öneri</span><span class="sxs-lookup"><span data-stu-id="fd714-105">Suggestion</span></span>|<span data-ttu-id="fd714-106">.NET Framework 4.7.1 uyumluluk sorunları bu değişikliği halinde çalıştırın ya da daha sonra değişikliğin aşağıdaki satırı ekleyerek çevirme <code>&lt;runtime&gt;</code>app.config dosyanıza bölümünü:</span><span class="sxs-lookup"><span data-stu-id="fd714-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="fd714-107">Kapsam</span><span class="sxs-lookup"><span data-stu-id="fd714-107">Scope</span></span>|<span data-ttu-id="fd714-108">İkincil</span><span class="sxs-lookup"><span data-stu-id="fd714-108">Minor</span></span>|
|<span data-ttu-id="fd714-109">Sürüm</span><span class="sxs-lookup"><span data-stu-id="fd714-109">Version</span></span>|<span data-ttu-id="fd714-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="fd714-110">4.7.1</span></span>|
|<span data-ttu-id="fd714-111">Tür</span><span class="sxs-lookup"><span data-stu-id="fd714-111">Type</span></span>|<span data-ttu-id="fd714-112">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="fd714-112">Runtime</span></span>|
