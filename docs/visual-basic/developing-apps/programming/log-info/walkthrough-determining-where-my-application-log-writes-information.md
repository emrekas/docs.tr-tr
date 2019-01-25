---
title: My.Application.Log (Visual Basic) bilgileri nereye yazdığını belirleme
ms.date: 07/20/2015
helpviewer_keywords:
- My.Log object, output location
- output, application log location
- My.Application.Log object, outpout location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
ms.openlocfilehash: bafb307eff6a5ce6fd6dff823abe2f68b7725f51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662679"
---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="10914-102">İzlenecek yol: My.Application.Log (Visual Basic) bilgileri nereye yazdığını belirleme</span><span class="sxs-lookup"><span data-stu-id="10914-102">Walkthrough: Determining Where My.Application.Log Writes Information (Visual Basic)</span></span>
<span data-ttu-id="10914-103">`My.Application.Log` Nesne için birkaç günlük dinleyicileri bilgileri yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10914-103">The `My.Application.Log` object can write information to several log listeners.</span></span> <span data-ttu-id="10914-104">Günlük dinleyicileri bilgisayarın yapılandırma dosyası tarafından yapılandırılır ve bir uygulamanın yapılandırma dosyası tarafından geçersiz kılınabilir.</span><span class="sxs-lookup"><span data-stu-id="10914-104">The log listeners are configured by the computer's configuration file and can be overridden by an application's configuration file.</span></span> <span data-ttu-id="10914-105">Bu konu başlığı altında varsayılan ayarları ve uygulama ayarlarını belirlemek nasıl açıklar.</span><span class="sxs-lookup"><span data-stu-id="10914-105">This topic describes the default settings and how to determine the settings for your application.</span></span>  
  
 <span data-ttu-id="10914-106">Varsayılan çıkış konumları hakkında daha fazla bilgi için bkz. [uygulama günlükleriyle çalışma](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="10914-106">For more information about the default output locations, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
### <a name="to-determine-the-listeners-for-myapplicationlog"></a><span data-ttu-id="10914-107">My.Application.Log için dinleyicileri belirlemek için</span><span class="sxs-lookup"><span data-stu-id="10914-107">To determine the listeners for My.Application.Log</span></span>  
  
1.  <span data-ttu-id="10914-108">Derlemenin yapılandırma dosyasını bulun.</span><span class="sxs-lookup"><span data-stu-id="10914-108">Locate the assembly's configuration file.</span></span> <span data-ttu-id="10914-109">Derleme geliştiriyorsanız app.config dosyasında Visual Studio'dan erişebilirsiniz **Çözüm Gezgini**.</span><span class="sxs-lookup"><span data-stu-id="10914-109">If you are developing the assembly, you can access the app.config in Visual Studio from the **Solution Explorer**.</span></span> <span data-ttu-id="10914-110">Aksi takdirde, yapılandırma dosyası adı "ile .config" eklenmiş derlemenin adıdır ve derleme olarak aynı dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="10914-110">Otherwise, the configuration file name is the assembly's name appended with ".config", and it is located in the same directory as the assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10914-111">Her derleme, bir yapılandırma dosyası vardır.</span><span class="sxs-lookup"><span data-stu-id="10914-111">Not every assembly has a configuration file.</span></span>  
  
     <span data-ttu-id="10914-112">Yapılandırma dosyasını bir XML dosyasıdır.</span><span class="sxs-lookup"><span data-stu-id="10914-112">The configuration file is an XML file.</span></span>  
  
2.  <span data-ttu-id="10914-113">Bulun `<listeners>` bölümünde `<source>` ile bölümünde `name` "DefaultSource bulunan", öznitelik `<sources>` bölümü.</span><span class="sxs-lookup"><span data-stu-id="10914-113">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="10914-114">`<sources>` Bölümünde bulunan `<system.diagnostics>` bölümünde, üst düzey `<configuration>` bölümü.</span><span class="sxs-lookup"><span data-stu-id="10914-114">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
     <span data-ttu-id="10914-115">Bu bölümler mevcut sonra bilgisayarın yapılandırma dosyası yapılandırabilirsiniz `My.Application.Log` günlük dinleyicileri.</span><span class="sxs-lookup"><span data-stu-id="10914-115">If these sections do not exist, then the computer's configuration file may configure the `My.Application.Log` log listeners.</span></span> <span data-ttu-id="10914-116">Aşağıdaki adımlarda, bilgisayar yapılandırma dosyasını tanımlar belirleme açıklanmıştır:</span><span class="sxs-lookup"><span data-stu-id="10914-116">The following steps describe how to determine what the computer configuration file defines:</span></span>  
  
    1.  <span data-ttu-id="10914-117">Bilgisayar bir machine.config dosyasını bulun.</span><span class="sxs-lookup"><span data-stu-id="10914-117">Locate the computer's machine.config file.</span></span> <span data-ttu-id="10914-118">Genellikle, bulunur *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* dizin, burada `SystemRoot` işletim sistemi dizin ve `frameworkVersion` sürümü [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10914-118">Typically, it is located in the *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* directory, where `SystemRoot` is the operating system directory, and `frameworkVersion` is the version of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
         <span data-ttu-id="10914-119">Machine.config ayarlarında bir uygulamanın yapılandırma dosyası tarafından geçersiz kılınabilir.</span><span class="sxs-lookup"><span data-stu-id="10914-119">The settings in machine.config can be overridden by an application's configuration file.</span></span>  
  
         <span data-ttu-id="10914-120">Aşağıda listelenen isteğe bağlı öğeler mevcut değilse bunları oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="10914-120">If the optional elements listed below do not exist, you can create them.</span></span>  
  
    2.  <span data-ttu-id="10914-121">Bulun `<listeners>` bölümünde `<source>` ile bölümünde `name` "DefaultSource" özniteliğini `<sources>` bölümünde `<system.diagnostics>` bölümünde, üst düzey `<configuration>` bölümü.</span><span class="sxs-lookup"><span data-stu-id="10914-121">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
         <span data-ttu-id="10914-122">Bu bölüm yoksa, ardından `My.Application.Log` yalnızca varsayılan günlük dinleyicileri sahiptir.</span><span class="sxs-lookup"><span data-stu-id="10914-122">If these sections do not exist, then the `My.Application.Log` has only the default log listeners.</span></span>  
  
3.  <span data-ttu-id="10914-123">Bulun <`add>` öğelerinde <`listeners>` bölümü.</span><span class="sxs-lookup"><span data-stu-id="10914-123">Locate the <`add>` elements in the <`listeners>` section.</span></span>  
  
     <span data-ttu-id="10914-124">Bu öğeleri eklemek için adlandırılmış günlük dinleyicileri `My.Application.Log` kaynak.</span><span class="sxs-lookup"><span data-stu-id="10914-124">These elements add the named log listeners to `My.Application.Log` source.</span></span>  
  
4.  <span data-ttu-id="10914-125">Bulun `<add>` öğeleri içinde günlük dinleyicileri adlarıyla `<sharedListeners>` bölümünde `<system.diagnostics>` bölümünde, üst düzey `<configuration>` bölümü.</span><span class="sxs-lookup"><span data-stu-id="10914-125">Locate the `<add>` elements with the names of the log listeners in the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="10914-126">Paylaşılan dinleyiciler birçok tür için burada verileri dinleyici yönlendirir açıklaması dinleyicinin başlatma verilerini içerir:</span><span class="sxs-lookup"><span data-stu-id="10914-126">For many types of shared listeners, the listener's initialization data includes a description of where the listener directs the data:</span></span>  
  
    -   <span data-ttu-id="10914-127">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> dinleyicisi giriş açıklandığı bir dosyayı günlüğe yazar.</span><span class="sxs-lookup"><span data-stu-id="10914-127">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener writes to a file log, as described in the introduction.</span></span>  
  
    -   <span data-ttu-id="10914-128">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> dinleyici bilgileri tarafından belirtilen bilgisayarın olay günlüğüne yazdığı `initializeData` parametresi.</span><span class="sxs-lookup"><span data-stu-id="10914-128">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener writes information to the computer event log specified by the `initializeData` parameter.</span></span> <span data-ttu-id="10914-129">Olay günlüğünü görüntülemek için kullanabileceğiniz **Sunucu Gezgini** veya **Windows Olay Görüntüleyicisi'ni**.</span><span class="sxs-lookup"><span data-stu-id="10914-129">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="10914-130">Daha fazla bilgi için [.NET Framework ETW olayları](../../../../framework/performance/etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="10914-130">For more information, see [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span></span>  
  
    -   <span data-ttu-id="10914-131"><xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> Ve <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> dinleyicileri yazma belirtilen dosyaya `initializeData` parametresi.</span><span class="sxs-lookup"><span data-stu-id="10914-131">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners write to the file specified in the `initializeData` parameter.</span></span>  
  
    -   <span data-ttu-id="10914-132">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> dinleyici komut satırı konsola yazar.</span><span class="sxs-lookup"><span data-stu-id="10914-132">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener writes to the command-line console.</span></span>  
  
    -   <span data-ttu-id="10914-133">Burada günlük dinleyicileri diğer tür bilgilerini yazma hakkında daha fazla bilgi için bu türün belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="10914-133">For information about where other types of log listeners write information, consult that type's documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10914-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="10914-134">See also</span></span>
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DelimitedListTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics>
- [<span data-ttu-id="10914-135">Uygulama Günlükleriyle Çalışma</span><span class="sxs-lookup"><span data-stu-id="10914-135">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="10914-136">Nasıl yapılır: Günlük özel durumları</span><span class="sxs-lookup"><span data-stu-id="10914-136">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="10914-137">Nasıl yapılır: Günlük iletileri yazma</span><span class="sxs-lookup"><span data-stu-id="10914-137">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [<span data-ttu-id="10914-138">İzlenecek yol: My.Application.Log günlüğünün bilgileri yazdığı yeri değiştirme</span><span class="sxs-lookup"><span data-stu-id="10914-138">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="10914-139">.NET Framework'te ETW Olayları</span><span class="sxs-lookup"><span data-stu-id="10914-139">ETW Events in the .NET Framework</span></span>](../../../../framework/performance/etw-events.md)
- [<span data-ttu-id="10914-140">Sorun giderme: Günlük dinleyicileri</span><span class="sxs-lookup"><span data-stu-id="10914-140">Troubleshooting: Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
