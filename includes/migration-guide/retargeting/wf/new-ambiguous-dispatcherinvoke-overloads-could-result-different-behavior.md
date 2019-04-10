---
ms.openlocfilehash: 4529d8040fc08b5290ac46abd1ef752086ea3aeb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234828"
---
### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>Yeni (belirsiz) Dispatcher.Invoke aşırı yüklemeler farklı davranışlara neden

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.5 için yeni yükler ekler <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> türünde bir parametre içeren <xref:System.Action>. Varolan kod yeniden derlendiğinde, derleyiciler sahip Dispatcher.Invoke yöntemlere yapılan çağrılar çözülebilir bir <xref:System.Delegate> Dispatcher.Invoke yöntemleriyle çağrılar gibi bir <xref:System.Action> parametresi. Bir çağrı, bir Dispatcher.Invoke aşırı yükleme ile bir <xref:System.Delegate> parametresi bir Dispatcher.Invoke aşırı yüklemesi olan bir çağrı olarak çözümleniyorsa, bir <xref:System.Action> parametresi, davranışta aşağıdaki farklar meydana gelebilir:<ul><li>Bir özel durum oluşursa <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> ve <xref:System.Windows.Threading.Dispatcher.UnhandledException> olayları çoğalmaz. Bunun yerine, özel durum tarafından işlenen <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=name> olay.</li><li>Gibi bazı üyeler için çağrı <xref:System.Windows.Threading.DispatcherOperation.Result>, işlem tamamlanıncaya kadar engelleyin.</li></ul>|
|Öneri|Belirsizlik (ve işleme veya davranışlardan engelleyen bir özel durum olası farkları) kaçınmak için kod arama Dispatcher.Invoke bir boş object [] ikinci parametre olarak .NET Framework 4.0 yöntemi aşırı yüklemesine çözümleme emin olmak için Invoke çağrısına geçirebilirsiniz.|
|Kapsam|İkincil|
|Sürüm|4,5|
|Tür|Yeniden Hedefleme|
|Etkilenen API’ler|<ul><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType></li></ul>|
