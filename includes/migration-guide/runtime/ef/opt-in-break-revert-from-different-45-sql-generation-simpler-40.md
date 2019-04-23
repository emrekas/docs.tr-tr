---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774278"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="573ca-101">Öğesinden farklı 4.5 SQL oluşturma için daha basit 4.0 SQL oluşturma dönmek için kabul etme sonu</span><span class="sxs-lookup"><span data-stu-id="573ca-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="573ca-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="573ca-102">Details</span></span>|<span data-ttu-id="573ca-103">JOIN deyimleri oluşturmak ve bir çağrı içeren sorgular sınırlayan bir işleme ilk olmadan OrderBy artık ürettiğiniz daha basit SQL.</span><span class="sxs-lookup"><span data-stu-id="573ca-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="573ca-104">Bu sorgular, .NET Framework 4.5 sürümüne yükselttikten sonra önceki sürümlerinden daha karmaşık SQL oluşturdu.</span><span class="sxs-lookup"><span data-stu-id="573ca-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>|
|<span data-ttu-id="573ca-105">Öneri</span><span class="sxs-lookup"><span data-stu-id="573ca-105">Suggestion</span></span>|<span data-ttu-id="573ca-106">Bu özellik varsayılan olarak devre dışıdır.</span><span class="sxs-lookup"><span data-stu-id="573ca-106">This feature is disabled by default.</span></span> <span data-ttu-id="573ca-107">Entity Framework performans düşüşüne neden fazladan JOIN deyimleri oluşturursa aşağıdaki girişe ekleyerek bu özelliği etkinleştirebilirsiniz <code>&lt;appSettings&gt;</code> uygulama yapılandırma (app.config) dosyasından bölümünü:</span><span class="sxs-lookup"><span data-stu-id="573ca-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="573ca-108">Kapsam</span><span class="sxs-lookup"><span data-stu-id="573ca-108">Scope</span></span>|<span data-ttu-id="573ca-109">Geçirgen</span><span class="sxs-lookup"><span data-stu-id="573ca-109">Transparent</span></span>|
|<span data-ttu-id="573ca-110">Sürüm</span><span class="sxs-lookup"><span data-stu-id="573ca-110">Version</span></span>|<span data-ttu-id="573ca-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="573ca-111">4.5.2</span></span>|
|<span data-ttu-id="573ca-112">Tür</span><span class="sxs-lookup"><span data-stu-id="573ca-112">Type</span></span>|<span data-ttu-id="573ca-113">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="573ca-113">Runtime</span></span>|
