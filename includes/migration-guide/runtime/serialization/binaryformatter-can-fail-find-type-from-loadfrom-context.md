---
ms.openlocfilehash: ac929a8b3e9a7d56122f5699c51819ad483d1f5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805297"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a>BinaryFormatter LoadFrom bağlamı türünden bulmak başarısız olabilir

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.5, bir dizi itibarıyla <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> kullanırken, değişiklikler seri durumundan çıkarma farklılıkları neden olabilir <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> LoadFrom bağlamı yüklenen türler seri durumdan çıkarılacak. Bu değişiklikler nedeniyle yeni yöntemlerdir <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> artık farklı bir davranış neden olan bir tür yükler, bir <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> daha sonra bu türe seri durumdan çıkarmak çalışır. Bu eski XmlSerializer davranışına göre bazı durumlarda çalışmış olabilir ancak varsayılan serileştirme Bağlayıcısı LoadFrom bağlamı otomatik olarak aramaz. Farklı bir bağlamda yüklenmiş bir derlemeden bir tür yüklenirken değişiklikleri nedeniyle bir <xref:System.IO.FileNotFoundException?displayProperty=name> oluşturulabilir.|
|Öneri|Bu özel durumun görülür, <code>Binder</code> özelliği <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> doğru türde bulduğunuz bir özel bağlayıcı için ayarlanabilir.<pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre>Ve ardından özel bağlayıcı:<pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>|
|Kapsam|Kenar|
|Sürüm|4,5|
|Tür|Çalışma zamanı|
|Etkilenen API’ler|<ul><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
