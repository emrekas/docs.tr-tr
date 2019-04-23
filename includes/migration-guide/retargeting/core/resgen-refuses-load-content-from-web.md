---
ms.openlocfilehash: 6cdd410cc818c2c0a993a364e550f5f92ed6a821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59981869"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a><span data-ttu-id="e1fe5-101">İçeriği Web'den yüklemek ResGen reddediyor</span><span class="sxs-lookup"><span data-stu-id="e1fe5-101">Resgen refuses to load content from the web</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e1fe5-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="e1fe5-102">Details</span></span>|<span data-ttu-id="e1fe5-103">.resx dosyalarını ikili biçimlendirilmiş bir giriş içeriyor olabilir.</span><span class="sxs-lookup"><span data-stu-id="e1fe5-103">.resx files may contain binary formatted input.</span></span> <span data-ttu-id="e1fe5-104">Resgen, güvenilmeyen bir konumdan indirilen dosya yüklemek için kullanmayı denerseniz, varsayılan olarak giriş yükleme başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="e1fe5-104">If you attempt to use resgen to load a file that was downloaded from an untrusted location, it will fail to load the input by default.</span></span>|
|<span data-ttu-id="e1fe5-105">Öneri</span><span class="sxs-lookup"><span data-stu-id="e1fe5-105">Suggestion</span></span>|<span data-ttu-id="e1fe5-106">İkili biçimlendirilmiş bir giriş güvenilmeyen konumlardan gerektiren Resgen kullanıcılar web işareti giriş dosyasından kaldırın veya geri çevirme quirk uygulayın. Makine geniş çevirme quirk uygulamak için aşağıdaki kayıt defteri ayarını ekleyin: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span><span class="sxs-lookup"><span data-stu-id="e1fe5-106">Resgen users who require loading binary formatted input from untrusted locations can either remove the mark of the web from the input file or apply the opt-out quirk.Add the following registry setting to apply the machine wide opt-out quirk: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span></span>|
|<span data-ttu-id="e1fe5-107">Kapsam</span><span class="sxs-lookup"><span data-stu-id="e1fe5-107">Scope</span></span>|<span data-ttu-id="e1fe5-108">Kenar</span><span class="sxs-lookup"><span data-stu-id="e1fe5-108">Edge</span></span>|
|<span data-ttu-id="e1fe5-109">Sürüm</span><span class="sxs-lookup"><span data-stu-id="e1fe5-109">Version</span></span>|<span data-ttu-id="e1fe5-110">4.7.2</span><span class="sxs-lookup"><span data-stu-id="e1fe5-110">4.7.2</span></span>|
|<span data-ttu-id="e1fe5-111">Tür</span><span class="sxs-lookup"><span data-stu-id="e1fe5-111">Type</span></span>|<span data-ttu-id="e1fe5-112">Yeniden Hedefleme</span><span class="sxs-lookup"><span data-stu-id="e1fe5-112">Retargeting</span></span>|
