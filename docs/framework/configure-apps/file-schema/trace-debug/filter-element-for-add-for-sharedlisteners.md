---
title: <filter>İçin için <add> öğesi<sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 571a3add232f3e4f9747040dc104b85e8cc3085e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920504"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a>\<sharedListeners için \<> \<eklemek için > öğesini filtreleyin >
`sharedListeners` Koleksiyondaki bir dinleyiciye bir filtre ekler.  
  
 \<Yapılandırma >  
\<System. Diagnostics >  
\<sharedListeners > öğesi  
\<> Ekle  
\<Filtre >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**type**|Gerekli öznitelik.<br /><br /> Filtrenin türünü belirtir. Türün tam adını ( <xref:System.Type.FullName%2A?displayProperty=nameWithType> özelliğinin biçiminde) veya derleme bilgileri de dahil olmak üzere tam nitelikli tür adını ( <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> özelliğin biçiminde) kullanabilirsiniz. Tam nitelikli tür adı oluşturma hakkında bilgi için, bkz. [tam nitelikli tür adları belirtme](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|İsteğe bağlı öznitelik.<br /><br /> Belirtilen sınıf için oluşturucuya geçirilen dize.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|  
|`system.diagnostics`|İletileri ve bir izleme anahtarının ayarlandığı düzeyi depolayan, depolayan ve yönlendiren izleme dinleyicilerini belirtir.|  
|`sharedListeners`|Herhangi bir kaynak veya izleme öğesinin başvurmasına yönelik bir dinleyici koleksiyonu.|  
|`add`|**SharedListeners** koleksiyonuna bir dinleyici ekler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `<add>` Bir dinleyici `<sharedListeners>` öğenin öğesi içinde tanımlanmışsa, bu dinleyicinin filtresi `<add>` öğenin alt öğesi olan bir `<filter>` öğe içinde tanımlanmalıdır.  
  
 Bu öğe makine yapılandırma dosyasında (Machine. config) ve uygulama yapılandırma dosyasında kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, `<filter>` `sharedListeners` koleksiyonundaki izleme dinleyicisine `console` bir filtre eklemek için öğesinin nasıl kullanılacağını gösterir.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [İzleme ve Hata Ayıklama Ayarları Şeması](index.md)
