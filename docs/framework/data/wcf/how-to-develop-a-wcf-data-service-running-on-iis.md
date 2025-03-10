---
title: 'Nasıl yapılır: IIS üzerinde çalışan bir WCF Veri Hizmeti Geliştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: d03a0ae3bc84106d72803b22050a7c75a037be12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780103"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Nasıl yapılır: IIS üzerinde çalışan bir WCF veri hizmeti geliştirme

Bu konu, Internet Information Services (IIS) üzerinde çalışan bir ASP.NET Web uygulaması tarafından barındırılan Northwind örnek veritabanına dayalı bir veri hizmeti oluşturmak için WCF Veri Hizmetleri nasıl kullanacağınızı gösterir. ASP.NET geliştirme sunucusunda çalışan bir ASP.NET Web uygulaması olarak aynı Northwind Data Service 'in nasıl oluşturulacağı hakkında bir örnek için [WCF veri hizmetleri hızlı başlangıç](quickstart-wcf-data-services.md)bölümüne bakın.

> [!NOTE]
> Northwind veri hizmetini oluşturmak için, yerel bilgisayara Northwind örnek veritabanını yüklemiş olmanız gerekir. Bu örnek veritabanını indirmek için indirme sayfasına, [SQL Server Için örnek veritabanlarına](https://go.microsoft.com/fwlink/?linkid=24758)bakın.

Bu konuda, Entity Framework sağlayıcısı kullanılarak bir veri hizmetinin nasıl oluşturulacağı gösterilmektedir. Diğer veri hizmetleri sağlayıcıları kullanılabilir. Daha fazla bilgi için bkz. [veri hizmetleri sağlayıcıları](data-services-providers-wcf-data-services.md).

Hizmeti oluşturduktan sonra, veri hizmeti kaynaklarına açıkça erişim sağlamanız gerekir. Daha fazla bilgi için [nasıl yapılır: Veri hizmetine](how-to-enable-access-to-the-data-service-wcf-data-services.md)erişimi etkinleştirin.

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a>IIS üzerinde çalışan ASP.NET Web uygulaması oluşturma

1. Visual Studio 'da, **Dosya** menüsünde **Yeni** > **Proje**' yi seçin.

2. **Yeni proje** iletişim kutusunda, **yüklü** > [ **C# Visual** veya **Visual Basic**] > **Web** kategorisini seçin.

3. **ASP.NET Web uygulaması** şablonunu seçin.

4. Projenin `NorthwindService` adı olarak girin.

5. **Tamam**'ı tıklatın.

6. **Proje** menüsünde, **NorthwindService özellikleri**' ni seçin.

7. **Web** sekmesini seçin ve ardından **yerel IIS Web sunucusu kullan**' ı seçin.

8. **Sanal dizin oluştur** ' a ve ardından **Tamam**' a tıklayın.

9. Komut isteminden yönetici ayrıcalıklarıyla, aşağıdaki komutlardan birini yürütün (işletim sistemine bağlı olarak):

    - 32 bit sistemler:

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - 64 bit sistemler:

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     Bu, Windows Communication Foundation (WCF) bilgisayarda kayıtlı olduğundan emin olmanızı sağlar.

10. Komut isteminden yönetici ayrıcalıklarıyla, aşağıdaki komutlardan birini yürütün (işletim sistemine bağlı olarak):

    - 32 bit sistemler:

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - 64 bit sistemler:

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     Bu, bilgisayarda WCF yüklendikten sonra IIS 'nin düzgün şekilde çalıştığından emin olmanızı sağlar. Ayrıca IIS 'yi de yeniden başlatmanız gerekebilir.

11. ASP.NET uygulaması ııS7 üzerinde çalıştığında, aşağıdaki adımları da gerçekleştirmeniz gerekir:

    1. IIS Yöneticisi 'Ni açın ve **varsayılan Web sitesi**altında photoservice uygulamasına gidin.

    2. **Özellikler Görünümü**' nde, **kimlik doğrulaması**' na çift tıklayın.

    3. **Kimlik doğrulama** sayfasında, **anonim kimlik doğrulaması**' nı seçin.

    4. **Eylemler** bölmesinde, anonim kullanıcıların siteye bağlanacağı güvenlik sorumlusunu ayarlamak için **Düzenle** ' ye tıklayın.

    5. **Anonim kimlik doğrulaması kimlik bilgilerini düzenle** Iletişim kutusunda **uygulama havuzu kimliği**' ni seçin.

    > [!IMPORTANT]
    > Ağ hizmeti hesabı 'nı kullandığınızda, anonim kullanıcılara bu hesapla ilişkili tüm iç ağ erişimini vermiş olursunuz.

12. Visual Studio 'daki SQL Server Management Studio, sqlcmd. exe yardımcı programını veya Transact-SQL düzenleyicisini kullanarak, Northwind veritabanının eklendiği SQL Server örneğine karşı aşağıdaki Transact-SQL komutunu yürütün:

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    Bu, IIS çalıştırmak için kullanılan Windows hesabının SQL Server örneğinde bir oturum açma oluşturur. Bu, IIS 'nin SQL Server örneğine bağlanmasını sağlar.

13. Northwind veritabanı ekli olarak, aşağıdaki Transact-SQL komutlarını yürütün:

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    Bu, yeni oturum açma haklarına izin verir ve bu da IIS 'nin Northwind veritabanına verileri okumasını ve verileri yazmasını sağlar.

## <a name="define-the-data-model"></a>Veri modelini tanımlama

1. **Çözüm Gezgini**, ASP.net projesinin adına sağ tıklayın ve ardından**Yeni öğe** **Ekle** > ' ye tıklayın.

2. **Yeni öğe Ekle** iletişim kutusunda **ADO.net varlık veri modeli**' yi seçin.

3. Veri modeli adı için, yazın `Northwind.edmx`.

4. Varlık Veri Modeli sihirbazında, **veritabanından oluştur**' u seçin ve ardından **İleri**' ye tıklayın.

5. Aşağıdaki adımlardan birini gerçekleştirerek veri modelini veritabanına bağlayın ve ardından **İleri**' ye tıklayın:

    - Zaten yapılandırılmış bir veritabanı bağlantınız yoksa **Yeni bağlantı** ' ya tıklayın ve yeni bir bağlantı oluşturun. Daha fazla bilgi için [nasıl yapılır: SQL Server veritabanlarına](https://go.microsoft.com/fwlink/?LinkId=123631)bağlantı oluşturun. Bu SQL Server örneğine Northwind örnek veritabanının eklenmiş olması gerekir.

         \- veya -

    - Northwind veritabanına bağlanmak için zaten yapılandırılmış bir veritabanı bağlantınız varsa, bağlantı listesinden bu bağlantıyı seçin.

6. Sihirbazın son sayfasında, veritabanındaki tüm tablolar için onay kutularını seçin ve görünümler ve saklı yordamlar onay kutularını temizleyin.

7. Sihirbazı kapatmak için **son** ' a tıklayın.

## <a name="create-the-data-service"></a>Veri hizmetini oluşturma

1. **Çözüm Gezgini**, ASP.net projenizin adına sağ tıklayın ve ardından**Yeni öğe** **Ekle** > ' ye tıklayın.

2. **Yeni öğe Ekle** iletişim kutusunda, **WCF veri hizmeti**' ni seçin.

   ![Visual Studio 2015 ' de WCF veri hizmeti öğe şablonu](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > **WCF veri hizmeti** şablonu visual Studio 2015 'de kullanılabilir, ancak visual Studio 2017 ' de kullanılamaz.

3. Hizmetin adı için girin `Northwind`.

     Visual Studio, yeni hizmet için XML işaretlemesini ve kod dosyalarını oluşturur. Varsayılan olarak, kod Düzenleyicisi penceresi açılır. **Çözüm Gezgini**, hizmetin adı, Northwind ve uzantısı. svc.cs veya. svc. vb ' dir.

4. Veri Hizmeti kodunda, veri hizmetini tanımlayan sınıfın tanımındaki, bu `/* TODO: put your data source class name here */` örnekte olduğu `NorthwindEntities`gibi veri modelinin varlık kapsayıcısı olan türde olan açıklamayı değiştirin. Sınıf tanımı aşağıdaki gibi görünmelidir:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a>Ayrıca bkz.

- [Verilerinizi Hizmet Olarak Kullanıma Sunma](exposing-your-data-as-a-service-wcf-data-services.md)
