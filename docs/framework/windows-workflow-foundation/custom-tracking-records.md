---
title: Özel izleme kayıtları
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 7f866713b5d6f6c82dff80864f2eccb5d2f6cb30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529836"
---
# <a name="custom-tracking-records"></a>Özel izleme kayıtları
Bu konu, özel izleme kayıtları oluşturmak ve bunları birlikte kayıtları yayılan verilerle doldurabilirsiniz gösterilmektedir.  
  
## <a name="emitting-custom-tracking-records"></a>Özel izleme kayıtları yayma  
 Özel izleme kayıtları, aşağıdaki örnekte gösterildiği gibi bir kod etkinliği yayılabilir.  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 A <xref:System.Activities.Tracking.CustomTrackingRecord> çağırarak bir kod etkinliği yayılan <xref:System.Activities.NativeActivityContext.Track%2A> metodunda `ActvityContext`.  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Windows Server App Fabric izleme](https://go.microsoft.com/fwlink/?LinkId=201273)
- [App Fabric ile uygulamaları izleme](https://go.microsoft.com/fwlink/?LinkId=201275)
