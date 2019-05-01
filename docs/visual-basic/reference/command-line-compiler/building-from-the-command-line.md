---
title: Komut Satırından Derleme (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: 798baa90308c83e42b335635fb23a9983f5180fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61839390"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="a99be-102">Komut Satırından Derleme (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a99be-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="a99be-103">Visual Basic projesinde bir veya daha fazla ayrı bir kaynak dosyasından oluşur.</span><span class="sxs-lookup"><span data-stu-id="a99be-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="a99be-104">Derleme bilinen işlemi sırasında bu dosyaları birlikte tek bir pakette ulaşırlar — bir uygulama olarak çalıştırılabilir tek bir yürütülebilir dosya.</span><span class="sxs-lookup"><span data-stu-id="a99be-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 <span data-ttu-id="a99be-105">Visual Basic, Visual Studio tümleşik geliştirme ortamında (IDE) programları derleme alternatif olarak bir komut satırı derleyicisini sağlar.</span><span class="sxs-lookup"><span data-stu-id="a99be-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="a99be-106">Komut satırı derleyicisi, size gerekli olmayan IDE içindeki özellikleri kümesini durumlar için tasarlanmıştır-Örneğin, ne zaman, kullanan veya sınırlı sistem bellek ve depolama alanına sahip bilgisayarlar için yazma.</span><span class="sxs-lookup"><span data-stu-id="a99be-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
  <span data-ttu-id="a99be-107">Visual Studio IDE içinde kaynak dosyalarından derleme tercih **derleme** komutunu **derleme** menü.</span><span class="sxs-lookup"><span data-stu-id="a99be-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="a99be-108">Proje dosyalarını Visual Studio IDE'yi kullanarak derlediğinizde, ilişkili bilgileri görüntüleyebilir **vbc** komut ve çıktı penceresinde alt anahtarlar.</span><span class="sxs-lookup"><span data-stu-id="a99be-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="a99be-109">Bu bilgileri görüntülemek için Aç [Seçenekler iletişim kutusu, projeler ve çözümler, derleme ve çalıştırma](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)ve ardından **MSBuild proje oluşturması çıkış ayrıntısı** için **Normal** veya daha yüksek bir ayrıntı düzeyi.</span><span class="sxs-lookup"><span data-stu-id="a99be-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="a99be-110">Daha fazla bilgi için [nasıl yapılır: Görüntüleme, kaydetme ve yapılandırma derleme günlüğü dosyalarını](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span><span class="sxs-lookup"><span data-stu-id="a99be-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>  
  
 <span data-ttu-id="a99be-111">MSBuild kullanarak bir komut isteminde proje (.vbproj) dosyaları derleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a99be-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="a99be-112">Daha fazla bilgi için [komut satırı başvurusu](/visualstudio/msbuild/msbuild-command-line-reference) ve [izlenecek yol: MSBuild kullanarak](/visualstudio/msbuild/walkthrough-using-msbuild).</span><span class="sxs-lookup"><span data-stu-id="a99be-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a99be-113">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="a99be-113">In This Section</span></span>  
 [<span data-ttu-id="a99be-114">Nasıl yapılır: Komut Satırı Derleyicisini Çağırma</span><span class="sxs-lookup"><span data-stu-id="a99be-114">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="a99be-115">MS-DOS komut isteminde veya belirli bir alt dizinden komut satırı derleyicisini çağırma açıklar.</span><span class="sxs-lookup"><span data-stu-id="a99be-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="a99be-116">Örnek Derleme Komut Satırları</span><span class="sxs-lookup"><span data-stu-id="a99be-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="a99be-117">Örnek komut satırları, kendi kullanımınız için değiştirebileceğiniz bir listesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="a99be-117">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a99be-118">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="a99be-118">Related Sections</span></span>  
 [<span data-ttu-id="a99be-119">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="a99be-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="a99be-120">Derleyici seçenekleri, alfabetik veya amacına göre düzenlenmiş bir listesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="a99be-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="a99be-121">Koşullu Derleme</span><span class="sxs-lookup"><span data-stu-id="a99be-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="a99be-122">Kodun belirli bölümlerine derleme açıklar.</span><span class="sxs-lookup"><span data-stu-id="a99be-122">Describes how to compile particular sections of code.</span></span>  
  
 [<span data-ttu-id="a99be-123">Visual Studio'da Projeler ve Çözümler Oluşturma ve Temizleme</span><span class="sxs-lookup"><span data-stu-id="a99be-123">Building and Cleaning Projects and Solutions in Visual Studio</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="a99be-124">Neler farklı derlemelerde bulunan proje özellikleri'ni seçin ve projelerin doğru sırada derleme sağlamak düzenlemek açıklar.</span><span class="sxs-lookup"><span data-stu-id="a99be-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
