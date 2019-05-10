---
title: Windows Workflow’a Genel Bakış
ms.date: 03/30/2017
ms.assetid: fc44adbe-1412-49ae-81af-0298be44aae6
ms.openlocfilehash: bb714e5e5e4c1fe009ffa775efb456ebcc65c218
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592565"
---
# <a name="windows-workflow-overview"></a>Windows Workflow’a Genel Bakış
Bir iş akışı olarak adlandırılan elemental birimler kümesidir *etkinlikleri* gerçek hayattaki bir işleme açıklayan model olarak depolanır. İş akışları yürütme düzenini ve kısa veya uzun süren iş parçaları arasındaki bağımlı ilişkileri açıklamak için bir yol sağlar. Bu iş modeliyle baştan geçirir ve etkinlikleri sistem işlevlerini veya kişiler tarafından yürütülmesi gerekir.  
  
## <a name="workflow-run-time-engine"></a>İş akışı çalışma zamanı altyapısı  
 Çalışan her iş akışı örneği oluşturulur ve ana bilgisayar işlemi aşağıdakilerden biri etkileşim, bir işlem çalışma zamanı altyapısı tarafından korunur:  
  
- A <xref:System.Activities.WorkflowInvoker>, iş akışı gibi bir yöntem çağırır.  
  
- A <xref:System.Activities.WorkflowApplication> yürütme tek bir iş akışı örneğinin üzerinde kesin denetim.  
  
- A <xref:System.ServiceModel.WorkflowServiceHost> ileti tabanlı etkileşimler çok örnekli senaryolarda için.  
  
 Bu sınıfların her birini olarak temsil edilen temel etkinlik çalışma zamanı saran bir <xref:System.Activities.ActivityInstance> Etkinlik yürütme sorumludur. Birkaç da olabilir <xref:System.Activities.ActivityInstance> eşzamanlı olarak çalışan bir uygulama etki alanı içindeki nesneleri.  
  
 Önceki üç konak etkileşimi nesnelerin her biri, bir iş akışı program olarak başvurulan etkinliklerin ağacından oluşturulur. Bu tür veya sarmalayan bir özel konak kullanarak <xref:System.Activities.ActivityInstance>, iş akışı konsol uygulamaları dahil olmak üzere herhangi bir Windows işlem içinde yürütülebilir form tabanlı uygulamalar, Windows Hizmetleri [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web siteleri ve Windows Communication Foundation () WCF) Hizmetleri.  
  
 ![İş akışı ana bilgisayarı işlemi bileşenlerde](./media/44c79d1d-178b-4487-87ed-3e33015a3842.gif "44c79d1d-178b-4487-87ed-3e33015a3842")  
Ana bilgisayar işlemdeki iş akışı bileşenleri  
  
## <a name="interaction-between-workflow-components"></a>İş akışı bileşenleri arasındaki etkileşimi  
 Aşağıdaki diyagramda, iş akışı bileşenlerinin birbirleriyle nasıl etkileşim kurduklarını gösterir.  
  
 ![İş akışı bileşenlerinin nasıl etkileştiğini gösteren diyagram.](./media/overview/workflow-component-interatction.gif)  
  
 Yukarıdaki diyagramda <xref:System.Activities.WorkflowInvoker.Invoke%2A> yöntemi <xref:System.Activities.WorkflowInvoker> sınıfı, birden çok iş akışı örnekleri çağırmak için kullanılır. <xref:System.Activities.WorkflowInvoker> ana bilgisayardan yönetim gerektirmeyen basit iş akışları için kullanılır; ana bilgisayardan yönetim gereken iş akışları (gibi <xref:System.Activities.Bookmark> sürdürme) kullanarak yürütülmelidir <xref:System.Activities.WorkflowApplication.Run%2A> yerine. Bir iş akışı örneği başka çağırmadan önce tamamlanmasını beklemeniz gerekmez; çalışma zamanı altyapısı, birden çok iş akışı örneği eşzamanlı olarak çalıştırılmasını destekler.  Çağrılan iş akışı aşağıdaki gibidir:  
  
- A <xref:System.Activities.Statements.Sequence> içeren etkinlik bir <xref:System.Activities.Statements.WriteLine> alt etkinlik. A <xref:System.Activities.Variable> etkinliğin üst öğesinin bağlı olduğu bir <xref:System.Activities.InArgument> alt etkinlik. Hakkında değişkenleri, bağımsız değişkenleri ve bağlama hakkında daha fazla bilgi için bkz. [değişkenleri ve bağımsız değişkenler](variables-and-arguments.md).  
  
- Özel bir etkinlik olarak adlandırılan `ReadLine`. Bir <xref:System.Activities.OutArgument> , `ReadLine` etkinlik çağırmak için döndürülen <xref:System.Activities.WorkflowInvoker.Invoke%2A> yöntemi.  
  
- Öğesinden türetilen özel bir etkinlik <xref:System.Activities.CodeActivity> soyut sınıf. <xref:System.Activities.CodeActivity> Çalışma zamanı özelliklerine (örneğin, izleme ve Özellikler) erişebilirsiniz kullanarak <xref:System.Activities.CodeActivityContext> bir parametresi olarak kullanılabilen <xref:System.Activities.CodeActivity.Execute%2A> yöntemi. Bu çalışma zamanı özellikleri hakkında daha fazla bilgi için bkz: [takip ve izleme iş akışı](workflow-tracking-and-tracing.md) ve [iş akışı yürütme özellikleri](workflow-execution-properties.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [BizTalk Server 2006 veya WF? Projeniz için doğru iş akışı aracı seçme](https://go.microsoft.com/fwlink/?LinkId=154901)
