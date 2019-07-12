---
ms.openlocfilehash: a0dc2401155a162eaa5aa6b4d9e6af1ca1c2ccc8
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802706"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>Veri bağlama geliştirme KeyedCollection için

|   |   |
|---|---|
|Ayrıntılar|Sabit <xref:System.Windows.Data.Binding> kaynak nesnesi aynı imzaya sahip özel bir dizin oluşturucu bildirir, IList Indexer'ın yanlış kullanımı (örneğin KeyedCollection&lt;int, TItem&gt;).|
|Öneri|Sırayla bu değişiklik yararlanmak uygulama için .NET Framework 4.7.2 çalıştırmanız gerekir veya sonraki bir sürümü ve bu değişiklik aşağıdaki ekleyerek kabul et gerekir [AppContext anahtar](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) için <code>&lt;runtime&gt;</code> uygulama yapılandırma dosyasının ve Bu ayarın <code>false</code>:<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Kapsam|Ana|
|Sürüm|4.8|
|Tür|Çalışma zamanı|

