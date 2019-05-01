---
title: JSON Seri Hale Getirme
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: bb38005c02e9b3e850282d2a81c2e17143657025
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989865"
---
# <a name="json-serialization"></a>JSON Seri Hale Getirme
Bu örnek nasıl kullanılacağını gösterir <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> JavaScript nesne gösterimi (JSON) biçimindeki verileri seri hale getrime ve için. Bu serileştirme motoruna JSON verilerini örneğine dönüştürür [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] türler ve JSON verilerini içine geri. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> aynı türlerini destekleyen <xref:System.Runtime.Serialization.DataContractSerializer>. JSON veri biçimi zaman uyumsuz JavaScript ve XML (AJAX) yazma sırasında özellikle yararlı olur-Web uygulamaları stili. AJAX desteği Windows Communication Foundation (WCF) ScriptManager denetimi aracılığıyla ASP.NET AJAX ile kullanım için optimize edilmiştir. ASP.NET AJAX ile Windows Communication Foundation (WCF) kullanma örnekleri için bkz: [AJAX örnekleri](ajax.md).  
  
> [!NOTE]
>  Bu örnek için Kurulum yordamı ve derleme yönergeleri Bu konunun sonunda yer alır.  
  
 Örnek kullanan bir `Person` veri sözleşme serileştirme ve seri durumundan çıkarma göstermek.  

```csharp
[DataContract]
class Person
{
    [DataMember]
    internal string name;

    [DataMember]
    internal int age;
}
```

 Bir örneğini serileştirmek için `Person` JSON olarak yazın, oluşturun <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> ilk ve `WriteObject` JSON verilerini bir akışa yazmak için yöntemi.  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 Bellek akışı geçerli JSON verilerini içerir.
  
```json  
{"age":42,"name":"John"}  
```  
  
 Örnek, bir nesnede JSON verileri seri durumdan çıkarılırken gösterir. Ardından akış ve çağrı rewind `ReadObject`.  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 İnceleme `p2` nesnesi, JSON verilerini doğru şekilde seri durumdan, ortaya çıkarır.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü. Devam etmeden önce şu (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek, şu dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Ayarlamak için derleme ve örneği çalıştırma  
  
1. ' % S'çözüm JsonSerialization.sln açıklandığı gibi oluşturmak [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Sonuçta elde edilen konsol uygulamasını çalıştırın.  
