---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: f54028489ec5aa34ae38115d7a582b01b9da92f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931408"
---
# <a name="messagelogging"></a>\<messageLogging >
Bu öğe Windows Communication Foundation (WCF) ileti günlüğü özelliklerine yönelik ayarları tanımlar.  
  
 \<system.ServiceModel>  
\<Tanılama >  
\<messageLogging >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`logEntireMessage`|İletinin tamamının (ileti üst bilgisi ve gövdesi) günlüğe kaydedilip kaydedilmeyeceğini belirten bir Boole değeri. Varsayılan `false`olarak, yalnızca ileti üstbilgisinin günlüğe kaydedildiği anlamına gelir. Bu ayar tüm ileti günlüğü düzeylerini (hizmet, aktarım ve hatalı biçimlendirilmiş) etkiler.|  
|`logMalformedMessages`|Hatalı biçimlendirilmiş iletilerin günlüğe kaydedilip kaydedilmeyeceğini belirten bir Boole değeri. Hatalı biçimlendirilmiş iletiler, `maxMessagesToLog`öğesine doğru sayılmaz. Varsayılan, `false` değeridir.|  
|`logMessagesAtServiceLevel`|İletilerin hizmet düzeyinde (şifreleme ve aktarımlarla ilgili dönüşümlerden önce) izlenip izlenmediğini belirten bir Boole değeri. Varsayılan, `false` değeridir.|  
|`logMessagesAtTransportLevel`|İletilerin Aktarım düzeyinde izlenip izlenmediğini belirten bir Boolean değer. Yapılandırma dosyasında belirtilen filtreler uygulanır ve yalnızca filtrelerle eşleşen iletiler izlenebilir. Varsayılan, `false` değeridir.|  
|`maxMessagesToLog`|Günlüğe kaydedilecek en fazla ileti sayısını belirten pozitif bir tamsayı. Varsayılan değer 1000 ' dir.|  
|`maxSizeOfMessageToLog`|Günlüğe kaydedilecek bir iletinin bayt cinsinden en büyük boyutunu belirten pozitif bir tamsayı. Sınırdan daha büyük mesajlar günlüğe kaydedilmez. Bu ayar tüm izleme düzeylerini etkiler. Varsayılan değer 262144 ' dir (0x4000).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|filtreler|`filters` Öğesi XPath filtreleri koleksiyonunu tutar. Aktarım iletisi günlüğü etkin olduğunda (`logMessagesAtTransportLevel` yani `true`), yalnızca filtrelerle eşleşen iletiler günlüğe kaydedilir.<br /><br /> Filtreler yalnızca aktarım katmanında uygulanır. Hizmet düzeyi ve hatalı biçimlendirilmiş ileti günlüğe kaydetme, filtrelerle etkilenmez.<br /><br /> Bu öğenin `filter`tek özniteliği, bir XPathFilter.<br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|tanılama|Yönetici için çalışma zamanı incelemesi ve denetimi için WCF ayarlarını tanımlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 İletiler Yığındaki üç farklı düzeye kaydedilir: hizmet, taşıma ve hatalı biçimlendirilmiş. Her düzey ayrı olarak etkinleştirilebilir.  
  
 Aktarım ve hizmet düzeylerindeki belirli iletileri günlüğe kaydetmek için XPath filtreleri eklenebilir. Hiçbir filtre tanımlanmamışsa, tüm iletiler günlüğe kaydedilir. Filtreler yalnızca iletinin üst bilgilerine uygulanır. Gövde yoksayıldı. WCF, performansı artırmak için ileti gövdesini yoksayar. Gövdenin içeriğine göre filtrelemek istiyorsanız, filtre içeren özel bir dinleyici oluşturabilirsiniz.  
  
 İleti izlemeyi etkinleştirmek için bir izleme dinleyicisi oluşturmanız gerekir. Dinleyici, <xref:System.Diagnostics> izleme mimarisiyle birlikte çalışarak herhangi bir dinleyici olabilir. Aşağıdaki örnek, böyle bir dinleyicinin nasıl oluşturulacağını göstermektedir.  
  
```xml  
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel"
            switchValue="Verbose">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="ServiceModel Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="MessageLogging Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add initializeData="C:\ItProTools\TraceLog.xml"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="ServiceModel Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
    <add initializeData="C:\ItProTools\MessageLog.log"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="MessageLogging Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
  </sharedListeners>
</system.diagnostics>
```  
  
## <a name="example"></a>Örnek  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="42"
                maxSizeOfMessageToLog="42">
  <filters>
    <clear />
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [Günlüğe İleti Kaydetmeyi Yapılandırma](../../../wcf/diagnostics/configuring-message-logging.md)
