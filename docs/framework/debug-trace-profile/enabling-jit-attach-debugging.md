---
title: JIT-Ekleme Hata Ayıklamayı Etkinleştirme
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7af34cf4bd3a2367eaf320990dbbc24f4e7a8bbf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64660146"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="7118a-102">JIT-Ekleme Hata Ayıklamayı Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="7118a-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="7118a-103">JIT-ekleme hata ayıklamayı hatalarla ya da belirli yöntemler ve işlevlere tarafından tetiklenebilir bir hata ayıklayıcı bir işlemine iliştirme açıklamak için kullanılan ifade var.</span><span class="sxs-lookup"><span data-stu-id="7118a-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="7118a-104">JIT-ekleme hata ayıklamayı aşağıdaki hata koşulları altında kullanılır:</span><span class="sxs-lookup"><span data-stu-id="7118a-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
- <span data-ttu-id="7118a-105">İşlenmeyen özel durumları (yerel ve yönetilen kod).</span><span class="sxs-lookup"><span data-stu-id="7118a-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
- <span data-ttu-id="7118a-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> yöntem veya [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) işlevi (Windows 7 ailesi).</span><span class="sxs-lookup"><span data-stu-id="7118a-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) function (Windows 7 family).</span></span>  
  
- <span data-ttu-id="7118a-107">Önemli hatalarla çalışma zamanı.</span><span class="sxs-lookup"><span data-stu-id="7118a-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="7118a-108">JIT-ekleme hata ayıklamayı aşağıdaki yöntemleri ve işlevleri yapılan çağrılar tarafından ayrıca başlatılır:</span><span class="sxs-lookup"><span data-stu-id="7118a-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
- <span data-ttu-id="7118a-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> yöntem.</span><span class="sxs-lookup"><span data-stu-id="7118a-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="7118a-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> yöntem.</span><span class="sxs-lookup"><span data-stu-id="7118a-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="7118a-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) işlevi (Win32).</span><span class="sxs-lookup"><span data-stu-id="7118a-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) function (Win32).</span></span>  
  
 <span data-ttu-id="7118a-112">Önce [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework sağlanan yerel ve yönetilen hata ayıklayıcıları davranışını denetlemek için ayrı bir kayıt defteri anahtarları.</span><span class="sxs-lookup"><span data-stu-id="7118a-112">Before the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="7118a-113">İle başlayarak [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], denetim bir tek bir kayıt defteri anahtarı altında birleştirilir: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="7118a-113">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="7118a-114">Bu anahtarı ayarlayabilirsiniz değerleri bir hata ayıklayıcı çağrılan, ve olup bu durumda, kullanıcı etkileşimi gerektiren bir iletişim kutusu çağrılır olup olmadığını belirler.</span><span class="sxs-lookup"><span data-stu-id="7118a-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="7118a-115">Bu kayıt defteri anahtarı ayarlama hakkında daha fazla bilgi için bkz: [otomatik hata ayıklama yapılandırma](https://go.microsoft.com/fwlink/?LinkId=181767).</span><span class="sxs-lookup"><span data-stu-id="7118a-115">For information about setting this registry key, see [Configuring Automatic Debugging](https://go.microsoft.com/fwlink/?LinkId=181767).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7118a-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7118a-116">See also</span></span>

- [<span data-ttu-id="7118a-117">Hata Ayıklama, İzleme ve Profil Oluşturma</span><span class="sxs-lookup"><span data-stu-id="7118a-117">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
- [<span data-ttu-id="7118a-118">Görüntüde Hata Ayıklamayı Kolaylaştırma</span><span class="sxs-lookup"><span data-stu-id="7118a-118">Making an Image Easier to Debug</span></span>](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)
