---
title: 'Nasıl yapılır: Hizmet Bilgilerini Günlüğe Kaydetme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoLog property
- services, logging information
- Windows Service applications, logging information about
- event logs, service applications
- application event logs, service applications
- logs, service applications
ms.assetid: c0d8140f-c055-4d8e-a2e0-37358a550116
author: ghogen
ms.openlocfilehash: 1ffc698910fe722fe761c62b87b059068d5f243f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935517"
---
# <a name="how-to-log-information-about-services"></a>Nasıl yapılır: Hizmet Bilgilerini Günlüğe Kaydetme
Varsayılan olarak, tüm Windows hizmeti projelerinin uygulama olay günlüğü ile etkileşim kurma ve bu bilgilere yazma bilgileri ve özel durumları vardır. Uygulamanızda bu işlevselliği <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> isteyip istemediğinizi belirtmek için özelliğini kullanın. Varsayılan olarak, Windows hizmeti proje şablonuyla oluşturduğunuz her hizmet için günlük kaydı açıktır. Bir <xref:System.Diagnostics.EventLog> bileşenin örneğini oluşturmak veya bir kaynağı el <xref:System.Diagnostics.EventLog> ile kaydetmek zorunda kalmadan hizmet bilgilerini bir günlüğe yazmak için sınıfının statik bir biçimini kullanabilirsiniz.  
  
 Hizmetiniz için yükleyici, günlük kaydı açık olduğunda, hizmetin yüklendiği bilgisayardaki uygulama günlüğü ile projenizdeki her hizmeti otomatik olarak geçerli bir olay kaynağı olarak kaydeder. Hizmetin başlatıldığı, durdurulduğu, duraklatıldığı, kaldığı, yüklendiği veya kaldırıldığı her seferinde hizmet bilgileri günlüğe kaydedilir. Ayrıca oluşan tüm sorunları günlüğe kaydeder. Varsayılan davranışı kullanırken günlüğe giriş yazmak için herhangi bir kod yazmanız gerekmez; hizmet bunu sizin için otomatik olarak işler.  
  
 Uygulama günlüğü dışında bir olay günlüğüne yazmak isterseniz, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> özelliği olarak `false`ayarlamanız, hizmet kodunuzda kendi özel olay günlüğlerinizi oluşturmanız ve hizmetinizi bu günlük için geçerli bir giriş kaynağı olarak kaydetmeniz gerekir. Ardından, ilgilendiğiniz bir eylem olduğunda günlüğe girdileri kaydetmek için kod yazmalısınız.  
  
> [!NOTE]
> Özel bir olay günlüğü kullanır ve hizmet uygulamanızı ona yazacak şekilde yapılandırırsanız, kodunuzda hizmetin <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> özelliğini ayarlamadan önce olay günlüğüne erişmeye çalışmamalıdır. Olay günlüğü, hizmetinizi geçerli bir olay kaynağı olarak kaydetmek için bu özelliğin değerine ihtiyaç duyuyor.  
  
### <a name="to-enable-default-event-logging-for-your-service"></a>Hizmetiniz için varsayılan olay günlüğünü etkinleştirmek için  
  
- Bileşeninizin `true`özelliğini olarak ayarlayın. <xref:System.ServiceProcess.ServiceBase.AutoLog%2A>  
  
    > [!NOTE]
    > Varsayılan olarak, bu özellik olarak `true`ayarlanır. Bir koşulu değerlendirme ve sonra <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> özelliği bu koşulun sonucuna göre ayarlama gibi daha karmaşık bir işlem oluşturulmadığınız sürece bunu açıkça ayarlamanız gerekmez.  
  
### <a name="to-disable-event-logging-for-your-service"></a>Hizmetiniz için olay günlüğünü devre dışı bırakmak için  
  
- Bileşeninizin `false`özelliğini olarak ayarlayın. <xref:System.ServiceProcess.ServiceBase.AutoLog%2A>  
  
     [!code-csharp[VbRadconService#17](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#17)]
     [!code-vb[VbRadconService#17](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#17)]  
  
### <a name="to-set-up-logging-to-a-custom-log"></a>Özel bir günlüğe günlük kaydı ayarlamak için  
  
1. Ayarlama <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> özelliğini `false`.  
  
    > [!NOTE]
    > Özel bir günlük <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> kullanabilmeniz için false olarak ayarlamanız gerekir.  
  
2. Windows hizmet uygulamanızda bir <xref:System.Diagnostics.EventLog> bileşen örneği ayarlayın.  
  
3. <xref:System.Diagnostics.EventLog.CreateEventSource%2A> Yöntemini çağırarak ve kaynak dizeyi ve oluşturmak istediğiniz günlük dosyasının adını belirterek özel bir günlük oluşturun.  
  
4. <xref:System.Diagnostics.EventLog> Bileşen örneğindeki <xref:System.Diagnostics.EventLog.Source%2A> özelliği adım 3 ' te oluşturduğunuz kaynak dizeye ayarlayın.  
  
5. <xref:System.Diagnostics.EventLog> Bileşen örneğindeki <xref:System.Diagnostics.EventLog.WriteEntry%2A> yöntemine erişerek girdilerinizi yazın.  
  
     Aşağıdaki kod, özel bir günlüğe kaydetmenin nasıl ayarlanacağını gösterir.  
  
    > [!NOTE]
    > Bu kod örneğinde, bir <xref:System.Diagnostics.EventLog> bileşenin örneği (`EventLog1` Visual Basic) olarak adlandırılır `eventLog1` . 2\. adımda başka bir ada sahip bir örnek oluşturduysanız, kodu uygun şekilde değiştirin.  
  
     [!code-csharp[VbRadconService#14](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#14)]
     [!code-vb[VbRadconService#14](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#14)]  
    [!code-csharp[VbRadconService#15](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#15)]
    [!code-vb[VbRadconService#15](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#15)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Windows Hizmeti Uygulamalarına Giriş](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
