---
title: Oluşturma ve bir iş akışı örneği çalıştırma
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: a86835155417692bc332bf51eb5825ce0b017b04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527269"
---
# <a name="creating-and-running-a-workflow-instance"></a>Oluşturma ve bir iş akışı örneği çalıştırma
Bu örnek, bir iş akışı örneği çalıştırmak gösterilmektedir. Bu, zaman uyumlu ve zaman uyumsuz olarak yürütmek nasıl gösterir.  
  
## <a name="demonstrates"></a>Gösteriler  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>Tartışma  
 İlk bölümü örneğinin kullandığı <xref:System.Activities.WorkflowInvoker.Invoke%2A>. Bu, bir iş akışını yürütmek için en basit yoludur. İş akışları ile yürütülen <xref:System.Activities.WorkflowInvoker.Invoke%2A> zaman uyumlu olarak yürütülür.  
  
 İkinci bölümü örneğinin kullandığı <xref:System.Activities.WorkflowApplication> sınıfı. <xref:System.Activities.WorkflowApplication> çalışan bir iş akışı ile etkileşim kurmak için ve zaman uyumsuz iş akışı çalıştırma olanağı dahil olmak üzere her bir örneği hakkında daha fazla denetime sahip olmanızı sağlar.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü. Devam etmeden önce şu (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek, şu dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>Ayrıca bkz.
- [WorkflowInvoker ve WorkflowApplication Kullanma](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
