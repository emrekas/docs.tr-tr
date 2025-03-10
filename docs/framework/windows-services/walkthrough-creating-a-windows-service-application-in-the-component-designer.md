---
title: 'Öğretici: Windows hizmet uygulaması oluşturma'
ms.date: 03/27/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
ms.openlocfilehash: df2a99b6fe288cfa8b8a5d60bb127849323ed3a9
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545313"
---
# <a name="tutorial-create-a-windows-service-app"></a>Öğretici: Windows hizmet uygulaması oluşturma

Bu makalede, Visual Studio 'da bir olay günlüğüne ileti yazan bir Windows hizmet uygulamasının nasıl oluşturulacağı gösterilmektedir.

## <a name="create-a-service"></a>Bir hizmet oluşturma

Başlamak için projeyi oluşturun ve hizmetin düzgün çalışması için gereken değerleri ayarlayın.

1. Visual Studio **Dosya** menüsünden **Yeni** > **Proje** ' yi seçin (veya **CTRL**+**SHIFT**+**N**tuşlarına basarak) **Yeni proje** penceresini açın.

2. ' A gidin ve **Windows hizmeti (.NET Framework)** proje şablonunu seçin. Bunu bulmak için, **yüklü** ve **Visual C#**  veya **Visual Basic**' i genişletin ve **Windows Masaüstü**' nü seçin. Ya da, sağ üst köşedeki arama kutusuna *Windows hizmeti* girip **ENTER**tuşuna basın.

   ![Visual Studio 'da yeni proje iletişim kutusunda Windows hizmet şablonu](media/new-project-dialog.png)

   > [!NOTE]
   > **Windows hizmet** şablonunu görmüyorsanız, **.net masaüstü geliştirme** iş yükünü yüklemeniz gerekebilir:
   >
   > **Yeni proje** iletişim kutusunda sol alttaki **Visual Studio yükleyicisi aç** ' ı seçin. **.Net masaüstü geliştirme** iş yükünü seçin ve ardından **Değiştir**' i seçin.

3. **Ad**için *MyNewService*yazın ve ardından **Tamam**' ı seçin.

   **Tasarım** sekmesi görünür (**Service1.cs [Design]** veya **Service1. vb [Design]** ).

   Proje şablonu, öğesinden `Service1` <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>devralan adlı bir bileşen sınıfı içerir. Bu, hizmeti başlatmak için kod gibi temel hizmet kodunun çoğunu içerir.

## <a name="rename-the-service"></a>Hizmeti yeniden adlandırma

Hizmeti **Service1** iken **MyNewService**olarak yeniden adlandırın.

1. **Çözüm Gezgini**' de, **Service1.cs**veya **Service1. vb**öğesini seçin ve kısayol menüsünden **Yeniden Adlandır** ' ı seçin. Dosyayı **MyNewService.cs**veya **MyNewService. vb**olarak yeniden adlandırın ve ardından **ENTER** tuşuna basın

    Kod öğesi *Service1*için tüm başvuruları yeniden adlandırmak isteyip istemediğinizi soran bir açılır pencere görüntülenir.

2. Açılır pencerede **Evet**' i seçin.

    ![Yeniden adlandırma istemi](media/windows-service-rename.png "Windows hizmeti yeniden adlandırma istemi")

3. **Tasarım** sekmesinde, kısayol menüsünden **Özellikler** ' i seçin. **Özellikler** penceresinde **ServiceName** değerini *MyNewService*olarak değiştirin.

    ![Hizmet özellikleri](media/windows-service-properties.png "Windows hizmeti özellikleri")

4. **Dosya** menüsünden **Tümünü Kaydet** ' i seçin.

## <a name="add-features-to-the-service"></a>Hizmete özellikler ekleme

Bu bölümde, Windows hizmetine özel bir olay günlüğü eklersiniz. <xref:System.Diagnostics.EventLog> Bileşen, bir Windows hizmetine ekleyebileceğiniz bileşen türüne bir örnektir.

### <a name="add-custom-event-log-functionality"></a>Özel olay günlüğü işlevselliği Ekle

1. **Çözüm Gezgini**, **MyNewService.cs**Için kısayol menüsünden veya **MyNewService. vb**' de **Görünüm Tasarımcısı**' nı seçin.

2. **Araç kutusu**' nda **Bileşenler**' i genişletin ve ardından **EventLog** bileşenini **Service1.cs [Design]** veya **Service1. vb [Design]** sekmesine sürükleyin.

3. **Çözüm Gezgini**' de, **MyNewService.cs**veya **MyNewService. vb**kısayol menüsünde **kodu görüntüle**' yi seçin.

4. Özel bir olay günlüğü tanımlayın. İçin C#, var olan `MyNewService()` oluşturucuyu düzenleyin; `New()` Visual Basic için oluşturucuyu ekleyin:

   [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

5. <xref:System.Diagnostics?displayProperty=nameWithType> `Imports` Ad alanı için, **MyNewService.cs** (henüz yoksa) veya **MyNewService. vb**ifadesini ekleyin: `using`

    ```csharp
    using System.Diagnostics;
    ```

    ```vb
    Imports System.Diagnostics
    ```

6. **Dosya** menüsünden **Tümünü Kaydet** ' i seçin.

### <a name="define-what-occurs-when-the-service-starts"></a>Hizmet başladığında ne olduğunu tanımlayın

**MyNewService.cs** veya **MyNewService. vb**için kod düzenleyicisinde, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> yöntemini bulun; Projeyi oluştururken Visual Studio otomatik olarak boş bir yöntem tanımı oluşturdu. Hizmet başladığında bir girişi olay günlüğüne yazan kodu ekleyin:

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

#### <a name="polling"></a>Masını

Bir hizmet uygulaması uzun süre çalışan olacak şekilde tasarlandığından, genellikle <xref:System.ServiceProcess.ServiceBase.OnStart%2A> yönteminde ayarladığınız sistemi yoklar veya izler. Sistemin engellenmemesi için hizmetin işlemi başladıktan sonra yöntemiişletimsisteminedöndürmelidir.`OnStart`

Basit bir yoklama mekanizması ayarlamak için <xref:System.Timers.Timer?displayProperty=nameWithType> bileşenini kullanın. Süreölçer, düzenli aralıklarla <xref:System.Timers.Timer.Elapsed> bir olay oluşturur ve bu süre, hizmetiniz kendi izlemesini gerçekleştirebilir. <xref:System.Timers.Timer> Bileşeni aşağıdaki gibi kullanırsınız:

- Yöntemi içindeki bileşenin<xref:System.Timers.Timer> özelliklerini ayarlayın. `MyNewService.OnStart`
- <xref:System.Timers.Timer.Start%2A> Yöntemini çağırarak Zamanlayıcıyı başlatın.

##### <a name="set-up-the-polling-mechanism"></a>Yoklama mekanizmasını ayarlayın.

1. Yoklama mekanizmasını ayarlamak için `MyNewService.OnStart` olaya aşağıdaki kodu ekleyin:

   ```csharp
   // Set up a timer that triggers every minute.
   Timer timer = new Timer();
   timer.Interval = 60000; // 60 seconds
   timer.Elapsed += new ElapsedEventHandler(this.OnTimer);
   timer.Start();
   ```

   ```vb
   ' Set up a timer that triggers every minute.
   Dim timer As Timer = New Timer()
   timer.Interval = 60000 ' 60 seconds
   AddHandler timer.Elapsed, AddressOf Me.OnTimer
   timer.Start()
   ```

2. <xref:System.Timers?displayProperty=nameWithType> Ad alanı `using` için **MyNewService.cs**veya bir `Imports` deyime, **MyNewService. vb**öğesine bir ifade ekleyin:

   ```csharp
   using System.Timers;
   ```

   ```vb
   Imports System.Timers
   ```

3. Sınıfında, olayı<xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType> işleyecek `OnTimer`yöntemiekleyin: `MyNewService`

   ```csharp
   public void OnTimer(object sender, ElapsedEventArgs args)
   {
       // TODO: Insert monitoring activities here.
       eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId++);
   }
   ```

   ```vb
   Private Sub OnTimer(sender As Object, e As Timers.ElapsedEventArgs)
      ' TODO: Insert monitoring activities here.
      eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId)
      eventId = eventId + 1
   End Sub
   ```

4. `MyNewService` Sınıfında bir üye değişkeni ekleyin. Olay günlüğüne yazılacak bir sonraki olayın tanımlayıcısını içerir:

   ```csharp
   private int eventId = 1;
   ```

   ```vb
   Private eventId As Integer = 1
   ```

Tüm çalışmalarınızı ana iş parçacığında çalıştırmak yerine, arka plan çalışan iş parçacıklarını kullanarak görevleri çalıştırabilirsiniz. Daha fazla bilgi için bkz. <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.

### <a name="define-what-occurs-when-the-service-is-stopped"></a>Hizmet durdurulduğunda ne olduğunu tanımlayın

Hizmet durdurulduğunda olay günlüğüne bir girdi ekleyen <xref:System.ServiceProcess.ServiceBase.OnStop%2A> yönteme bir kod satırı ekleyin:

[!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a>Hizmet için diğer eylemleri tanımlayın

Bileşeniniz için ek <xref:System.ServiceProcess.ServiceBase.OnPause%2A>işlem <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>tanımlamak üzere <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> ,, ve yöntemlerini geçersiz kılabilirsiniz.

Aşağıdaki kod, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> `MyNewService` sınıfındaki yöntemini nasıl geçersiz kılabileceğiniz gösterilmektedir:

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

## <a name="set-service-status"></a>Hizmet durumunu ayarla

Hizmetler, bir kullanıcının bir hizmetin doğru çalışıp çalışmadığını anlayabilmesi için durumlarını [hizmet denetimi yöneticisine](/windows/desktop/Services/service-control-manager) bildirir. Varsayılan olarak, SERVICE_STOPPED, SERVICE_PAUSED ve SERVICE_RUNNING <xref:System.ServiceProcess.ServiceBase> içeren sınırlı bir durum ayarları kümesi raporlarından devralan bir hizmettir. Bir hizmetin başlatılması biraz zaman alıyorsa, SERVICE_START_PENDING durumunu raporlamak yararlı olur.

Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) işlevini çağıran kodu ekleyerek SERVICE_START_PENDING ve SERVICE_STOP_PENDING durum ayarlarını uygulayabilirsiniz.

### <a name="implement-service-pending-status"></a>Hizmet bekleme durumunu Uygula

1. <xref:System.Runtime.InteropServices?displayProperty=nameWithType> Ad alanı `using` için **MyNewService.cs**veya bir `Imports` deyime, **MyNewService. vb**öğesine bir ifade ekleyin:

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. `ServiceState` Değerleri bildirmek ve bir platform çağırma çağrısında kullanacağınız durum için bir yapı eklemek üzere **MyNewService.cs**veya **MyNewService. vb**' ye aşağıdaki kodu ekleyin:

    ```csharp
    public enum ServiceState
    {
        SERVICE_STOPPED = 0x00000001,
        SERVICE_START_PENDING = 0x00000002,
        SERVICE_STOP_PENDING = 0x00000003,
        SERVICE_RUNNING = 0x00000004,
        SERVICE_CONTINUE_PENDING = 0x00000005,
        SERVICE_PAUSE_PENDING = 0x00000006,
        SERVICE_PAUSED = 0x00000007,
    }

    [StructLayout(LayoutKind.Sequential)]
    public struct ServiceStatus
    {
        public int dwServiceType;
        public ServiceState dwCurrentState;
        public int dwControlsAccepted;
        public int dwWin32ExitCode;
        public int dwServiceSpecificExitCode;
        public int dwCheckPoint;
        public int dwWaitHint;
    };
    ```

    ```vb
    Public Enum ServiceState
        SERVICE_STOPPED = 1
        SERVICE_START_PENDING = 2
        SERVICE_STOP_PENDING = 3
        SERVICE_RUNNING = 4
        SERVICE_CONTINUE_PENDING = 5
        SERVICE_PAUSE_PENDING = 6
        SERVICE_PAUSED = 7
    End Enum

    <StructLayout(LayoutKind.Sequential)>
    Public Structure ServiceStatus
        Public dwServiceType As Long
        Public dwCurrentState As ServiceState
        Public dwControlsAccepted As Long
        Public dwWin32ExitCode As Long
        Public dwServiceSpecificExitCode As Long
        Public dwCheckPoint As Long
        Public dwWaitHint As Long
    End Structure
    ```

    > [!NOTE]
    > Hizmet denetimi Yöneticisi, bir Windows `dwWaitHint` hizmetinin `dwCheckpoint` başlaması veya kapatılması için ne kadar süre bekleneceğini öğrenmek için [SERVICE_STATUS yapısının](/windows/win32/api/winsvc/ns-winsvc-service_status) ve üyelerini kullanır. Ve `OnStart` `SetServiceStatus` `dwCheckPoint` yöntemleriniz uzun bir süre çalışıyorsa, hizmetiniz arttırılan bir değerle tekrar çağırarak daha fazla zaman isteğinde bulunabilir. `OnStop`

3. Sınıfında, [Platform Invoke](../interop/consuming-unmanaged-dll-functions.md)kullanarak [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) işlevini bildirin: `MyNewService`

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. SERVICE_START_PENDING durumunu uygulamak için, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> yönteminin başına aşağıdaki kodu ekleyin:

    ```csharp
    // Update the service state to Start Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Start Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

5. Durumu SERVICE_RUNNING olarak ayarlamak için `OnStart` yönteminin sonuna kod ekleyin:

    ```csharp
    // Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

6. Seçim Uzun süre çalışan bir yöntem ise, `OnStop` yöntemi içinde bu yordamı tekrarlayın. <xref:System.ServiceProcess.ServiceBase.OnStop%2A> SERVICE_STOP_PENDING durumunu uygulayın ve `OnStop` yöntemin çıkış yapmadan önce SERVICE_STOPPED durumunu döndürün.

   Örneğin:

    ```csharp
    // Update the service state to Stop Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);

    // Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Stop Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)

    ' Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

## <a name="add-installers-to-the-service"></a>Hizmete yükleyiciler ekleme

Bir Windows hizmetini çalıştırmadan önce, onu yüklemeniz gerekir, bunu hizmet denetimi Yöneticisi ile kaydeder. Kayıt ayrıntılarını işlemek için projenize yükleyiciler ekleyin.

1. **Çözüm Gezgini**, **MyNewService.cs**Için kısayol menüsünden veya **MyNewService. vb**' de **Görünüm Tasarımcısı**' nı seçin.

2. **Tasarım** görünümünde, arka plan alanını seçin, sonra kısayol menüsünden **Yükleyici Ekle** ' yi seçin.

     Varsayılan olarak, Visual Studio projenize iki yükleyici içeren adlı `ProjectInstaller`bir bileşen sınıfı ekler. Bu yükleyiciler hizmetinize ve hizmetin ilişkili sürecine yöneliktir.

3. **ProjectInstaller**için **Tasarım** görünümünde, bir görsel C# proje Için **Serviceınstaller1 & lt** veya Visual Basic projesi için **Serviceınstaller1 & lt** ' i seçin, sonra kısayol menüsünden **Özellikler** ' i seçin.

4. **Özellikler** penceresinde, <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> özelliğin **MyNewService**olarak ayarlandığını doğrulayın.

5. <xref:System.ServiceProcess.ServiceInstaller.Description%2A> Özelliğe *örnek bir hizmet*gibi metin ekleyin.

     Bu metin, **Hizmetler** penceresinin **Açıklama** sütununda görüntülenir ve kullanıcıya hizmeti açıklar.

    ![Hizmetler penceresinde hizmet açıklaması.](media/windows-service-description.png "Hizmet açıklaması")

6. <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> Özelliğe metin ekleyin. Örneğin, *MyNewService görünen adı*.

     Bu metin, **Hizmetler** penceresinin **görünen ad** sütununda görünür. Bu ad, sistem tarafından kullanılan ad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> (örneğin, hizmetinizi başlatmak için kullandığınız `net start` ad) özelliğinden farklı olabilir.

7. Özelliğini, <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> açılan listeden <xref:System.ServiceProcess.ServiceStartMode.Automatic> olarak ayarlayın.

8. İşiniz bittiğinde, **Özellikler** penceresi aşağıdaki şekilde görünmelidir:

     ![Windows hizmeti Için yükleyici özellikleri](media/windows-service-installer-properties.png "Windows hizmeti yükleyicisi özellikleri")

9. **ProjectInstaller**için **Tasarım** görünümünde, bir görsel C# proje Için **Serviceprocessınstaller1** veya Visual Basic projesi için **Serviceprocessınstaller1** ' i seçin, sonra kısayol menüsünden **Özellikler** ' i seçin. . Özelliğini, <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> açılan listeden <xref:System.ServiceProcess.ServiceAccount.LocalSystem> olarak ayarlayın.

     Bu ayar hizmeti yükleyip yerel sistem hesabını kullanarak çalıştırır.

    > [!IMPORTANT]
    > <xref:System.ServiceProcess.ServiceAccount.LocalSystem> Hesabın, olay günlüğüne yazma özelliği de dahil olmak üzere geniş izinleri vardır. Bu hesabı kullanırken dikkatli olun; kötü amaçlı yazılımlardan gelecek saldırı riskinizi arttırabilir. Diğer görevler için, yerel bilgisayarda ayrıcalıklı <xref:System.ServiceProcess.ServiceAccount.LocalService> olmayan bir kullanıcı olarak davranan ve herhangi bir uzak sunucuya anonim kimlik bilgileri sunan hesabı kullanmayı göz önünde bulundurun. Bu örnek, <xref:System.ServiceProcess.ServiceAccount.LocalService> hesap günlüğüne yazmak için izin gerektiğinden hesabı kullanmayı denerseniz başarısız olur.

Yükleyiciler hakkında daha fazla bilgi için bkz [. nasıl yapılır: Hizmet uygulamanıza](how-to-add-installers-to-your-service-application.md)yükleyicileri ekleyin.

## <a name="optional-set-startup-parameters"></a>Seçim Başlangıç parametrelerini ayarla

> [!NOTE]
> Başlangıç parametrelerini eklemeye karar vermeden önce, hizmetinize bilgileri iletmenin en iyi yolu olup olmadığını göz önünde bulundurun. Kullanımı ve ayrıştırma kolaysa da, bir kullanıcı bunları kolayca geçersiz kılabilir, ancak kullanıcıların belge olmadan bulması ve kullanması daha zor olabilir. Genel olarak, hizmetiniz yalnızca birkaç başlangıç parametresi gerektiriyorsa, bunun yerine kayıt defteri veya yapılandırma dosyası kullanmanız gerekir.

Windows hizmeti komut satırı bağımsız değişkenlerini veya başlangıç parametrelerini kabul edebilir. Başlangıç parametrelerini işlemek için kod eklediğinizde, bir Kullanıcı Hizmeti Özellikler penceresinde kendi özel başlangıç parametreleriyle hizmetinizi başlatabilir. Ancak, bu başlangıç parametreleri hizmetin bir sonraki başlatılışında kalıcı olmaz. Başlangıç parametrelerini kalıcı olarak ayarlamak için kayıt defterinde ayarlayın.

Her bir Windows hizmetinin, **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services** alt anahtarında bir kayıt defteri girişi vardır. Her bir hizmetin alt anahtarı altında, hizmetinizin erişebileceği bilgileri depolamak için **Parameters** alt anahtarını kullanın. Windows hizmeti için uygulama yapılandırma dosyalarını, diğer tür programlar için yaptığınız şekilde kullanabilirsiniz. Örnek kod için bkz <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.

### <a name="to-add-startup-parameters"></a>Başlangıç parametreleri eklemek için

1. **Program.cs**veya **MyNewService. Designer. vb**öğesini seçin, ardından kısayol menüsünde **kodu görüntüle** ' yi seçin. `Main` Yönteminde, bir giriş parametresi eklemek ve onu Service yapıcısına iletmek için kodu değiştirin:

   [!code-csharp[VbRadconService](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/Program-add-parameter.cs?highlight=1,6)]
   [!code-vb[VbRadconService](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.Designer-add-parameter.vb?highlight=1-2)]

2. **MyNewService.cs**veya **MyNewService. vb** `MyNewService` ' de, Oluşturucu giriş parametresini aşağıdaki gibi işleyecek şekilde değiştirin:

   ```csharp
   using System.Diagnostics;

   public MyNewService(string[] args)
   {
       InitializeComponent();

       string eventSourceName = "MySource";
       string logName = "MyNewLog";

       if (args.Length > 0)
       {
          eventSourceName = args[0];
       }

       if (args.Length > 1)
       {
           logName = args[1];
       }

       eventLog1 = new EventLog();

       if (!EventLog.SourceExists(eventSourceName))
       {
           EventLog.CreateEventSource(eventSourceName, logName);
       }

       eventLog1.Source = eventSourceName;
       eventLog1.Log = logName;
   }
   ```

   ```vb
   Imports System.Diagnostics

   Public Sub New(ByVal cmdArgs() As String)
       InitializeComponent()
       Dim eventSourceName As String = "MySource"
       Dim logName As String = "MyNewLog"
       If (cmdArgs.Count() > 0) Then
           eventSourceName = cmdArgs(0)
       End If
       If (cmdArgs.Count() > 1) Then
           logName = cmdArgs(1)
       End If
       eventLog1 = New EventLog()
       If (Not EventLog.SourceExists(eventSourceName)) Then
           EventLog.CreateEventSource(eventSourceName, logName)
       End If
       eventLog1.Source = eventSourceName
       eventLog1.Log = logName
   End Sub
   ```

   Bu kod, olay kaynağını ve günlük adını kullanıcının sağladığı başlangıç parametrelerine göre ayarlar. Herhangi bir bağımsız değişken sağlanmadığında, varsayılan değerleri kullanır.

3. Komut satırı bağımsız değişkenlerini belirtmek için, **ProjectInstaller.cs**veya **ProjectInstaller. vb**dosyasındaki `ProjectInstaller` sınıfına aşağıdaki kodu ekleyin:

   ```csharp
   protected override void OnBeforeInstall(IDictionary savedState)
   {
       string parameter = "MySource1\" \"MyLogFile1";
       Context.Parameters["assemblypath"] = "\"" + Context.Parameters["assemblypath"] + "\" \"" + parameter + "\"";
       base.OnBeforeInstall(savedState);
   }
   ```

   ```vb
   Protected Overrides Sub OnBeforeInstall(ByVal savedState As IDictionary)
       Dim parameter As String = "MySource1"" ""MyLogFile1"
       Context.Parameters("assemblypath") = """" + Context.Parameters("assemblypath") + """ """ + parameter + """"
       MyBase.OnBeforeInstall(savedState)
   End Sub
   ```

   Genellikle, bu değer Windows hizmeti için yürütülebilir dosyanın tam yolunu içerir. Hizmetin doğru başlaması için, kullanıcının yol ve her bir parametre için tırnak işaretleri sağlaması gerekir. Kullanıcı, Windows hizmeti için başlangıç parametrelerini değiştirmek üzere **ImagePath** kayıt defteri girdisindeki parametreleri değiştirebilir. Ancak, daha iyi bir yol, değeri programlı bir şekilde değiştirmek ve işlevselliği bir yönetim veya yapılandırma yardımcı programı kullanarak gibi Kullanıcı dostu bir şekilde kullanıma sunmasıdır.

## <a name="build-the-service"></a>Hizmeti oluşturun

1. **Çözüm Gezgini**' de, **MyNewService** projesinin kısayol menüsünden **Özellikler** ' i seçin.

   Projeniz için özellik sayfaları görüntülenir.

2. **Uygulama** sekmesinde, **Başlangıç nesnesi** listesinde, Visual Basic projeler için **MyNewService. program**veya **Sub Main** ' i seçin.

3. Projeyi derlemek için, **Çözüm Gezgini**menüsünde, projeniz için kısayol menüsünden **Oluştur** ' u seçin (veya **CTRL**+ **+ Shift**+**B**tuşlarına basın).

## <a name="install-the-service"></a>Hizmeti yükler

Windows hizmetini oluşturduğunuza göre, artık yükleyebilirsiniz. Bir Windows hizmetini yüklemek için, yüklendiği bilgisayarda yönetici kimlik bilgilerine sahip olmanız gerekir.

1. Yönetim kimlik bilgileriyle [Visual Studio için geliştirici komut istemi](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) açın. Windows **Başlat** menüsünde, Visual Studio klasöründeki **vs 2017 için geliştirici komut istemi** ' yi seçin ve > ardından kısayol menüsünde**yönetici olarak çalıştır** ' ı seçin.

2. **Visual Studio için geliştirici komut istemi** penceresinde, projenizin çıkışını içeren klasöre gidin (varsayılan olarak, projenizin *\Bin\Debug* alt dizininde).

3. Aşağıdaki komutu girin:

    ```shell
    installutil MyNewService.exe
    ```

    Hizmet başarıyla yüklerse, komut başarıyı bildirir.

    Sistem *InstallUtil. exe*' yi bulamazsa, bilgisayarınızda bulunduğundan emin olun. Bu araç, *%windir%\Microsoft.NET\Framework [64\\]&lt;&gt;Framework sürümü*klasörüne .NET Framework yüklenir. Örneğin, 64 bit sürümü için varsayılan yol *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*' dir.

    **InstallUtil. exe** işlemi başarısız olursa, nedenini öğrenmek için yükleme günlüğünü kontrol edin. Varsayılan olarak, günlük hizmet yürütülebiliri ile aynı klasörsdır. Yükleme şu durumlarda başarısız olabilir:
    - <xref:System.ComponentModel.RunInstallerAttribute> Sınıf `ProjectInstaller` sınıfında yok.
    - Özniteliği olarak `true`ayarlanmadı.
    - `ProjectInstaller` Sınıfı olarak`public`tanımlanmamıştır.

Daha fazla bilgi için [nasıl yapılır: Hizmetleri](how-to-install-and-uninstall-services.md)yükleme ve kaldırma.

## <a name="start-and-run-the-service"></a>Hizmeti başlatma ve çalıştırma

1. Windows 'ta, **Hizmetler** masaüstü uygulamasını açın. **Windows**R tuşuna basarak Çalıştır kutusunu açın, Services. msc yazın ve ardından ENTER tuşuna basın veya Tamam ' ı seçin.+

     Hizmetinizi, sizin için ayarladığınız görünen ada göre alfabetik olarak görüntülenen **Hizmetler**bölümünde görmeniz gerekir.

     ![Hizmetler penceresinde MyNewService.](media/windowsservices-serviceswindow.PNG)

2. Hizmeti başlatmak için hizmetin kısayol menüsünden **Başlat** ' ı seçin.

3. Hizmeti durdurmak için hizmetin kısayol menüsünden **Durdur** ' u seçin.

4. Seçim Hizmetinizi başlatmak ve durdurmak için komut satırından **net start &lt;Service Name&gt;**  ve **net stop &lt;hizmet adı&gt;**  komutlarını kullanın.

### <a name="verify-the-event-log-output-of-your-service"></a>Hizmetinizin olay günlüğü çıkışını doğrulama

1. Windows 'ta **Olay Görüntüleyicisi** masaüstü uygulamasını açın. Windows Search çubuğuna *Olay Görüntüleyicisi* girin ve sonra arama sonuçlarından **Olay Görüntüleyicisi** ' ı seçin.

   > [!TIP]
   > Visual Studio 'da, **Görünüm** menüsünden **Sunucu Gezgini** açarak (veya **CTRL**+**alt**+**öğeleri**' ne basarak) ve yerel bilgisayarın **olay günlükleri** düğümünü genişleterek olay günlüklerine erişebilirsiniz.

2. **Olay Görüntüleyicisi**, **uygulama ve hizmet günlükleri**' ni genişletin.

3. **MyNewLog** listesini bulun (veya komut satırı bağımsız değişkenleri ekleme yordamını Izlediyseniz **MyLogFile1** ) ve genişletin. Hizmetinizin gerçekleştirdiği iki eylem (başlatma ve durdurma) için girişleri görmeniz gerekir.

     ![Olay günlüğü girişlerini görmek için Olay Görüntüleyicisi kullanın](media/windows-service-event-viewer.png)

## <a name="clean-up-resources"></a>Kaynakları temizleme

Artık Windows hizmeti uygulamasına ihtiyacınız yoksa, bunu kaldırabilirsiniz.

1. Yönetim kimlik bilgileriyle **Visual Studio için geliştirici komut istemi** açın.

2. **Visual Studio için geliştirici komut istemi** penceresinde, projenizin çıkışını içeren klasöre gidin.

3. Aşağıdaki komutu girin:

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   Hizmet başarıyla kaldırılırsa, komut hizmetinizin başarıyla kaldırıldığını bildirir. Daha fazla bilgi için [nasıl yapılır: Hizmetleri](how-to-install-and-uninstall-services.md)yükleme ve kaldırma.

## <a name="next-steps"></a>Sonraki adımlar

Hizmeti oluşturduğumuz artık şunları yapabilirsiniz:

- Başkalarının Windows hizmetinizi yüklemek için kullanması için tek başına bir kurulum programı oluşturun. [Wix araç takımını](https://wixtoolset.org/) kullanarak bir Windows hizmeti için yükleyici oluşturun. Diğer fikirler için bkz. [Yükleyici paketi oluşturma](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).

- Yüklemiş olduğunuz hizmete komutlar göndermenizi sağlayan bileşenigezin.<xref:System.ServiceProcess.ServiceController>

- Uygulama çalışırken olay günlüğü oluşturmak yerine, uygulamayı yüklerken bir olay günlüğü oluşturmak için bir yükleyici kullanın. Uygulamayı kaldırdığınızda olay günlüğü yükleyici tarafından silinir. Daha fazla bilgi için bkz. <xref:System.Diagnostics.EventLogInstaller>.

## <a name="see-also"></a>Ayrıca bkz.

- [Windows hizmeti uygulamaları](index.md)
- [Windows hizmet uygulamalarına giriş](introduction-to-windows-service-applications.md)
- [Nasıl yapılır: Windows hizmet uygulamalarında hata ayıklama](how-to-debug-windows-service-applications.md)
- [Hizmetler (Windows)](/windows/desktop/Services/services)
