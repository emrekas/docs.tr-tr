---
title: -errorreport (C# Derleyici Seçenekleri)
ms.date: 07/20/2015
f1_keywords:
- /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
ms.openlocfilehash: 4797f35a3738955f620fad7a93f8695685d21057
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59345098"
---
# <a name="-errorreport-c-compiler-options"></a><span data-ttu-id="68a3c-102">-errorreport (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="68a3c-102">-errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="68a3c-103">Bu seçenek, bir C# derleyici iç hatası Microsoft'a bildirmek için kullanışlı bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="68a3c-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68a3c-104">Windows Vista ve Windows Server 2008'de yaptığınız için Visual Studio hata raporlama ayarlarını Windows hata bildirimi (WER) aracılığıyla yapılan ayarlarını geçersiz kılmaz.</span><span class="sxs-lookup"><span data-stu-id="68a3c-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="68a3c-105">WER ayarları her zaman Visual Studio hata bildirimi ayarları üzerinde önceliklidir.</span><span class="sxs-lookup"><span data-stu-id="68a3c-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68a3c-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="68a3c-106">Syntax</span></span>  
  
```console  
-errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a><span data-ttu-id="68a3c-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="68a3c-107">Arguments</span></span>  
 <span data-ttu-id="68a3c-108">**Yok**</span><span class="sxs-lookup"><span data-stu-id="68a3c-108">**none**</span></span>  
 <span data-ttu-id="68a3c-109">Derleyici iç hatalarıyla ilgili raporlar toplanmaz ve Microsoft'a gönderilir.</span><span class="sxs-lookup"><span data-stu-id="68a3c-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>  
  
 <span data-ttu-id="68a3c-110">**istemi**</span><span class="sxs-lookup"><span data-stu-id="68a3c-110">**prompt**</span></span>  
 <span data-ttu-id="68a3c-111">Derleyici iç hatası aldığınızda rapor göndermek isteyip istemediğinizi sorar.</span><span class="sxs-lookup"><span data-stu-id="68a3c-111">Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="68a3c-112">**İstemi** geliştirme ortamında bir uygulama derlediğinizde varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="68a3c-112">**prompt** is the default when you compile an application in the development environment.</span></span>  
  
 <span data-ttu-id="68a3c-113">**Kuyruk**</span><span class="sxs-lookup"><span data-stu-id="68a3c-113">**queue**</span></span>  
 <span data-ttu-id="68a3c-114">Hata raporunu kuyruğa alır.</span><span class="sxs-lookup"><span data-stu-id="68a3c-114">Queues the error report.</span></span> <span data-ttu-id="68a3c-115">Yönetici kimlik bilgileriyle oturum açtığında günlüğe kaydedilen son Time hatalar bildirebilir.</span><span class="sxs-lookup"><span data-stu-id="68a3c-115">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="68a3c-116">Üç günde birden çok kez hata raporu göndermek için istenmez.</span><span class="sxs-lookup"><span data-stu-id="68a3c-116">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="68a3c-117">**Kuyruk** , komut satırında bir uygulama derlerken varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="68a3c-117">**queue** is the default when you compile an application at the command line.</span></span>  
  
 <span data-ttu-id="68a3c-118">**Gönder**</span><span class="sxs-lookup"><span data-stu-id="68a3c-118">**send**</span></span>  
 <span data-ttu-id="68a3c-119">Derleyici iç hata raporlarını otomatik olarak Microsoft'a gönderir.</span><span class="sxs-lookup"><span data-stu-id="68a3c-119">Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="68a3c-120">Bu seçeneği etkinleştirmek için önce Microsoft veri toplama ilkesini kabul etmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="68a3c-120">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="68a3c-121">Belirttiğiniz ilk kez **- errorreport: gönderme** bir bilgisayarda, bir derleyici iletisi Microsoft veri koleksiyonu ilkesini içeren Web sitesi başvuracaktır.</span><span class="sxs-lookup"><span data-stu-id="68a3c-121">The first time that you specify **-errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>  
    
## <a name="remarks"></a><span data-ttu-id="68a3c-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="68a3c-122">Remarks</span></span>  
 <span data-ttu-id="68a3c-123">Derleyici bir kaynak kodu dosyasını işlerken bir iç derleyici hatası (ICE) sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="68a3c-123">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="68a3c-124">Bir ICE ortaya çıktığında, derleyici bir çıktı dosyasını veya kodunuzu düzeltmek için kullanabileceğiniz herhangi bir kullanışlı tanılama üretmez.</span><span class="sxs-lookup"><span data-stu-id="68a3c-124">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>  
  
 <span data-ttu-id="68a3c-125">Bir ICE alındığında önceki sürümlerde, sorunu bildirmek için Microsoft Ürün Destek Hizmetleri'ne başvurmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="68a3c-125">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="68a3c-126">Kullanarak **- errorreport**, Visual C# ekibine ICE bilgi sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="68a3c-126">By using **-errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="68a3c-127">Hata raporları, gelecekteki derleyici sürümleri artırmaya yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="68a3c-127">Your error reports can help improve future compiler releases.</span></span>  
  
 <span data-ttu-id="68a3c-128">Bir kullanıcının yeteneğini raporları göndermek için bilgisayar ve kullanıcı ilkesi izinlerine bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="68a3c-128">A user's ability to send reports depends on computer and user policy permissions.</span></span>  
  
 <span data-ttu-id="68a3c-129">Hata ayıklayıcısı hakkında daha fazla bilgi için bkz: [Dr açıklaması. Windows (Drwtsn32.exe) aracı için Watson](https://support.microsoft.com/help/308538/description-of-the-dr--watson-for-windows-drwtsn32-exe-tool).</span><span class="sxs-lookup"><span data-stu-id="68a3c-129">For more information about error debugger, see [Description of the Dr. Watson for Windows (Drwtsn32.exe) Tool](https://support.microsoft.com/help/308538/description-of-the-dr--watson-for-windows-drwtsn32-exe-tool).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="68a3c-130">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="68a3c-130">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="68a3c-131">Projenin açın **özellikleri** sayfası.</span><span class="sxs-lookup"><span data-stu-id="68a3c-131">Open the project's **Properties** page.</span></span> <span data-ttu-id="68a3c-132">Daha fazla bilgi için [derleme sayfası, Proje Tasarımcısı (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="68a3c-132">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="68a3c-133">Tıklayın **derleme** özellik sayfası.</span><span class="sxs-lookup"><span data-stu-id="68a3c-133">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="68a3c-134">Tıklayın **Gelişmiş** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="68a3c-134">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="68a3c-135">Değiştirme **iç derleyici hatası raporlama** özelliği.</span><span class="sxs-lookup"><span data-stu-id="68a3c-135">Modify the **Internal Compiler Error Reporting** property.</span></span>  
  
 <span data-ttu-id="68a3c-136">Bu derleyici seçeneğini program üzerinden ayarlamak hakkında daha fazla bilgi için bkz. <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span><span class="sxs-lookup"><span data-stu-id="68a3c-136">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a3c-137">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="68a3c-137">See also</span></span>

- [<span data-ttu-id="68a3c-138">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="68a3c-138">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
