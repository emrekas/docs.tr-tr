---
title: Özel İzleme
ms.date: 03/30/2017
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
ms.openlocfilehash: b53b22b485a7ac340821073d2f2914b13a7b7011
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044297"
---
# <a name="custom-tracking"></a>Özel İzleme
Bu örnek, bir özel izleme katılımcısının nasıl oluşturulacağını ve izleme verilerinin içeriğini konsola nasıl yazılacağını gösterir. Buna ek olarak, örnek, Kullanıcı tanımlı verilerle <xref:System.Activities.Tracking.CustomTrackingRecord> doldurulmuş nesneleri nasıl yayılacağını gösterir. Konsol tabanlı izleme katılımcısı, kod içinde oluşturulan <xref:System.Activities.Tracking.TrackingRecord> bir izleme profili nesnesi kullanılarak iş akışı tarafından yayılan nesneleri filtreler.

## <a name="sample-details"></a>Örnek Ayrıntılar
 Windows Workflow Foundation (WF), bir iş akışı örneğinin yürütülmesini izlemek için bir izleme altyapısı sağlar. İzleme çalışma zamanı, iş akışı kullanım ömrü, iş akışı etkinliklerinin olayları ve özel izleme etkinlikleriyle ilgili olayları göstermek için bir iş akışı örneği uygular. Aşağıdaki tabloda izleme altyapısının birincil bileşenleri ayrıntılı olarak verilmiştir.

|Bileşen|Açıklama|
|---------------|-----------------|
|Çalışma zamanını izleme|İzleme kayıtlarını yaymakta olan altyapıyı sağlar.|
|Katılımcıları izleme|İzleme kayıtlarını tüketir. [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]izleme kayıtlarını Windows için olay Izleme (ETW) olayları olarak yazan bir izleme katılımcısına sahip olarak gelir.|
|İzleme profili|Bir iş akışı örneğinden yayılan izleme kayıtlarının bir alt kümesi için bir izleme katılımcısının abone olmasına izin veren bir filtreleme mekanizması.|

 Aşağıdaki tabloda iş akışı çalışma zamanının yaydığı izleme kayıtlarının ayrıntıları verilmiştir.

|İzleme kaydı|Açıklama|
|---------------------|-----------------|
|İş akışı örneği izleme kayıtları.|İş akışı örneğinin yaşam döngüsünü açıklar. Örneğin, iş akışı başladığında veya tamamlandığında bir örnek kayıt yayınlanır.|
|Etkinlik durumu Izleme kayıtları.|Ayrıntıları etkinlik yürütmesi. Bu kayıtlar, bir etkinliğin zamanlandığı veya etkinliğin ne zaman tamamlandığı ya da bir hata oluşturulduğu zaman gibi bir iş akışı etkinliğinin durumunu gösterir.|
|Bookmark sürdürme kaydı.|Bir iş akışı örneği içindeki bir yer işareti kaldığı zaman yayınlanır.|
|Özel Izleme kayıtları.|Bir iş akışı yazarı özel Izleme kayıtları oluşturabilir ve bunları özel etkinlik içinde yayabilir.|

 İzleme, izleme profilleri kullanılarak oluşturulan <xref:System.Activities.Tracking.TrackingRecord> nesnelerin bir alt kümesi için abone olur. Bir izleme profili, belirli bir izleme kayıt türü için abone 'e izin veren izleme sorguları içerir. İzleme profilleri kodda veya yapılandırmada belirtilebilir.

### <a name="custom-tracking-participant"></a>Özel Izleme Katılımcısı
 İzleme katılımcı API 'si, iş akışı çalışma zamanı tarafından yayılan nesneleri işlemek <xref:System.Activities.Tracking.TrackingRecord> için özel mantık içerebilen bir kullanıcı tarafından belirtilen izleme katılımcısından izleme çalışma zamanının uzantısına izin verir.

 Kullanıcının uygulaması <xref:System.Activities.Tracking.TrackingParticipant>gereken bir izleme katılımcısı yazmak için. Özellikle, <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> yöntemi özel katılımcı tarafından uygulanmalıdır. Bu yöntem, bir <xref:System.Activities.Tracking.TrackingRecord> iş akışı çalışma zamanı tarafından yayınlanarak çağrılır.

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 Tüm izleme katılımcısı ConsoleTrackingParticipant.cs dosyasında uygulanır. Aşağıdaki kod örneği <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> , özel izleme katılımcısının yöntemidir.

```csharp
protected override void Track(TrackingRecord record, TimeSpan timeout)
{
    ...
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;
    if (workflowInstanceRecord != null)
    {
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " Workflow InstanceID: {0} Workflow instance state: {1}",
            record.InstanceId, workflowInstanceRecord.State));
    }

    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;
    if (activityStateRecord != null)
    {
        IDictionary<String, object> variables = activityStateRecord.Variables;
        StringBuilder vars = new StringBuilder();

        if (variables.Count > 0)
        {
            vars.AppendLine("\n\tVariables:");
            foreach (KeyValuePair<string, object> variable in variables)
            {
                vars.AppendLine(String.Format(
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));
            }
        }
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",
                activityStateRecord.Activity.Name, activityStateRecord.State,
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));
    }

    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;

    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))
    {
        ...
    }
    Console.WriteLine();

}
```

 Aşağıdaki kod örneği, konsol katılımcısını iş akışı Invoker 'a ekler.

```csharp
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()
{
    ...
    // The tracking profile is set here, refer to Program.CS
...
}

WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
```

### <a name="emitting-custom-tracking-records"></a>Özel Izleme kayıtlarını yayma
 Bu örnek ayrıca özel bir iş akışı etkinliğinden <xref:System.Activities.Tracking.CustomTrackingRecord> nesneleri yayma özelliğini gösterir:

- <xref:System.Activities.Tracking.CustomTrackingRecord> Nesneler oluşturulur ve kaydıyla birlikte yayınlanmaları istenen kullanıcı tanımlı verilerle doldurulur.

- , Öğesinin Track yöntemi çağırarak yayılır. <xref:System.Activities.ActivityContext> <xref:System.Activities.Tracking.CustomTrackingRecord>

 Aşağıdaki örnek, nesneleri özel bir etkinlik <xref:System.Activities.Tracking.CustomTrackingRecord> içinde nasıl yayılacağını gösterir.

```csharp
// Create the Custom Tracking Record
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")
{
    Data =
    {
        {"OrderId", 200},
        {"OrderDate", "20 Aug 2001"}
    }
};

// Emit custom tracking record
context.Track(customRecord);
```

#### <a name="to-use-this-sample"></a>Bu örneği kullanmak için

1. Visual Studio 2010 kullanarak CustomTrackingSample. sln çözüm dosyasını açın.

2. Çözümü derlemek için CTRL + SHIFT + B tuşlarına basın.

3. Çözümü çalıştırmak için CTRL + F5 tuşlarına basın.

> [!IMPORTANT]
> Örnekler bilgisayarınızda zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizini denetleyin.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Bu dizin yoksa, tüm Windows Communication Foundation (WCF) ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri indirmek için [Windows Communication Foundation (WCF) ve Windows Workflow Foundation (WF) örneklerine .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) ' e gidin. Bu örnek, aşağıdaki dizinde bulunur.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a>Ayrıca bkz.

- [AppFabric Izleme örnekleri](https://go.microsoft.com/fwlink/?LinkId=193959)
