---
ms.openlocfilehash: a6f93bbdf39a1b525e2daeb12afc3a6392a66e30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235954"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="62017-101">.NET Framework 4. 5'altında serileştirilen MailMessage nesneleri seri durumdan çıkarma işlemi başarısız olabilir</span><span class="sxs-lookup"><span data-stu-id="62017-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="62017-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="62017-102">Details</span></span>|<span data-ttu-id="62017-103">.NET Framework 4.5 ile başlayarak <xref:System.Web.Mail.MailMessage> nesneleri, ASCII olmayan karakterler içerebilir.</span><span class="sxs-lookup"><span data-stu-id="62017-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="62017-104">.NET Framework 4'te yalnızca ASCII karakterleri desteklenir.</span><span class="sxs-lookup"><span data-stu-id="62017-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="62017-105"><xref:System.Web.Mail.MailMessage> ASCII olmayan karakterler içeren ve .NET Framework 4.5 ya da daha sonra serileştirilmiş nesneler, .NET Framework 4 altında seri durumdan çıkarılamıyor.</span><span class="sxs-lookup"><span data-stu-id="62017-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>|
|<span data-ttu-id="62017-106">Öneri</span><span class="sxs-lookup"><span data-stu-id="62017-106">Suggestion</span></span>|<span data-ttu-id="62017-107">Kodunuzu işlenirken özel durum işleme sağladığı, bir <xref:System.Web.Mail.MailMessage> nesne.</span><span class="sxs-lookup"><span data-stu-id="62017-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>|
|<span data-ttu-id="62017-108">Kapsam</span><span class="sxs-lookup"><span data-stu-id="62017-108">Scope</span></span>|<span data-ttu-id="62017-109">İkincil</span><span class="sxs-lookup"><span data-stu-id="62017-109">Minor</span></span>|
|<span data-ttu-id="62017-110">Sürüm</span><span class="sxs-lookup"><span data-stu-id="62017-110">Version</span></span>|<span data-ttu-id="62017-111">4,5</span><span class="sxs-lookup"><span data-stu-id="62017-111">4.5</span></span>|
|<span data-ttu-id="62017-112">Tür</span><span class="sxs-lookup"><span data-stu-id="62017-112">Type</span></span>|<span data-ttu-id="62017-113">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="62017-113">Runtime</span></span>|
|<span data-ttu-id="62017-114">Etkilenen API’ler</span><span class="sxs-lookup"><span data-stu-id="62017-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
