---
title: 'Nasıl yapılır: Bir Uygulamayı Yerelleştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: 777d0fa9217b647b9ee9bd952addaa83b5f825fc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374121"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="bceb3-102">Nasıl yapılır: Bir Uygulamayı Yerelleştirme</span><span class="sxs-lookup"><span data-stu-id="bceb3-102">How to: Localize an Application</span></span>
<span data-ttu-id="bceb3-103">Bu öğreticide LocBaml aracı kullanarak yerelleştirilmiş bir uygulama oluşturulacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="bceb3-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bceb3-104">LocBaml aracı, bir üretim ortamına hazır uygulamasını değil.</span><span class="sxs-lookup"><span data-stu-id="bceb3-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="bceb3-105">Bu, bazı yerelleştirme API'lerini kullanır ve yerelleştirme Aracı nasıl yazabilirsiniz gösterir bir örnek sunulur.</span><span class="sxs-lookup"><span data-stu-id="bceb3-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
<a name="Introduction"></a>   
## <a name="overview"></a><span data-ttu-id="bceb3-106">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="bceb3-106">Overview</span></span>  
 <span data-ttu-id="bceb3-107">Bu tartışma bir uygulamayı yerelleştirme için adım adım bir yaklaşım sunar.</span><span class="sxs-lookup"><span data-stu-id="bceb3-107">This discussion gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="bceb3-108">İlk olarak, böylece Çevrilecek metin ayıklanabileceği uygulamanızı hazırlayacaksınız.</span><span class="sxs-lookup"><span data-stu-id="bceb3-108">First, you will prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="bceb3-109">Metin çevrildikten sonra çevrilmiş metni özgün uygulamayı yeni bir kopyasını birleştirecektir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-109">After the text is translated, you will merge the translated text into a new copy of the original application.</span></span>  
  
<a name="Requirements"></a>   
## <a name="requirements"></a><span data-ttu-id="bceb3-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="bceb3-110">Requirements</span></span>  
 <span data-ttu-id="bceb3-111">Bu tartışma kursunda kullanacağınız [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)], komut satırından çalışan bir derleyici olduğu.</span><span class="sxs-lookup"><span data-stu-id="bceb3-111">Over the course of this discussion, you will use [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)], which is a compiler that runs from the command line.</span></span>  
  
 <span data-ttu-id="bceb3-112">Ayrıca, bir proje dosyasını kullanmak için yönlendirilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bceb3-112">Also, you will be instructed to use a project file.</span></span> <span data-ttu-id="bceb3-113">Nasıl kullanılacağı hakkında yönergeler için [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] ve proje dosyaları, bkz: [derleme ve dağıtma](../app-development/building-and-deploying-wpf-applications.md).</span><span class="sxs-lookup"><span data-stu-id="bceb3-113">For instructions on how to use [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] and project files, see [Build and Deploy](../app-development/building-and-deploying-wpf-applications.md).</span></span>  
  
 <span data-ttu-id="bceb3-114">Bu konudaki tüm örnekler en-US (İngilizce-ABD) kültürü kullanır.</span><span class="sxs-lookup"><span data-stu-id="bceb3-114">All the examples in this discussion use en-US (English-US) as the culture.</span></span> <span data-ttu-id="bceb3-115">Bu örneklerin adımları, farklı bir dil yüklemeden çalışmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="bceb3-115">This enables you to work through the steps of the examples without installing a different language.</span></span>  
  
<a name="create_sample_app"></a>   
## <a name="create-a-sample-application"></a><span data-ttu-id="bceb3-116">Örnek bir uygulama oluşturma</span><span class="sxs-lookup"><span data-stu-id="bceb3-116">Create a Sample Application</span></span>  
 <span data-ttu-id="bceb3-117">Bu adımda, uygulamanızın yerelleştirme için hazırlık yapacaksınız.</span><span class="sxs-lookup"><span data-stu-id="bceb3-117">In this step, you will prepare your application for localization.</span></span> <span data-ttu-id="bceb3-118">İçinde [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] örnekleri, bu konudaki kod örnekleri için kullanılacak bir HelloApp örnek sağlanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="bceb3-118">In the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="bceb3-119">Bu örneği kullanmak istiyorsanız, indirme [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] dosyalarını [LocBaml aracı örneği](https://go.microsoft.com/fwlink/?LinkID=160016).</span><span class="sxs-lookup"><span data-stu-id="bceb3-119">If you would like to use this sample, download the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] files from the [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016).</span></span>  
  
1.  <span data-ttu-id="bceb3-120">Yerelleştirme başlamak istediğiniz noktayı uygulamanızı geliştirin.</span><span class="sxs-lookup"><span data-stu-id="bceb3-120">Develop your application to the point where you want to start localization.</span></span>  
  
2.  <span data-ttu-id="bceb3-121">Proje dosyasında bir geliştirme dilini belirtmek böylece [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] bir ana derlemeye ve bir uydu derlemesi oluşturur (bir dosyayla. resources.dll uzantısı) nötr dil kaynakları içerecek şekilde.</span><span class="sxs-lookup"><span data-stu-id="bceb3-121">Specify the development language in the project file so that [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="bceb3-122">HelloApp örnek proje dosyasında HelloApp.csproj'dur.</span><span class="sxs-lookup"><span data-stu-id="bceb3-122">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="bceb3-123">Bu dosyada, aşağıdaki şekilde tanımlanan bir geliştirme dilini bulacaksınız:</span><span class="sxs-lookup"><span data-stu-id="bceb3-123">In that file, you will find the development language identified as follows:</span></span>  
  
     `<UICulture>en-US</UICulture>`  
  
3.  <span data-ttu-id="bceb3-124">İçin Uıd'leri ekleyin, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dosyaları.</span><span class="sxs-lookup"><span data-stu-id="bceb3-124">Add Uids to your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files.</span></span> <span data-ttu-id="bceb3-125">Uıd'leri dosyalarda yapılan değişiklikler izlemek ve çevrilmelidir öğeleri tanımlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="bceb3-125">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="bceb3-126">Uıd'leri dosyalarınıza eklemek için çalıştırın **updateuid** proje dosyanızda:</span><span class="sxs-lookup"><span data-stu-id="bceb3-126">To add Uids to your files, run **updateuid** on your project file:</span></span>  
  
     <span data-ttu-id="bceb3-127">**msbuild -t:updateuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="bceb3-127">**msbuild -t:updateuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="bceb3-128">Eksik veya Uıd'leri yinelenen doğrulamak için çalıştırın **checkuid**:</span><span class="sxs-lookup"><span data-stu-id="bceb3-128">To verify that you have no missing or duplicate Uids, run **checkuid**:</span></span>  
  
     <span data-ttu-id="bceb3-129">**msbuild -t:checkuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="bceb3-129">**msbuild -t:checkuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="bceb3-130">Çalıştırdıktan sonra **updateuid**, dosyalarınızı Uıd'leri içermelidir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-130">After running **updateuid**, your files should contain Uids.</span></span> <span data-ttu-id="bceb3-131">Örneğin, Pane1.xaml dosyasında, aşağıdaki bulduğunuz:</span><span class="sxs-lookup"><span data-stu-id="bceb3-131">For example, in the Pane1.xaml file of HelloApp, you should find the following:</span></span>  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>   
## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="bceb3-132">Nötr dil kaynakları uydu derleme oluşturma</span><span class="sxs-lookup"><span data-stu-id="bceb3-132">Create the Neutral Language Resources Satellite Assembly</span></span>  
 <span data-ttu-id="bceb3-133">Uygulama dilden kaynakları uydu derlemesi oluşturmak için yapılandırdıktan sonra uygulamayı derleyin.</span><span class="sxs-lookup"><span data-stu-id="bceb3-133">After the application is configured to generate a neutral language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="bceb3-134">Bu, ana uygulama derlemesine yanı sıra LocBaml tarafından yerelleştirme için gerekli bağımsız dil kaynakları uydu derlemesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="bceb3-134">This generates the main application assembly, as well as the neutral language resources satellite assembly that is required by LocBaml for localization.</span></span> <span data-ttu-id="bceb3-135">Uygulamayı oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="bceb3-135">To build the application:</span></span>  
  
1.  <span data-ttu-id="bceb3-136">Derleme oluşturmak için HelloApp bir [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="bceb3-136">Compile HelloApp to create a [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)]:</span></span>  
  
     <span data-ttu-id="bceb3-137">**MSBuild helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="bceb3-137">**msbuild helloapp.csproj**</span></span>  
  
2.  <span data-ttu-id="bceb3-138">Yeni oluşturulan ana uygulama derlemesine, HelloApp.exe aşağıdaki klasörde oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="bceb3-138">The newly created main application assembly, HelloApp.exe, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\`  
  
3.  <span data-ttu-id="bceb3-139">Yeni oluşturulan dilden kaynakları uydu derlemesini HelloApp.resources.dll aşağıdaki klasörde oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="bceb3-139">The newly created neutral language resources satellite assembly, HelloApp.resources.dll, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>   
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="bceb3-140">Derleme LocBaml aracı</span><span class="sxs-lookup"><span data-stu-id="bceb3-140">Build the LocBaml Tool</span></span>  
  
1.  <span data-ttu-id="bceb3-141">LocBaml oluşturmak gereken tüm dosyaları bulunan [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="bceb3-141">All the files necessary to build LocBaml are located in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] samples.</span></span> <span data-ttu-id="bceb3-142">C# dosyalarını indirmeye [LocBaml aracı örneği](https://go.microsoft.com/fwlink/?LinkID=160016).</span><span class="sxs-lookup"><span data-stu-id="bceb3-142">Download the C# files from the [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016).</span></span>  
  
2.  <span data-ttu-id="bceb3-143">Komut satırından derleme aracı için proje dosyası (locbaml.csproj) çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="bceb3-143">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  
  
     <span data-ttu-id="bceb3-144">**MSBuild locbaml.csproj**</span><span class="sxs-lookup"><span data-stu-id="bceb3-144">**msbuild locbaml.csproj**</span></span>  
  
3.  <span data-ttu-id="bceb3-145">Yeni oluşturulan yürütülebilir dosya (LocBaml.exe'yi) bulmak için Bin\Release dizine gidin.</span><span class="sxs-lookup"><span data-stu-id="bceb3-145">Go to the Bin\Release directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="bceb3-146">Example:C:\LocBaml\Bin\Release\locbaml.exe.</span><span class="sxs-lookup"><span data-stu-id="bceb3-146">Example:C:\LocBaml\Bin\Release\locbaml.exe.</span></span>  
  
4.  <span data-ttu-id="bceb3-147">LocBaml çalıştırdığınızda belirtebileceğiniz seçenekleri aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="bceb3-147">The options that you can specify when you run LocBaml are as follows:</span></span>  
  
    -   <span data-ttu-id="bceb3-148">**Ayrıştırma** veya **-p:** BAML, kaynaklar ayrıştırır veya [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] .csv ya da .txt dosyası oluşturmak için dosyaları.</span><span class="sxs-lookup"><span data-stu-id="bceb3-148">**parse** or **-p:** Parses Baml, resources, or [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] files to generate a .csv or .txt file.</span></span>  
  
    -   <span data-ttu-id="bceb3-149">**oluşturma** veya **-g:** Yerelleştirilmiş bir ikili dosya çevrilmiş bir dosyayı kullanarak oluşturur.</span><span class="sxs-lookup"><span data-stu-id="bceb3-149">**generate** or **-g:** Generates a localized binary file by using a translated file.</span></span>  
  
    -   <span data-ttu-id="bceb3-150">**Çıkış** veya **-o** {*filedirectory*] **:** Çıkış dosyası adı.</span><span class="sxs-lookup"><span data-stu-id="bceb3-150">**out** or **-o** {*filedirectory*] **:** Output file name.</span></span>  
  
    -   <span data-ttu-id="bceb3-151">**kültür** veya **- cul** {*kültür*] **:** Çıkış bütünleştirilmiş kodları yerel ayarı.</span><span class="sxs-lookup"><span data-stu-id="bceb3-151">**culture** or **-cul** {*culture*] **:** Locale of output assemblies.</span></span>  
  
    -   <span data-ttu-id="bceb3-152">**Çeviri** veya **- trans** {*translation.csv*] **:** Çevrilmiş veya yerelleştirilmiş dosyası.</span><span class="sxs-lookup"><span data-stu-id="bceb3-152">**translation** or **-trans** {*translation.csv*] **:** Translated or localized file.</span></span>  
  
    -   <span data-ttu-id="bceb3-153">**asmpath** veya **- asmpath:** {*filedirectory*] **:** Varsa, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] kodu özel denetimler içeren, siz sağlamalısınız **asmpath** özel denetim derleme.</span><span class="sxs-lookup"><span data-stu-id="bceb3-153">**asmpath** or **-asmpath:** {*filedirectory*] **:** If your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code contains custom controls, you must supply the **asmpath** to the custom control assembly.</span></span>  
  
    -   <span data-ttu-id="bceb3-154">**nologo:** Hiçbir logo veya telif hakkı bilgilerini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="bceb3-154">**nologo:** Displays no logo or copyright information.</span></span>  
  
    -   <span data-ttu-id="bceb3-155">**ayrıntılı:** Ayrıntılı modu bilgileri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="bceb3-155">**verbose:** Displays verbose mode information.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bceb3-156">Seçeneklerin bir listesi Aracı çalıştırırken gerekiyorsa, yazın **LocBaml.exe'yi** ve ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="bceb3-156">If you need a list of the options when you are running the tool, type     **LocBaml.exe** and press ENTER.</span></span>  
  
<a name="parse_dll"></a>   
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="bceb3-157">Bir dosya ayrıştırılamıyor LocBaml Kullanma</span><span class="sxs-lookup"><span data-stu-id="bceb3-157">Use LocBaml to Parse a File</span></span>  
 <span data-ttu-id="bceb3-158">LocBaml aracı oluşturduğunuza göre bu HelloApp.resources.dll yerelleştirilecek metin içeriği ayıklama için ayrıştırmak için kullanıma hazır olursunuz.</span><span class="sxs-lookup"><span data-stu-id="bceb3-158">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1.  <span data-ttu-id="bceb3-159">LocBaml.exe ana uygulama derlemesine oluşturulduğu, uygulamanızın bin\debug klasörüne kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="bceb3-159">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2.  <span data-ttu-id="bceb3-160">Uydu derleme dosyasını ayrıştırma ve bir .csv dosyası olarak çıktısını depolamak için aşağıdaki komutu kullanın:</span><span class="sxs-lookup"><span data-stu-id="bceb3-160">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
     <span data-ttu-id="bceb3-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span><span class="sxs-lookup"><span data-stu-id="bceb3-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bceb3-162">HelloApp.resources.dll giriş dosyası içinde değilse LocBaml.exe'yi aynı dizine taşı dosyalarından birini her iki dosya aynı dizinde olmasını sağlamak.</span><span class="sxs-lookup"><span data-stu-id="bceb3-162">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3.  <span data-ttu-id="bceb3-163">LocBaml dosyalarını ayrıştırmak için çalıştırdığınızda, çıktı virgül (.csv dosyaları) veya sekme (.txt dosyaları) tarafından ayrılmış yedi alandan oluşur.</span><span class="sxs-lookup"><span data-stu-id="bceb3-163">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="bceb3-164">Aşağıdaki ayrıştırılmış .csv dosyasını HelloApp.resources.dll için gösterir:</span><span class="sxs-lookup"><span data-stu-id="bceb3-164">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="bceb3-165">HelloApp.g.en US.resources:window1.baml, Stack1:System.Windows.Controls.StackPanel. $Content, Yoksay FALSE, FALSE, #Text1; #Text2;</span><span class="sxs-lookup"><span data-stu-id="bceb3-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="bceb3-166">HelloApp.g.en US.resources:window1.baml, Text1:System.Windows.Controls.TextBlock. None, $Content TRUE, TRUE, Merhaba Dünya</span><span class="sxs-lookup"><span data-stu-id="bceb3-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="bceb3-167">HelloApp.g.en US.resources:window1.baml, Text2:System.Windows.Controls.TextBlock. None, $Content TRUE, TRUE, güle güle World</span><span class="sxs-lookup"><span data-stu-id="bceb3-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="bceb3-168">Yedi alanlar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="bceb3-168">The seven fields are:</span></span>  
  
   1.  <span data-ttu-id="bceb3-169">**BAML adı**.</span><span class="sxs-lookup"><span data-stu-id="bceb3-169">**BAML Name**.</span></span> <span data-ttu-id="bceb3-170">Kaynak dili uydu derlemeye göre BAML kaynağının adı.</span><span class="sxs-lookup"><span data-stu-id="bceb3-170">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   2.  <span data-ttu-id="bceb3-171">**Kaynak anahtarı**.</span><span class="sxs-lookup"><span data-stu-id="bceb3-171">**Resource Key**.</span></span> <span data-ttu-id="bceb3-172">Yerelleştirilmiş kaynak tanımlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="bceb3-172">The localized resource identifier.</span></span>  
  
   3.  <span data-ttu-id="bceb3-173">**Kategori**.</span><span class="sxs-lookup"><span data-stu-id="bceb3-173">**Category**.</span></span> <span data-ttu-id="bceb3-174">Değer türü.</span><span class="sxs-lookup"><span data-stu-id="bceb3-174">The value type.</span></span> <span data-ttu-id="bceb3-175">Bkz: [Yerelleştirme öznitelikleri ve Yorumlar](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="bceb3-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   4.  <span data-ttu-id="bceb3-176">**Okunabilirlik**.</span><span class="sxs-lookup"><span data-stu-id="bceb3-176">**Readability**.</span></span> <span data-ttu-id="bceb3-177">Olup değeri bir yerelleştiriciye tarafından okunabilir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-177">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="bceb3-178">Bkz: [Yerelleştirme öznitelikleri ve Yorumlar](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="bceb3-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   5.  <span data-ttu-id="bceb3-179">**Modifiability'e göre**.</span><span class="sxs-lookup"><span data-stu-id="bceb3-179">**Modifiability**.</span></span> <span data-ttu-id="bceb3-180">Olup değeri bir yerelleştiriciye tarafından değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-180">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="bceb3-181">Bkz: [Yerelleştirme öznitelikleri ve Yorumlar](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="bceb3-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   6.  <span data-ttu-id="bceb3-182">**Açıklamalar**.</span><span class="sxs-lookup"><span data-stu-id="bceb3-182">**Comments**.</span></span> <span data-ttu-id="bceb3-183">Ek açıklama değeri nasıl yerelleştirilmiş belirlemeye yardımcı olması için değeri.</span><span class="sxs-lookup"><span data-stu-id="bceb3-183">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="bceb3-184">Bkz: [Yerelleştirme öznitelikleri ve Yorumlar](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="bceb3-184">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   7.  <span data-ttu-id="bceb3-185">**Değer**.</span><span class="sxs-lookup"><span data-stu-id="bceb3-185">**Value**.</span></span> <span data-ttu-id="bceb3-186">İstenen kültüre Çevrilecek metin değeri.</span><span class="sxs-lookup"><span data-stu-id="bceb3-186">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="bceb3-187">Aşağıdaki tabloda, bu alanlar .csv dosyasını ayrılmış değerleri nasıl eşleştiği gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="bceb3-187">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="bceb3-188">BAML adı</span><span class="sxs-lookup"><span data-stu-id="bceb3-188">BAML name</span></span>|<span data-ttu-id="bceb3-189">Kaynak anahtarı</span><span class="sxs-lookup"><span data-stu-id="bceb3-189">Resource key</span></span>|<span data-ttu-id="bceb3-190">Kategori</span><span class="sxs-lookup"><span data-stu-id="bceb3-190">Category</span></span>|<span data-ttu-id="bceb3-191">Okunabilirlik</span><span class="sxs-lookup"><span data-stu-id="bceb3-191">Readability</span></span>|<span data-ttu-id="bceb3-192">Modifiability'e göre</span><span class="sxs-lookup"><span data-stu-id="bceb3-192">Modifiability</span></span>|<span data-ttu-id="bceb3-193">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bceb3-193">Comments</span></span>|<span data-ttu-id="bceb3-194">Değer</span><span class="sxs-lookup"><span data-stu-id="bceb3-194">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="bceb3-195">HelloApp.g.en US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="bceb3-195">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="bceb3-196">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="bceb3-196">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="bceb3-197">Yoksayma</span><span class="sxs-lookup"><span data-stu-id="bceb3-197">Ignore</span></span>|<span data-ttu-id="bceb3-198">FALSE</span><span class="sxs-lookup"><span data-stu-id="bceb3-198">FALSE</span></span>|<span data-ttu-id="bceb3-199">FALSE</span><span class="sxs-lookup"><span data-stu-id="bceb3-199">FALSE</span></span>||<span data-ttu-id="bceb3-200">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="bceb3-200">#Text1;#Text2</span></span>|
   |<span data-ttu-id="bceb3-201">HelloApp.g.en US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="bceb3-201">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="bceb3-202">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="bceb3-202">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="bceb3-203">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="bceb3-203">None</span></span>|<span data-ttu-id="bceb3-204">TRUE</span><span class="sxs-lookup"><span data-stu-id="bceb3-204">TRUE</span></span>|<span data-ttu-id="bceb3-205">TRUE</span><span class="sxs-lookup"><span data-stu-id="bceb3-205">TRUE</span></span>||<span data-ttu-id="bceb3-206">Merhaba Dünya</span><span class="sxs-lookup"><span data-stu-id="bceb3-206">Hello World</span></span>|
   |<span data-ttu-id="bceb3-207">HelloApp.g.en US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="bceb3-207">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="bceb3-208">Text2:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="bceb3-208">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="bceb3-209">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="bceb3-209">None</span></span>|<span data-ttu-id="bceb3-210">TRUE</span><span class="sxs-lookup"><span data-stu-id="bceb3-210">TRUE</span></span>|<span data-ttu-id="bceb3-211">TRUE</span><span class="sxs-lookup"><span data-stu-id="bceb3-211">TRUE</span></span>||<span data-ttu-id="bceb3-212">Güle güle World</span><span class="sxs-lookup"><span data-stu-id="bceb3-212">Goodbye World</span></span>|
  
   <span data-ttu-id="bceb3-213">Dikkat tüm değerler için **açıklamaları** alanın değer içermesi; bir alan bir değer yoksa boş.</span><span class="sxs-lookup"><span data-stu-id="bceb3-213">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="bceb3-214">Ayrıca ilk satırda öğe okunabilir ve değiştirilebilir ve "Yoksay" sahip olarak dikkat edin, **kategori** değeri, her biri olmadığını değeri yerelleştirilebilir olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-214">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4.  <span data-ttu-id="bceb3-215">Ayrıştırılmış dosyaları, özellikle de büyük dosyalarda yerelleştirilebilir öğelerinde bulunmasını kolaylaştırmak için sıralama veya öğelerini göre filtreleme **kategori**, **okunabilirliği**, ve **Modifiability'egöre**.</span><span class="sxs-lookup"><span data-stu-id="bceb3-215">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="bceb3-216">Örneğin, okunamaz ve değiştirilemeyen değerlere filtre uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bceb3-216">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
<a name="translate_loc_content"></a>   
## <a name="translate-the-localizable-content"></a><span data-ttu-id="bceb3-217">Yerelleştirilebilir İçerik Çevir</span><span class="sxs-lookup"><span data-stu-id="bceb3-217">Translate the Localizable Content</span></span>  
 <span data-ttu-id="bceb3-218">Ayıklanan içeriği çevirmek kullanılabilir olan herhangi bir aracı kullanın.</span><span class="sxs-lookup"><span data-stu-id="bceb3-218">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="bceb3-219">Bunu yapmak için en iyi yolu kaynaklara bir .csv dosyası ve görüntülemeye yazmaktır [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)], çeviri yapmadan değişikliklerini son sütunu (değer).</span><span class="sxs-lookup"><span data-stu-id="bceb3-219">A good way to do this is to write the resources to a .csv file and view them in [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)], making translation changes to the last column (value).</span></span>  
  
<a name="merge_translations"></a>   
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="bceb3-220">LocBaml yeni oluşturmak için kullanın. resources.dll dosyasını</span><span class="sxs-lookup"><span data-stu-id="bceb3-220">Use LocBaml to Generate a New .resources.dll File</span></span>  
 <span data-ttu-id="bceb3-221">LocBaml ile HelloApp.resources.DLL'i tarafından tanımlanan içeriği çevrilmiştir ve özgün uygulamasına birleştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-221">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="bceb3-222">Kullanım **oluşturmak** veya **-g** yeni bir seçenek. resources.dll dosyasını.</span><span class="sxs-lookup"><span data-stu-id="bceb3-222">Use the **generate** or **-g** option to generate a new .resources.dll file.</span></span>  
  
1.  <span data-ttu-id="bceb3-223">Yeni bir HelloApp.resources.dll dosyası oluşturmak için aşağıdaki sözdizimini kullanın.</span><span class="sxs-lookup"><span data-stu-id="bceb3-223">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="bceb3-224">Kültür en-US olarak işaretleyin (/ cul: en-US).</span><span class="sxs-lookup"><span data-stu-id="bceb3-224">Mark the culture as en-US (/cul:en-US).</span></span>  
  
     <span data-ttu-id="bceb3-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span><span class="sxs-lookup"><span data-stu-id="bceb3-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bceb3-226">Giriş dosyası Hello.csv LocBaml.exe yürütülebilir dosya ile aynı dizinde değilse, her iki dosya aynı dizinde, böylece dosyalarından birini taşıyın.</span><span class="sxs-lookup"><span data-stu-id="bceb3-226">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2.  <span data-ttu-id="bceb3-227">Yeni oluşturulan HelloApp.resources.dll dosyanızla C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll dizininde Eski HelloApp.resources.dll dosyasını değiştirin.</span><span class="sxs-lookup"><span data-stu-id="bceb3-227">Replace the old HelloApp.resources.dll file in the C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll directory with your newly created HelloApp.resources.dll file.</span></span>  
  
3.  <span data-ttu-id="bceb3-228">"Hello World" ve "Goodbye World" artık uygulamanızda çevrilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-228">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4.  <span data-ttu-id="bceb3-229">Farklı bir kültüre çevirmek için çevireceğiniz dil kültürünü kullanın.</span><span class="sxs-lookup"><span data-stu-id="bceb3-229">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="bceb3-230">Aşağıdaki örnek, Canadian'a Çevir gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="bceb3-230">The following example shows how to translate to French-Canadian:</span></span>  
  
     <span data-ttu-id="bceb3-231">**LocBaml.exe'yi / HelloApp.resources.dll /trans:Hellofr Oluştur-CA.csv /out:c: \ /cul:fr-CA**</span><span class="sxs-lookup"><span data-stu-id="bceb3-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span></span>  
  
5.  <span data-ttu-id="bceb3-232">Ana uygulama derlemesine aynı derlemede yeni bir uydu derleme barındırmak için yeni bir kültüre özgü klasör oluşturun.</span><span class="sxs-lookup"><span data-stu-id="bceb3-232">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="bceb3-233">French-Canadian için klasörü, fr-CA olabilir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-233">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6.  <span data-ttu-id="bceb3-234">Oluşturulan uydu derlemesini yeni klasöre kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="bceb3-234">Copy the generated satellite assembly to the new folder.</span></span>  
  
7.  <span data-ttu-id="bceb3-235">Yeni bir uydu derleme test etmek için uygulamanızı altında çalıştırılacağı kültürü değiştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-235">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="bceb3-236">Bunu iki yoldan biriyle yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="bceb3-236">You can do this in one of two ways:</span></span>  
  
    -   <span data-ttu-id="bceb3-237">İşletim sisteminizin bölgesel ayarları değiştirin (**Başlat** &#124; **Denetim Masası** &#124; **bölge ve Dil Seçenekleri**).</span><span class="sxs-lookup"><span data-stu-id="bceb3-237">Change your operating system's regional settings (**Start** &#124; **Control Panel** &#124; **Regional and Language Options**).</span></span>  
  
    -   <span data-ttu-id="bceb3-238">Uygulamanızda, App.xaml.cs için aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="bceb3-238">In your application, add the following code to App.xaml.cs:</span></span>  
  
   [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
   [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
   [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>   
## <a name="some-tips-for-using-locbaml"></a><span data-ttu-id="bceb3-239">LocBaml kullanmaya yönelik bazı ipuçları</span><span class="sxs-lookup"><span data-stu-id="bceb3-239">Some Tips for Using LocBaml</span></span>  
  
-   <span data-ttu-id="bceb3-240">Özel denetimler tanımlayabilirsiniz tüm bağımlı derlemeler LocBaml yerel dizine kopyalanır veya GAC içine yüklenmelidir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-240">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="bceb3-241">Okuduğunda API yerelleştirme bağımlı derleme erişimi olması gerektiğinden bu gereklidir [!INCLUDE[TLA#tla_baml](../../../../includes/tlasharptla-baml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bceb3-241">This is necessary because the localization API must have access to the dependent assemblies when it reads the [!INCLUDE[TLA#tla_baml](../../../../includes/tlasharptla-baml-md.md)].</span></span>  
  
-   <span data-ttu-id="bceb3-242">Ana derleme imzalanmışsa, aynı zamanda oluşturulan kaynak DLL yüklenecek sırayla imzalanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-242">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
-   <span data-ttu-id="bceb3-243">Yerelleştirilmiş kaynak sürümü DLL ana derleme ile eşitlenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-243">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>  
  
<a name="Whats_Next"></a>   
## <a name="whats-next"></a><span data-ttu-id="bceb3-244">Yenilikler</span><span class="sxs-lookup"><span data-stu-id="bceb3-244">What's Next</span></span>  
 <span data-ttu-id="bceb3-245">Artık LocBaml aracı kullanmak nasıl temel bir anlayışa sahipsiniz.</span><span class="sxs-lookup"><span data-stu-id="bceb3-245">You should now have a basic understanding of how to use the LocBaml tool.</span></span>  <span data-ttu-id="bceb3-246">Uıd'leri içeren bir dosya olmak.</span><span class="sxs-lookup"><span data-stu-id="bceb3-246">You should be able to make a file that contains Uids.</span></span> <span data-ttu-id="bceb3-247">LocBaml aracı kullanarak, yerelleştirilebilir içerik ayıklamak için dosyayı ayrıştırılacak erişebileceğinizi ve içerik çevrilebilir sonra üretmeden olmalıdır bir. resources.dll dosyasını çevrilen içeriğin birleştirir.</span><span class="sxs-lookup"><span data-stu-id="bceb3-247">By using the LocBaml tool, you should be able to parse a file to extract the localizable content, and after the content is translated, you should be able to generate a .resources.dll file that merges the translated content.</span></span> <span data-ttu-id="bceb3-248">Bu konu, her olası ayrıntı içermez, ancak artık uygulamalarınızı yerelleştirme için LocBaml kullanmak için gerekli bilgi vardır.</span><span class="sxs-lookup"><span data-stu-id="bceb3-248">This topic does not include every possible detail, but you now have the knowledge necessary to use LocBaml for localizing your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bceb3-249">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="bceb3-249">See also</span></span>
- [<span data-ttu-id="bceb3-250">WPF için Genelleştirme</span><span class="sxs-lookup"><span data-stu-id="bceb3-250">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="bceb3-251">Otomatik Düzen Kullanımına Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="bceb3-251">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
