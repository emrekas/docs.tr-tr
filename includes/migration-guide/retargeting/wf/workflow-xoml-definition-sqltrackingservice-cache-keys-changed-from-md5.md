---
ms.openlocfilehash: 47aa67096f8dcd250521d9c34dde97cb2eb368d7
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803469"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a>İş akışı XOML tanımını ve SqlTrackingService önbellek anahtarları için SHA256 MD5 değiştirildi

|   |   |
|---|---|
|Ayrıntılar|İş akışı çalışma zamanı'nda iş akışı tanımı XOML içinde tanımlanan bir önbellekte tutar. SqlTrackingService dizeleri tarafından Anahtarlanan bir önbellek da tutar. Bu Önbelleklerin sağlama toplamı karma değeri içeren değerleri tarafından Anahtarlanan. .NET Framework 4.7.2 ve önceki sürümleri, bu sağlama toplamı karma FIPS etkin sistemlerinde sorunları nedeniyle MD5 algoritma kullanılır. .NET Framework 4.8 ile başlayarak, kullanılan algoritması SHA256 olan. Değerleri iş akışı çalışma zamanı ve SqlTrackingService başlatıldığında her seferinde yeniden hesaplanır çünkü bu değişiklik ile bir uyumluluk sorunu olmamalıdır. Ancak, gerekirse geri eski karma algoritması kullanımına geri dönmek kanıtlayabilecekleri quirks sağladık.|
|Öneri|Bu değişiklik iş akışı çalıştırılırken bir sorun sunarsa, aşağıdakilerden birini veya her ikisi de ayarını deneyin <code>AppContext</code> anahtarlar:<ul><li>&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; true.</li><li>&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; to true.</li></ul>Kod:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>Veya yapılandırma dosyasında (Bu oluşturan uygulamanın yapılandırma dosyasında olması gereken <xref:System.Workflow.Runtime.WorkflowRuntime> nesnesi):<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Kapsam|İkincil|
|Sürüm|4.8|
|Tür|Yeniden Hedefleme|

