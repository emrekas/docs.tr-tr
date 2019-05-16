---
title: Derleme bir C# Visual Studio 2017 ile .NET Standard kitaplığı
description: Visual Studio 2017 kullanılarak C# dilinde yazılmış bir .NET Standard sınıf kitaplığı oluşturmayı öğrenin.
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 440ef2ed398b22262923422efd7f1259e3ee9b74
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633699"
---
# <a name="build-a-net-standard-library-with-c-and-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="be95d-103">Bir .NET Standard kitaplığı ile derleme C# ve Visual Studio 2017'de .NET Core SDK'sı</span><span class="sxs-lookup"><span data-stu-id="be95d-103">Build a .NET Standard library with C# and the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="be95d-104">A *sınıf kitaplığı* türlerini ve bir uygulama tarafından çağrılan yöntemlere tanımlar.</span><span class="sxs-lookup"><span data-stu-id="be95d-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="be95d-105">.NET Standard 2.0 hedefleyen bir sınıf kitaplığı, .NET Standard sürümünü destekleyen herhangi bir .NET uygulaması tarafından çağrılacak kitaplığınızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="be95d-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="be95d-106">Sınıf kitaplığınıza bitirdikten sonra bir üçüncü taraf bileşeni veya bir veya daha fazla uygulama ile birlikte gelen bir bileşeni olarak dahil etmek isteyip istemediğinizi olarak dağıtmak isteyip istemediğinize karar verebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="be95d-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="be95d-107">.NET Standard sürümleri ve destekledikleri platformlar listesi için bkz: [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="be95d-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="be95d-108">Bu konuda, tek bir dize işleme yöntemini içeren bir basit bir yardımcı program kitaplığı oluşturacaksınız.</span><span class="sxs-lookup"><span data-stu-id="be95d-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="be95d-109">Olarak uygulayacaksınız bir [genişletme yöntemi](../../csharp/programming-guide/classes-and-structs/extension-methods.md) üyesi değilmiş gibi çağırabilirsiniz <xref:System.String> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="be95d-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="be95d-110">Bir sınıf kitaplığı çözüm oluşturma</span><span class="sxs-lookup"><span data-stu-id="be95d-110">Creating a class library solution</span></span>

<span data-ttu-id="be95d-111">Sınıf kitaplığı projenizi ve ilgili projeleri çözüm oluşturmaya başlayın.</span><span class="sxs-lookup"><span data-stu-id="be95d-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="be95d-112">Bir Visual Studio çözümü yalnızca bir veya daha fazla proje için kapsayıcı işlevi görür.</span><span class="sxs-lookup"><span data-stu-id="be95d-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="be95d-113">Çözümü oluşturmak için:</span><span class="sxs-lookup"><span data-stu-id="be95d-113">To create the solution:</span></span>

1. <span data-ttu-id="be95d-114">Visual Studio menü çubuğunda **dosya** > **yeni** > **proje**.</span><span class="sxs-lookup"><span data-stu-id="be95d-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="be95d-115">İçinde **yeni proje** iletişim kutusunda genişletin **diğer proje türleri** düğüm ve select **Visual Studio çözümleri**.</span><span class="sxs-lookup"><span data-stu-id="be95d-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="be95d-116">Seçin ve "ClassLibraryProjects" çözümünü arlandırın **Tamam** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="be95d-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Yeni Proje iletişim kutusu ile vurgulanmış yeni bir boş çözüm](./media/library-with-visual-studio/new-project-dialog.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="be95d-118">Sınıf kitaplığı projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="be95d-118">Creating the class library project</span></span>

<span data-ttu-id="be95d-119">Sınıf kitaplığı projenizi oluşturun:</span><span class="sxs-lookup"><span data-stu-id="be95d-119">Create your class library project:</span></span>

1. <span data-ttu-id="be95d-120">İçinde **Çözüm Gezgini**, sağ **ClassLibraryProjects** çözüm dosyası ve bağlam menüsünden seçin **Ekle** > **yeni Proje**.</span><span class="sxs-lookup"><span data-stu-id="be95d-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="be95d-121">İçinde **Yeni Proje Ekle** iletişim kutusunda genişletin **Visual C#** düğümünü seçip **.NET Standard** düğümünü ve ardından **sınıf kitaplığı (.NET Standard)** proje şablonu.</span><span class="sxs-lookup"><span data-stu-id="be95d-121">In the **Add New Project** dialog, expand the **Visual C#** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="be95d-122">İçinde **adı** metin kutusunda, projenin adı "StringLibrary" girin.</span><span class="sxs-lookup"><span data-stu-id="be95d-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="be95d-123">Seçin **Tamam** sınıf kitaplığı projesi oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="be95d-123">Select **OK** to create the class library project.</span></span>

   ![Yeni kitaplık projesi iletişim kutusu Ekle](./media/library-with-visual-studio/add-new-library-project.png)

   <span data-ttu-id="be95d-125">Kod penceresi, ardından Visual Studio geliştirme ortamında açar.</span><span class="sxs-lookup"><span data-stu-id="be95d-125">The code window then opens in the Visual Studio development environment.</span></span>

   ![Visual Studio uygulama penceresinin varsayılan sınıf kitaplığı şablonu kodu gösterme](./media/library-with-visual-studio/string-library-project.png)

1. <span data-ttu-id="be95d-127">Kitaplığımızı .NET Standard'ın doğru sürümü hedeflediğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="be95d-127">Check to make sure that our library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="be95d-128">Kitaplığı projesinde sağ **Çözüm Gezgini** windows, ardından **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="be95d-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="be95d-129">**Hedef Framework'ü** metin kutusuna .NET Standard 2.0 hedeflediğiniz gösterir.</span><span class="sxs-lookup"><span data-stu-id="be95d-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Sınıf kitaplığı için proje özellikleri](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="be95d-131">Kod penceresinde kodu aşağıdaki kodla değiştirin ve dosyayı kaydedin:</span><span class="sxs-lookup"><span data-stu-id="be95d-131">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="be95d-132">Sınıf Kitaplığı `UtilityLibraries.StringLibrary`, adında bir yöntem içeriyorsa `StartsWithUpper`, döndüren bir <xref:System.Boolean> geçerli dize örneğinde bir büyük harf karakteri ile başlayan olup olmadığını gösteren değer.</span><span class="sxs-lookup"><span data-stu-id="be95d-132">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="be95d-133">Unicode standardı, küçük harfli karakterlerden büyük harf karakterler ayırır.</span><span class="sxs-lookup"><span data-stu-id="be95d-133">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="be95d-134"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> Yöntemi döndürür `true` bir karakterin büyük harf ise.</span><span class="sxs-lookup"><span data-stu-id="be95d-134">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="be95d-135">Menü çubuğunda, seçin **derleme** > **Çözümü Derle**.</span><span class="sxs-lookup"><span data-stu-id="be95d-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="be95d-136">Projenin hatasız derlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="be95d-136">The project should compile without error.</span></span>

   ![Derleme başarılı olduğunu gösteren çıkış bölmesi](./media/library-with-visual-studio/output-pane-successful-build.png)

## <a name="next-step"></a><span data-ttu-id="be95d-138">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="be95d-138">Next step</span></span>

<span data-ttu-id="be95d-139">Kitaplık başarıyla oluşturdunuz.</span><span class="sxs-lookup"><span data-stu-id="be95d-139">You've successfully built the library.</span></span> <span data-ttu-id="be95d-140">Yöntemlerinden herhangi biri olarak adlandırılan henüz olduğundan, beklendiği gibi çalıştığını bilmiyorum.</span><span class="sxs-lookup"><span data-stu-id="be95d-140">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="be95d-141">Kullanarak test etmek için kitaplığınızın geliştirme sonraki adımı olan bir [Birim Test projesi](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="be95d-141">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>
