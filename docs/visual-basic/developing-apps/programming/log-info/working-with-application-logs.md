---
title: Visual Basic'te Uygulama Günlükleriyle Çalışma
ms.date: 07/20/2015
helpviewer_keywords:
- logs, application
- application event logs, Visual Basic
- application event logs
ms.assetid: 2581afd1-5791-4bc4-86b2-46244e9fe468
ms.openlocfilehash: 00c54a59ccfe2a49dcf35b322ca077a10a48ae7d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61712103"
---
# <a name="working-with-application-logs-in-visual-basic"></a><span data-ttu-id="ad606-102">Visual Basic'te Uygulama Günlükleriyle Çalışma</span><span class="sxs-lookup"><span data-stu-id="ad606-102">Working with Application Logs in Visual Basic</span></span>

<span data-ttu-id="ad606-103">`My.Application.Log` Ve `My.Log` nesnelerini günlüğe kaydetme ve izleme bilgileri günlüklere yazılır kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="ad606-103">The `My.Application.Log` and `My.Log` objects make it easy to write logging and tracing information to logs.</span></span>

## <a name="how-messages-are-logged"></a><span data-ttu-id="ad606-104">İletileri nasıl kaydedilir</span><span class="sxs-lookup"><span data-stu-id="ad606-104">How Messages are Logged</span></span>

<span data-ttu-id="ad606-105">İlk olarak, ileti önem derecesi ile denetlenir <xref:System.Diagnostics.TraceSource.Switch%2A> günlüğün özelliği <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="ad606-105">First, the severity of the message is checked with the <xref:System.Diagnostics.TraceSource.Switch%2A> property of the log's <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> property.</span></span> <span data-ttu-id="ad606-106">Tarafından varsayılan, yalnızca önem derecesi "Bilgi" iletileri ve daha yüksek günlüğün içinde belirtilen izleme dinleyicilerine geçirilir `TraceListener` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="ad606-106">By default, only messages of severity "Information" and higher are passed on to the trace listeners, specified in the log's `TraceListener` collection.</span></span> <span data-ttu-id="ad606-107">Ardından, her dinleyici şekilde dinleyicinin iletinin önem karşılaştırır <xref:System.Diagnostics.TraceSource.Switch%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="ad606-107">Then, each listener compares the severity of the message to the listener's <xref:System.Diagnostics.TraceSource.Switch%2A> property.</span></span> <span data-ttu-id="ad606-108">İleti önem derecesi yeterince yüksek ise dinleyici iletisi yazar.</span><span class="sxs-lookup"><span data-stu-id="ad606-108">If the message's severity is high enough, the listener writes out the message.</span></span>

<span data-ttu-id="ad606-109">Yazılan bir ileti nasıl gösterir Aşağıdaki diyagramda `WriteEntry` yöntemi geçirilen `WriteLine` günlüğün yöntemlerinin izleme dinleyicileri:</span><span class="sxs-lookup"><span data-stu-id="ad606-109">The following diagram shows how a message written to the `WriteEntry` method gets passed to the `WriteLine` methods of the log's trace listeners:</span></span>

![My günlük araması gösteren diyagram.](./media/working-with-application-logs/my-log-call-messages.png)

<span data-ttu-id="ad606-111">Günlük ve iz dinleyicileri davranışını, uygulamanın yapılandırma dosyasını değiştirerek değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ad606-111">You can change the behavior of the log and the trace listeners by changing the application's configuration file.</span></span> <span data-ttu-id="ad606-112">Aşağıdaki diyagramda, günlük bölümlerini ve yapılandırma dosyası arasındaki ilişkiyi gösterir.</span><span class="sxs-lookup"><span data-stu-id="ad606-112">The following diagram shows the correspondence between the parts of the log and the configuration file.</span></span>

![My günlük yapılandırmasını gösteren diyagram.](./media/working-with-application-logs/my-log-configuration.png)

## <a name="where-messages-are-logged"></a><span data-ttu-id="ad606-114">Burada iletileri günlüğe kaydedilir</span><span class="sxs-lookup"><span data-stu-id="ad606-114">Where Messages are Logged</span></span>

<span data-ttu-id="ad606-115">Derleme herhangi bir yapılandırma dosyası varsa `My.Application.Log` ve `My.Log` nesneleri yazmak için uygulamanın hata ayıklama çıkışını (aracılığıyla <xref:System.Diagnostics.DefaultTraceListener> sınıfı).</span><span class="sxs-lookup"><span data-stu-id="ad606-115">If the assembly has no configuration file, the `My.Application.Log` and `My.Log` objects write to the application's debug output (through the <xref:System.Diagnostics.DefaultTraceListener> class).</span></span> <span data-ttu-id="ad606-116">Ayrıca, `My.Application.Log` nesneyi derlemenin günlük dosyasına yazar (aracılığıyla <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> sınıfı), ancak `My.Log` nesneyi ASP.NET Web sayfasına ilişkin çıktısına yazar (aracılığıyla <xref:System.Web.WebPageTraceListener> sınıfı).</span><span class="sxs-lookup"><span data-stu-id="ad606-116">In addition, the `My.Application.Log` object writes to the assembly's log file (through the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class), while the `My.Log` object writes to the ASP.NET Web page's output (through the <xref:System.Web.WebPageTraceListener> class).</span></span>

<span data-ttu-id="ad606-117">Visual Studio'da hata ayıklama çıkışı görüntülenebilir **çıkış** uygulamanızı hata ayıklama modunda çalışırken penceresi.</span><span class="sxs-lookup"><span data-stu-id="ad606-117">The debug output can be viewed in the Visual Studio **Output** window when running your application in debug mode.</span></span> <span data-ttu-id="ad606-118">Açmak için **çıkış** penceresinde tıklayın **hata ayıklama** menü öğesi, noktasına **Windows**ve ardından **çıkış**.</span><span class="sxs-lookup"><span data-stu-id="ad606-118">To open the **Output** window, click the **Debug** menu item, point to **Windows**, and then click **Output**.</span></span> <span data-ttu-id="ad606-119">İçinde **çıkış** penceresinde **hata ayıklama** gelen **çıktıyı Göster** kutusu.</span><span class="sxs-lookup"><span data-stu-id="ad606-119">In the **Output** window, select **Debug** from the **Show output from** box.</span></span>

<span data-ttu-id="ad606-120">Varsayılan olarak, `My.Application.Log` yolunda kullanıcının uygulama verileri için günlük dosyasına yazar.</span><span class="sxs-lookup"><span data-stu-id="ad606-120">By default, `My.Application.Log` writes the log file in the path for the user's application data.</span></span> <span data-ttu-id="ad606-121">Yolundan alabilirsiniz <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> özelliği <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> nesne.</span><span class="sxs-lookup"><span data-stu-id="ad606-121">You can get the path from the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> property of the <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> object.</span></span> <span data-ttu-id="ad606-122">Yol biçimi aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="ad606-122">The format of that path is as follows:</span></span>

`BasePath`\\`CompanyName`\\`ProductName`\\`ProductVersion`

<span data-ttu-id="ad606-123">İçin tipik bir değer `BasePath` gibidir.</span><span class="sxs-lookup"><span data-stu-id="ad606-123">A typical value for `BasePath` is as follows.</span></span>

<span data-ttu-id="ad606-124">C:\Documents ve ayarları\\`username`\Application veri</span><span class="sxs-lookup"><span data-stu-id="ad606-124">C:\Documents and Settings\\`username`\Application Data</span></span>

<span data-ttu-id="ad606-125">Değerlerini `CompanyName`, `ProductName`, ve `ProductVersion` uygulamanın derleme bilgilerden gelir.</span><span class="sxs-lookup"><span data-stu-id="ad606-125">The values of `CompanyName`, `ProductName`, and `ProductVersion` come from the application's assembly information.</span></span> <span data-ttu-id="ad606-126">Günlük dosyası adı biçimindedir *AssemblyName*.log, burada *AssemblyName* uzantısı olmadan bir derlemenin dosya adı.</span><span class="sxs-lookup"><span data-stu-id="ad606-126">The form of the log file name is *AssemblyName*.log, where *AssemblyName* is the file name of the assembly without the extension.</span></span> <span data-ttu-id="ad606-127">Orijinal günlüğü kullanılamadığında uygulama günlüğüne yazmak çalıştığında gibi birden fazla günlük dosyası gerekli olursa, günlük dosyası adı için formdur *AssemblyName*-*yineleme* .log, burada `iteration` bir pozitif `Integer`.</span><span class="sxs-lookup"><span data-stu-id="ad606-127">If more than one log file is needed, such as when the original log is unavailable when the application attempts to write to the log, the form for the log file name is *AssemblyName*-*iteration*.log, where `iteration` is a positive `Integer`.</span></span>

<span data-ttu-id="ad606-128">Ekleyerek veya değiştirerek bilgisayarın ve uygulama yapılandırma dosyaları varsayılan davranışı geçersiz kılabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ad606-128">You can override the default behavior by adding or changing the computer's and the application's configuration files.</span></span> <span data-ttu-id="ad606-129">Daha fazla bilgi için [izlenecek yol: My.Application.log günlüğünün bilgileri nereye yazdığını değiştirme](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="ad606-129">For more information, see [Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md).</span></span>

## <a name="configuring-log-settings"></a><span data-ttu-id="ad606-130">Günlük ayarlarını yapılandırma</span><span class="sxs-lookup"><span data-stu-id="ad606-130">Configuring Log Settings</span></span>

<span data-ttu-id="ad606-131">`Log` Nenesindeki çalışır ve varsayılan bir uygulama bir uygulama yapılandırma dosyası app.config. Varsayılan değerleri değiştirmek için yeni ayarlar ile bir yapılandırma dosyası eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ad606-131">The `Log` object has a default implementation that works without an application configuration file, app.config. To change the defaults, you must add a configuration file with the new settings.</span></span> <span data-ttu-id="ad606-132">Daha fazla bilgi için [izlenecek yol: My.Application.Log çıktısını filtreleme](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="ad606-132">For more information, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>

<span data-ttu-id="ad606-133">Günlük yapılandırma bölümlerini bulunan `<system.diagnostics>` ana düğüm `<configuration>` app.config dosyasının düğümü.</span><span class="sxs-lookup"><span data-stu-id="ad606-133">The log configuration sections are located in the `<system.diagnostics>` node in the main `<configuration>` node of the app.config file.</span></span> <span data-ttu-id="ad606-134">Günlük bilgilerini, çeşitli düğümler tanımlanır:</span><span class="sxs-lookup"><span data-stu-id="ad606-134">Log information is defined in several nodes:</span></span>

- <span data-ttu-id="ad606-135">Dinleyiciler için `Log` nesne tanımlanmış `<sources>` DefaultSource adlı düğüm.</span><span class="sxs-lookup"><span data-stu-id="ad606-135">The listeners for the `Log` object are defined in the `<sources>` node named DefaultSource.</span></span>

- <span data-ttu-id="ad606-136">Önem derecesi filtresi `Log` nesne tanımlanmış `<switches>` DefaultSwitch adlı düğüm.</span><span class="sxs-lookup"><span data-stu-id="ad606-136">The severity filter for the `Log` object is defined in the `<switches>` node named DefaultSwitch.</span></span>

- <span data-ttu-id="ad606-137">Günlük dinleyicileri tanımlanan `<sharedListeners>` düğümü.</span><span class="sxs-lookup"><span data-stu-id="ad606-137">The log listeners are defined in the `<sharedListeners>` node.</span></span>

 <span data-ttu-id="ad606-138">Örnekleri `<sources>`, `<switches>`, ve `<sharedListeners>` düğümleri, aşağıdaki kodda gösterilmiştir:</span><span class="sxs-lookup"><span data-stu-id="ad606-138">Examples of `<sources>`, `<switches>`, and `<sharedListeners>` nodes are shown in the following code:</span></span>

```xml
<configuration>
  <system.diagnostics>
    <sources>
      <source name="DefaultSource" switchName="DefaultSwitch">
        <listeners>
          <add name="FileLog"/>
        </listeners>
      </source>
    </sources>
    <switches>
      <add name="DefaultSwitch" value="Information" />
    </switches>
    <sharedListeners>
      <add name="FileLog"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
          Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
          PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL"
        initializeData="FileLogWriter"
      />
    </sharedListeners>
  </system.diagnostics>
</configuration>
```

## <a name="changing-log-settings-after-deployment"></a><span data-ttu-id="ad606-139">Dağıtımdan sonra günlük ayarlarını değiştirme</span><span class="sxs-lookup"><span data-stu-id="ad606-139">Changing Log Settings after Deployment</span></span>

<span data-ttu-id="ad606-140">Bir uygulama geliştirdiğinizde, Yukarıdaki örneklerde gösterildiği gibi yapılandırma ayarlarını app.config dosyasında depolanır.</span><span class="sxs-lookup"><span data-stu-id="ad606-140">When you develop an application, its configuration settings are stored in the app.config file, as shown in the examples above.</span></span> <span data-ttu-id="ad606-141">Uygulamanızı dağıttıktan sonra yapılandırma dosyasını düzenleyerek günlük yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ad606-141">After you deploy your application, you can still configure the log by editing the configuration file.</span></span> <span data-ttu-id="ad606-142">Windows tabanlı bir uygulama, bu dosyanın adıdır *applicationName*. exe.config ve yürütülebilir dosyasıyla aynı klasörde bulunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="ad606-142">In a Windows-based application, this file's name is *applicationName*.exe.config, and it must reside in the same folder as the executable file.</span></span> <span data-ttu-id="ad606-143">Bir Web uygulaması için bu yöntem, projeyle ilişkili Web.config dosyasıdır.</span><span class="sxs-lookup"><span data-stu-id="ad606-143">For a Web application, this is the Web.config file associated with the project.</span></span>

<span data-ttu-id="ad606-144">Uygulamanızı ilk kez bir sınıf örneği oluşturan kodu yürütüldüğünde, nesne hakkında bilgi için yapılandırma dosyasını denetler.</span><span class="sxs-lookup"><span data-stu-id="ad606-144">When your application executes the code that creates an instance of a class for the first time, it checks the configuration file for information about the object.</span></span> <span data-ttu-id="ad606-145">İçin `Log` nesne, ilk kez böyle `Log` erişilen nesne.</span><span class="sxs-lookup"><span data-stu-id="ad606-145">For the `Log` object, this happens the first time the `Log` object is accessed.</span></span> <span data-ttu-id="ad606-146">Sistem yapılandırma dosyası herhangi bir nesne için yalnızca bir kez inceler; ilk kez uygulama nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="ad606-146">The system examines the configuration file only once for any particular object—the first time your application creates the object.</span></span> <span data-ttu-id="ad606-147">Bu nedenle, değişikliklerin etkili olması uygulamayı yeniden başlatmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="ad606-147">Therefore, you may need to restart the application for the changes to take effect.</span></span>

<span data-ttu-id="ad606-148">Dağıtılan bir uygulamada izleme kodu, uygulama başlatılmadan önce anahtar nesneleri yeniden etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="ad606-148">In a deployed application, you enable trace code by reconfiguring switch objects before your application starts.</span></span> <span data-ttu-id="ad606-149">Genellikle, bu anahtar nesneler üzerinde ve devre dışı veya izleme düzeylerini değiştirip ardından uygulamanız yeniden kapatma içerir.</span><span class="sxs-lookup"><span data-stu-id="ad606-149">Typically, this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="ad606-150">Güvenlik Değerlendirmeleri</span><span class="sxs-lookup"><span data-stu-id="ad606-150">Security Considerations</span></span>

<span data-ttu-id="ad606-151">Veri günlüğü için yazarken aşağıdakileri değerlendirin:</span><span class="sxs-lookup"><span data-stu-id="ad606-151">Consider the following when writing data to the log:</span></span>

- <span data-ttu-id="ad606-152">**Kullanıcı bilgilerini sızmasını önleyin.**</span><span class="sxs-lookup"><span data-stu-id="ad606-152">**Avoid leaking user information.**</span></span> <span data-ttu-id="ad606-153">Uygulama yazma işlemlerini günlüğe yazılacak bilgi yalnızca onaylanan emin olun.</span><span class="sxs-lookup"><span data-stu-id="ad606-153">Ensure that your application writes only approved information to the log.</span></span> <span data-ttu-id="ad606-154">Örneğin, kullanıcı adları, ancak kullanıcı parolalarının içermesi için Uygulama günlüğünü kabul edilebilir olabilir.</span><span class="sxs-lookup"><span data-stu-id="ad606-154">For example, it may be acceptable for the application log to contain user names, but not user passwords.</span></span>

- <span data-ttu-id="ad606-155">**Günlük konumları güvenli hale.**</span><span class="sxs-lookup"><span data-stu-id="ad606-155">**Make log locations secure.**</span></span> <span data-ttu-id="ad606-156">Olası hassas bilgiler içeren herhangi bir günlüğü güvenli bir konumda depolanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="ad606-156">Any log that contains potentially sensitive information should be stored in a secure location.</span></span>

- <span data-ttu-id="ad606-157">**Yanıltıcı bilgi kaçının.**</span><span class="sxs-lookup"><span data-stu-id="ad606-157">**Avoid misleading information.**</span></span> <span data-ttu-id="ad606-158">Genel olarak, uygulamanızın verileri kullanmadan önce bir kullanıcı tarafından girilen tüm veriler doğrulamalıdır.</span><span class="sxs-lookup"><span data-stu-id="ad606-158">In general, your application should validate all data entered by a user before using that data.</span></span> <span data-ttu-id="ad606-159">Bu, verileri uygulama günlüğüne yazma içerir.</span><span class="sxs-lookup"><span data-stu-id="ad606-159">This includes writing data to the application log.</span></span>

- <span data-ttu-id="ad606-160">**Hizmet reddi kaçının.**</span><span class="sxs-lookup"><span data-stu-id="ad606-160">**Avoid denial of service.**</span></span> <span data-ttu-id="ad606-161">Uygulamanızı günlüğe çok bilgi yazar, bunu günlük dolgu yüklenemedi veya zor önemli bilgileri bulmanızı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="ad606-161">If your application writes too much information to the log, it could fill the log or make finding important information difficult.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad606-162">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ad606-162">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="ad606-163">Uygulamadan Günlüğe Bilgi Kaydetme</span><span class="sxs-lookup"><span data-stu-id="ad606-163">Logging Information from the Application</span></span>](../../../../visual-basic/developing-apps/programming/log-info/index.md)
