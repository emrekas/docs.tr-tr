---
title: Visual Studio'da WCF veri hizmeti oluşturma
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: 361582866dabf51665e1dc94fdc49e8710d8ad3e
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091831"
---
# <a name="create-the-data-service"></a><span data-ttu-id="05598-102">Veri hizmetini oluşturma</span><span class="sxs-lookup"><span data-stu-id="05598-102">Create the data service</span></span>

<span data-ttu-id="05598-103">Bu konu başlığında, WCF Veri Hizmetleri kullanıma sunmak için kullandığı örnek veri hizmeti oluşturma bir [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Northwind örnek veritabanını temel alan bir akış.</span><span class="sxs-lookup"><span data-stu-id="05598-103">In this topic, you create a sample data service that uses WCF Data Services to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="05598-104">Görev aşağıdaki temel adımları içerir:</span><span class="sxs-lookup"><span data-stu-id="05598-104">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="05598-105">Bir ASP.NET Web uygulaması oluşturun.</span><span class="sxs-lookup"><span data-stu-id="05598-105">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="05598-106">Veri modeli varlık veri modeli araçları kullanarak tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="05598-106">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="05598-107">Veri Hizmeti Web uygulamasına ekleyin.</span><span class="sxs-lookup"><span data-stu-id="05598-107">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="05598-108">Veri hizmetine erişimi etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="05598-108">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="05598-109">ASP.NET web uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="05598-109">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="05598-110">Visual Studio'da üzerinde **dosya** menüsünde **yeni** > **proje**.</span><span class="sxs-lookup"><span data-stu-id="05598-110">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="05598-111">İçinde **yeni proje** altında Visual Basic veya Visual C# Seç iletişim kutusu **Web** kategori tıklayın ve ardından **ASP.NET Web uygulaması**.</span><span class="sxs-lookup"><span data-stu-id="05598-111">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="05598-112">Girin `NorthwindService` seçin ve proje adı olarak **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="05598-112">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="05598-113">İçinde **yeni ASP.NET Web uygulaması** iletişim kutusunda **boş** seçip **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="05598-113">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="05598-114">(İsteğe bağlı) Web uygulamanız için belirli bağlantı noktası numarası belirtin.</span><span class="sxs-lookup"><span data-stu-id="05598-114">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="05598-115">Not: bağlantı noktası numarası `12345` Bu hızlı başlangıç konuları dizisinde kullanılır.</span><span class="sxs-lookup"><span data-stu-id="05598-115">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="05598-116">İçinde **Çözüm Gezgini**, yeni oluşturduğunuz ASP.NET projeye sağ tıklayın ve ardından **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="05598-116">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="05598-117">Seçin **Web** sekmesini ve değerini ayarlama **belirli bağlantı noktası** metin kutusuna `12345`.</span><span class="sxs-lookup"><span data-stu-id="05598-117">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="05598-118">Veri modelini tanımlama</span><span class="sxs-lookup"><span data-stu-id="05598-118">Define the data model</span></span>

1. <span data-ttu-id="05598-119">İçinde **Çözüm Gezgini**ASP.NET proje adına sağ tıklayın ve ardından **Ekle** > **yeni öğe**.</span><span class="sxs-lookup"><span data-stu-id="05598-119">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="05598-120">İçinde **Yeni Öğe Ekle** iletişim kutusunda **veri** kategori tıklayın ve ardından **ADO.NET varlık veri modeli**.</span><span class="sxs-lookup"><span data-stu-id="05598-120">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="05598-121">Veri modeli için adını `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="05598-121">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="05598-122">İçinde **varlık veri modeli Sihirbazı**seçin **EF veritabanı Tasarımcısından**ve ardından **sonraki**.</span><span class="sxs-lookup"><span data-stu-id="05598-122">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="05598-123">Aşağıdakilerden birini yaparak veri modeli veritabanına bağlanmak ve ardından **sonraki**:</span><span class="sxs-lookup"><span data-stu-id="05598-123">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    -   <span data-ttu-id="05598-124">Önceden yapılandırılmış bir veritabanı bağlantısı yoksa, tıklayın **yeni bağlantı** ve yeni bir bağlantı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="05598-124">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="05598-125">Daha fazla bilgi için [nasıl yapılır: SQL Server veritabanlarına bağlantı oluşturma](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="05598-125">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="05598-126">Bu SQL Server örneği, Northwind örnek veritabanına ekli olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="05598-126">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="05598-127">\- veya -</span><span class="sxs-lookup"><span data-stu-id="05598-127">\- or -</span></span>

    -   <span data-ttu-id="05598-128">Northwind veritabanına bağlanmak için zaten yapılandırılmış bir veritabanı bağlantısı varsa, bu bağlantı bağlantılar listesinden seçin.</span><span class="sxs-lookup"><span data-stu-id="05598-128">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="05598-129">Sihirbazın son sayfasında, veritabanında tüm tabloların onay kutularını işaretleyin ve görünümler ve saklı yordamlar için onay kutularını temizleyin.</span><span class="sxs-lookup"><span data-stu-id="05598-129">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="05598-130">Tıklayın **son** sihirbazı kapatın.</span><span class="sxs-lookup"><span data-stu-id="05598-130">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="05598-131">WCF veri hizmeti oluşturma</span><span class="sxs-lookup"><span data-stu-id="05598-131">Create the WCF data service</span></span>

1. <span data-ttu-id="05598-132">İçinde **Çözüm Gezgini**, ASP.NET proje üzerinde sağ tıklayın ve ardından **Ekle** > **yeni öğe**.</span><span class="sxs-lookup"><span data-stu-id="05598-132">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="05598-133">İçinde **Yeni Öğe Ekle** iletişim kutusunda **WCF veri hizmeti** öğesi şablonundan **Web** kategorisi.</span><span class="sxs-lookup"><span data-stu-id="05598-133">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Visual Studio 2015'te WCF veri hizmeti öğe şablonu](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="05598-135">**WCF veri hizmeti** şablonu kullanılabilir Visual Studio 2015, ancak Visual Studio 2017 içinde değil.</span><span class="sxs-lookup"><span data-stu-id="05598-135">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="05598-136">Hizmet adını yazın `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="05598-136">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="05598-137">Visual Studio, yeni hizmet için XML işaretleme ve kod dosyalarını oluşturur.</span><span class="sxs-lookup"><span data-stu-id="05598-137">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="05598-138">Varsayılan olarak, kod düzenleyicisi penceresi açılır.</span><span class="sxs-lookup"><span data-stu-id="05598-138">By default, the code-editor window opens.</span></span> <span data-ttu-id="05598-139">İçinde **Çözüm Gezgini**, uzantıyı adıyla Northwind hizmette olduğunu *. svc.cs* veya *. svc.vb*.</span><span class="sxs-lookup"><span data-stu-id="05598-139">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="05598-140">Veri Hizmeti için kod içinde açıklamayı değiştirin `/* TODO: put your data source class name here */` veri modelinin varlık kapsayıcı türü olan veri hizmeti tanımlayan sınıf tanımında, bu durumda olduğu `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="05598-140">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="05598-141">Sınıf tanımını aşağıdaki görünmesi gerekir:</span><span class="sxs-lookup"><span data-stu-id="05598-141">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="05598-142">Veri Hizmeti kaynaklarına erişimi etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="05598-142">Enable access to data service resources</span></span>

1. <span data-ttu-id="05598-143">Veri Hizmeti için kodda yer tutucusunu değiştirin `InitializeService` işlevi aşağıdaki:</span><span class="sxs-lookup"><span data-stu-id="05598-143">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="05598-144">Bu yetkili istemcilerin okuma ve yazma erişimi için belirtilen varlık kümesi kaynakları sağlar.</span><span class="sxs-lookup"><span data-stu-id="05598-144">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05598-145">ASP.NET uygulamaya erişebilmesi için herhangi bir istemci veri hizmeti tarafından kullanıma sunulan kaynakları da erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="05598-145">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="05598-146">Bir üretim veri hizmeti kaynaklarına yetkisiz erişimi önlemek için Ayrıca uygulama güvenli hale getirmelisiniz.</span><span class="sxs-lookup"><span data-stu-id="05598-146">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="05598-147">Daha fazla bilgi için [WCF Veri Hizmetleri güvenli hale getirme](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="05598-147">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="05598-148">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="05598-148">Next steps</span></span>

<span data-ttu-id="05598-149">Northwind örnek veritabanını temel alan bir OData akışına sunan yeni bir veri hizmeti başarıyla oluşturdunuz ve ASP.NET Web uygulamasında izinlere sahip istemciler için erişim etkinleştirmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="05598-149">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="05598-150">Ardından, Visual Studio'dan veri hizmeti başlatın ve OData akışına bir Web tarayıcısı üzerinden HTTP GET isteği göndererek erişim:</span><span class="sxs-lookup"><span data-stu-id="05598-150">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="05598-151">Bir web tarayıcısından hizmete erişme</span><span class="sxs-lookup"><span data-stu-id="05598-151">Access the service from a web browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="05598-152">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="05598-152">See also</span></span>

- <span data-ttu-id="05598-153">[ADO.NET varlık veri modeli araçları](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="05598-153">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>