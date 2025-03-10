---
title: SQL İzleme
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 24cc484bf11d7cedab949d61c63f805a28a9f849
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038065"
---
# <a name="sql-tracking"></a>SQL İzleme
Bu örnek, izleme kayıtlarını bir SQL veritabanına yazan özel bir SQL izleme katılımcısının nasıl yazılacağını gösterir. Windows Workflow Foundation (WF), bir iş akışı örneğinin yürütülmesi için görünürlük elde etmek üzere iş akışı izleme sağlar. İzleme çalışma zamanı, iş akışının yürütülmesi sırasında iş akışı izleme kayıtlarını yayar. İş akışı izleme hakkında daha fazla bilgi için bkz. [Iş akışı izleme ve izleme](../workflow-tracking-and-tracing.md).

#### <a name="to-use-this-sample"></a>Bu örneği kullanmak için

1. SQL Server 2008, SQL Server 2008 Express veya daha yeni bir sürümün yüklü olduğunu doğrulayın. Örnekle paketlenmiş betikler, yerel bilgisayarınızda bir SQL Express örneği kullanımını varsayar. Farklı bir örneğiniz varsa, örneği çalıştırmadan önce lütfen veritabanıyla ilgili betikleri değiştirin.

2. Betikler dizinindeki Trackingsetup. cmd ' i çalıştırarak SQL Server izleme veritabanını oluşturun (\Wf\basic\izlemedosyası \ KomutDosyaları). Bu, TrackingSample adlı bir veritabanı oluşturur.

    > [!NOTE]
    > Betik, SQL Express 'in varsayılan örneğinde veritabanını oluşturur. Farklı bir veritabanı örneğine yüklemek isterseniz, Trackingsetup. cmd betiğini düzenleyin.  
  
3. Visual Studio 2010 ' de SqlTrackingSample. sln dosyasını açın.  
  
4. Çözümü derlemek için CTRL + SHIFT + B tuşlarına basın.  
  
5. Uygulamayı çalıştırmak için F5'e basın.  
  
     Tarayıcı penceresi açılır ve uygulamanın dizin listesini gösterir.  
  
6. Tarayıcıda, StockPriceService. xamlx ' ye tıklayın.  
  
7. Tarayıcı, yerel hizmet WSDL adresini içeren StockPriceService sayfasını görüntüler. Bu adresi kopyalayın.  
  
     Yerel hizmet WSDL adresi `http://localhost:65193/StockPriceService.xamlx?wsdl`örneği.  
  
8. Dosya Gezgini 'ni kullanarak WCF test istemcisini (WcfTestClient. exe) çalıştırın. Microsoft Visual Studio 10.0 \ Common7\ıde dizininde bulunur.  
  
9. WCF test istemcisinde **Dosya** menüsüne tıklayın ve **Hizmet Ekle**' yi seçin. Yerel hizmet adresini metin kutusuna yapıştırın. İletişim kutusunu kapatmak için **Tamam** ' ı tıklatın.  
  
10. WCF test istemcisinde **GetStockPrice**' ye çift tıklayın. Bu `GetStockPrice` işlem bir parametre alan işlemi açar, değeri `Contoso` yazın ve **çağır**' a tıklayın.  
  
11. Yayınlanan izleme kayıtları bir SQL veritabanına yazılır. İzleme kayıtlarını görüntülemek için, SQL Management Studio 'de TrackingSample veritabanını açın ve tablolara gidin. SQL Server Management Studio hakkında daha fazla bilgi için bkz. [SQL Server Management Studio tanıtımı](https://go.microsoft.com/fwlink/?LinkId=165645). SQL Server 2008 Management Studio Express [buradan](https://go.microsoft.com/fwlink/?LinkId=180520)indirilebilir. Tablolarda bir SELECT sorgusu çalıştırmak, ilgili tablolarda depolanan izleme kayıtları içindeki verileri görüntüler.  
  
#### <a name="to-uninstall-the-sample"></a>Örneği kaldırmak için  
  
1. Örnek dizininde theTrackingcleanup. cmd betiğini çalıştırın (\Wf\basic\izlemesqltracking).  
  
    > [!NOTE]
    > Trackingcleanup. cmd yerel bilgisayarınızdaki SQL Express veritabanını silmeye çalışır. Başka bir SQL Server örneği kullanıyorsanız, Trackingcleanup. cmd ' yi düzenleyin.

> [!IMPORTANT]
> Örnekler bilgisayarınızda zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizini denetleyin.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Bu dizin yoksa, tüm Windows Communication Foundation (WCF) ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri indirmek için [Windows Communication Foundation (WCF) ve Windows Workflow Foundation (WF) örneklerine .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) ' e gidin. Bu örnek, aşağıdaki dizinde bulunur.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a>Ayrıca bkz.

- [AppFabric Izleme örnekleri](https://go.microsoft.com/fwlink/?LinkId=193959)
