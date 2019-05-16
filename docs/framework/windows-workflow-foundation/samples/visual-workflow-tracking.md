---
title: Görsel İş Akışı İzleme
ms.date: 03/30/2017
ms.assetid: 0143448f-2044-40a0-8a3d-941f6d12468b
ms.openlocfilehash: abd9f294018f6aa1fd2020314688258ac00792f7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637795"
---
# <a name="visual-workflow-tracking"></a>Görsel İş Akışı İzleme
Bu örnek nasıl izleme uygulaması aracılığıyla hata ayıklama işlevselliğini kullanarak görsel bir iş akışı yazılacağını gösterir [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].

## <a name="sample-details"></a>Örnek Ayrıntıları
 Uygulama (Workflow.xaml içinde tanımlanmıştır) basit bir akış çizelgesi iş akışı çalıştırır ve o anda yürütülen iş akışı görüntülemek için iş akışı tasarımcısını yeniden barındırır. İş akışı yürütülür, o anda yürütülen etkinlik sarı bir anahat ve hata ayıklama ok ile gösterilir. Ayrıca, iş akışı tarafından oluşturulan izleme kayıtları da uygulama penceresinde görüntülenir. İş akışı izleme hakkında daha fazla bilgi için bkz: [takip ve izleme iş akışı](../workflow-tracking-and-tracing.md). İş akışı tasarımcısını yeniden barındırma hakkında daha fazla bilgi için bkz. [iş akışı tasarımcısını yeniden barındırma](../rehosting-the-workflow-designer.md).

 İş akışı simülatör iki sözlük tutarak çalışır. Şu anda yürütülen etkinlik nesnesi ve etkinlik örneği oluşturulan XAML satır numarası arasındaki eşlemeyi içerir. Diğer Etkinlik örneği kimliği ve etkinlik nesnesi arasındaki eşlemeyi içerir. Kullanarak bir özel izleme kayıtları yayılan profili, izleme uygulama şu anda yürütülen etkinliğin örnek kimliği belirler ve geri örneği XAML dosyası ile eşleştirir. Yeniden barındırılan iş akışı Tasarımcısı, Tasarımcı yüzeyine faaliyete vurgulayın ve özellikle etkinlik etrafında sarı bir kenarlık çizmek ve sol tarafında bir sarı ok görüntüleme iş akışı hata ayıklayıcı, aynı yöntemi kullanmak için talimat verilmiştir Tasarımcı.

#### <a name="to-use-this-sample"></a>Bu örneği kullanmak için

1. Visual Studio 2010'daki örnek dizinden WorkflowSimulator.sln dosyasını açın.

2. Çözümü derlemek için CTRL + SHIFT + B tuşlarına basın.

3. Örneği çalıştırmak için CTRL + F5 tuşlarına basın. Bu Workflow.xaml dosyası yeniden barındırılan iş akışı Tasarımcısı penceresinde görüntüler.

4. Tıklayın **dosya** menü ve select **iş akışı çalıştırma...** .

5. Daha önce açıklandığı gibi şu anda yürütülen etkinlik bildirimi vurgulanır ve izleme kayıtları uygulama penceresinin sağ tarafında görüntülenir.

6. İş akışı tamamlandığında, herhangi bir karşılık hangi etkinlik incelemek için izleme kayıtları tıklayabilirsiniz.

> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü. Devam etmeden önce şu (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek, şu dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\VisualWorkflowTracking`
