---
title: 'İzlenecek yol: (Visual Studio) DataRepeater denetimindeki verileri görüntüleme'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
ms.openlocfilehash: 4153fecaecc80fc4c40fb6dd9026b07c49ec0fb7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729255"
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="a4a9e-102">İzlenecek yol: (Visual Studio) DataRepeater denetimindeki verileri görüntüleme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="a4a9e-103">Bu izlenecek yolda ilişkili verileri görüntülemek için temel bir başlangıç ve bitiş senaryosu sağlar. bir <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="a4a9e-104">Önkoşul</span><span class="sxs-lookup"><span data-stu-id="a4a9e-104">Prerequisite</span></span>  
 <span data-ttu-id="a4a9e-105">Bu izlenecek yol, Northwind örnek veritabanıyla kurulan gerektirir.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="a4a9e-106">Geliştirme bilgisayarınızda bu veritabanı yoksa Microsoft Download Center'dan gelen indirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="a4a9e-107">Yönergeler için [Downloading Sample Databases](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="a4a9e-107">For instructions, see [Downloading Sample Databases](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="a4a9e-108">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="a4a9e-108">Overview</span></span>  
 <span data-ttu-id="a4a9e-109">Bu kılavuzun ilk bölümü dört ana görevden oluşur:</span><span class="sxs-lookup"><span data-stu-id="a4a9e-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="a4a9e-110">Bir çözüm oluşturma.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="a4a9e-111">Ekleme bir <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="a4a9e-112">Veri kaynağı ekleme.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="a4a9e-113">Verilere bağlı denetimler ekleme.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="a4a9e-114">DataRepeater çözümü oluşturma</span><span class="sxs-lookup"><span data-stu-id="a4a9e-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="a4a9e-115">Bu adımda, bir proje ve çözüm oluşturun.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="a4a9e-116">DataRepeater çözüm oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="a4a9e-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="a4a9e-117">Visual Studio **dosya** menüsünü tıklatın **yeni proje**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="a4a9e-118">İçinde **proje türleri** bölmesinde **yeni proje** iletişim kutusunda **Visual Basic**ve ardından **Windows**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="a4a9e-119">İçinde **şablonları** bölmesinde tıklayın **Windows Forms uygulaması**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="a4a9e-120">İçinde **adı** kutusuna `DataRepeaterApp`.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="a4a9e-121">**Tamam**'ı tıklatın.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="a4a9e-122">Windows Forms Tasarımcısı'nı açar.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="a4a9e-123">Formu Windows Form Tasarımcısı'nda seçin.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="a4a9e-124">İçinde **özellikleri** penceresinde **boyutu** özelliğini `800, 700`.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="a4a9e-125">DataRepeater denetimi ekleme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="a4a9e-126">Bu adımda eklediğiniz bir <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> forma.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="a4a9e-127">DataRepeater denetimi eklemek için</span><span class="sxs-lookup"><span data-stu-id="a4a9e-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="a4a9e-128">Üzerinde **görünümü** menüsünde tıklatın **araç kutusu**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="a4a9e-129">**Araç kutusu** açılır.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="a4a9e-130">Seçin **Visual Basic PowerPacks** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="a4a9e-131">Sürükleme bir <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi **Form1**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="a4a9e-132">Özellikler penceresinde ayarlayın **konumu** özelliğini `0, 25`.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="a4a9e-133">Ayarlama **boyutu** özelliğini `460, 600`.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="a4a9e-134">Veri kaynağı ekleme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-134">Adding a Data Source</span></span>  
 <span data-ttu-id="a4a9e-135">Bu adımda, bir veri kaynağı için eklediğiniz <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="a4a9e-136">Bir veri kaynağı eklemek için</span><span class="sxs-lookup"><span data-stu-id="a4a9e-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="a4a9e-137">Üzerinde **veri** menüsünü tıklatın **veri kaynaklarını Göster**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="a4a9e-138">İçinde **veri kaynakları** penceresinde tıklayın **yeni veri kaynağı Ekle**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="a4a9e-139">Seçin **veritabanı** üzerinde **bir veri kaynağı türü seçin** sayfasında ve ardından **sonraki**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a4a9e-140">Üzerinde **veri bağlantınızı seçin** sayfasında, aşağıdaki adımlardan birini gerçekleştirin:</span><span class="sxs-lookup"><span data-stu-id="a4a9e-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="a4a9e-141">Northwind örnek veritabanıyla kurulan veri bağlantısı açılan listede kullanılabilir durumdaysa bu bağlantıya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="a4a9e-142">-veya-</span><span class="sxs-lookup"><span data-stu-id="a4a9e-142">-or-</span></span>  
  
    -   <span data-ttu-id="a4a9e-143">Tıklayın **yeni bağlantı** yeni bir veri bağlantısı yapılandırmak için.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="a4a9e-144">Daha fazla bilgi için [yeni bağlantı ekleme](/visualstudio/data-tools/add-new-connections).</span><span class="sxs-lookup"><span data-stu-id="a4a9e-144">For more information, see [Add new connections](/visualstudio/data-tools/add-new-connections).</span></span>  
  
5.  <span data-ttu-id="a4a9e-145">Veritabanına parola gerekiyorsa, hassas verileri eklemek ve ardından seçeneğini **sonraki**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4a9e-146">Bir iletişim kutusu görüntülenirse, tıklayın **Evet** dosyayı projenize kaydetmek için.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="a4a9e-147">Tıklayın **sonraki** üzerinde **bağlantı dizesini uygulama yapılandırma dosyasına Kaydet** sayfası.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="a4a9e-148">Genişletin **tabloları** düğümde **veritabanı nesnelerinizi seçin** sayfası.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="a4a9e-149">Yanındaki onay kutularını işaretleyin **müşteriler** ve **siparişler** tablolar ve ardından **son**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="a4a9e-150">**NorthwindDataSet** projenize eklenir ve **müşteriler** ve **siparişler** tablolar görünür **veri kaynakları** penceresi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="a4a9e-151">Verilere bağlı denetimler ekleme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="a4a9e-152">Bu adımda, verilere bağlı denetimler ekleme <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="a4a9e-153">Verilere bağlı denetimler eklemek için</span><span class="sxs-lookup"><span data-stu-id="a4a9e-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="a4a9e-154">İçinde **veri kaynakları** penceresinde için üst düzey düğümü seçmek **müşteriler** tablo.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="a4a9e-155">Tabloya bırakma türünü değiştirme **ayrıntıları** tıklayarak **ayrıntıları** Tablo düğümü aşağı açılan listesinde.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="a4a9e-156">Seçin **müşteriler** tablo düğüm ve öğe şablonu bölgesi (üst bölge) sürükleyin <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="a4a9e-157">A <xref:System.Windows.Forms.BindingNavigator> denetimi forma eklenir ve **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**,  **TableAdapterManager**, ve **CustomersBindingNavigator** bileşenler, bileşen tepsisine eklenir.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="a4a9e-158">Tüm alanları ve bunların ilişkili etiketleri seçin ve bunları öğesi şablon alanının sol kenardaki konumlandırın.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="a4a9e-159">Son beş alanları seçin (**bölge**, **posta kodu**, **Ülke**, **telefon**, ve **faks**) ve kendi ilişkili etiketleri ve yukarı ve sağa ilk altı alanların taşıyın.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="a4a9e-160">Öğe şablonu (üst bölge denetimin) seçin.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="a4a9e-161">Özellikler penceresinde ayarlayın **boyutu** özelliğini `427, 170`.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="a4a9e-162">Bu noktada, yinelenen müşterilerin listesini görüntüleyen bir çalışan uygulamanız var.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="a4a9e-163">Uygulamayı çalıştırmak, verileri değiştirme ve ekleyin veya müşteri kayıtları silmek için F5 tuşuna basabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="a4a9e-164">İsteğe bağlı sonraki adımlarda nasıl özelleştirileceğini öğreneceksiniz <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="a4a9e-165">Sonraki adımlar (isteğe bağlı)</span><span class="sxs-lookup"><span data-stu-id="a4a9e-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="a4a9e-166">Kılavuzun bu bölümü, dört isteğe bağlı görevden oluşur:</span><span class="sxs-lookup"><span data-stu-id="a4a9e-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="a4a9e-167">Görünümünü değiştirme <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="a4a9e-168">Kullanıcıların ekleme veya kayıt silme engelliyor.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="a4a9e-169">Arama özelliği ekleniyor <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="a4a9e-170">Bir ana ve ayrıntı tablosunu ekleme <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="a4a9e-171">DataRepeater denetiminin görünümünü değiştirme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="a4a9e-172">İsteğe bağlı Bu adımda, değiştirdiğiniz `BackColor` , <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> tasarım zamanında denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="a4a9e-173">Ayrıca değişen renklerde satırları görüntülemek ve bir etiketin değiştirmek için kod ekleme `ForeColor` koşullu olarak.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="a4a9e-174">Denetiminin görünümünü değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="a4a9e-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="a4a9e-175">Windows Form Tasarımcısı'nda (alt) ana bölgesi seçin <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="a4a9e-176">Özellikler penceresinde ayarlayın `BackColor` beyaz özelliği.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="a4a9e-177">Çift <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Kod Düzenleyicisi'ni açın.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="a4a9e-178">Kod Düzenleyicisi'nde olay açılan listesinde, **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="a4a9e-179">İçinde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> olay işleyicisi için alternatif aşağıdaki kodu ekleyin `BackColor`:</span><span class="sxs-lookup"><span data-stu-id="a4a9e-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  <span data-ttu-id="a4a9e-180">İçinde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> olay işleyicisi değiştirmek için aşağıdaki kodu ekleyin `ForeColor` bir koşula bağlı bir etiketin:</span><span class="sxs-lookup"><span data-stu-id="a4a9e-180">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  <span data-ttu-id="a4a9e-181">Uygulamayı çalıştırmak ve istediğiniz özelleştirmeleri görmek için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-181">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="a4a9e-182">Kullanıcıların eklemek veya kayıtları silme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-182">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="a4a9e-183">İsteğe bağlı Bu adımda, kullanıcıların ekleme veya kayıt silme engelleyen kod ekleme <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-183">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="a4a9e-184">Ekleme ve silme kayıtlarını kullanıcıların engellemek için</span><span class="sxs-lookup"><span data-stu-id="a4a9e-184">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="a4a9e-185">Windows Form Tasarımcısı'nda, formun Kod Düzenleyicisi'ni açmak için çift tıklayın.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-185">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="a4a9e-186">Aşağıdaki kodu ekleyin `Form_Load` olay:</span><span class="sxs-lookup"><span data-stu-id="a4a9e-186">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  <span data-ttu-id="a4a9e-187">Sınıf adı aşağı açılan listesinde, tıklayın **BindingNavigatorDeleteItem**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-187">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="a4a9e-188">Yöntem adı aşağı açılan listesinde, tıklayın **EnabledChanged**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-188">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="a4a9e-189">Aşağıdaki kodu ekleyin `BindingNavigatorDeleteItem_EnabledChanged` olay işleyicisi:</span><span class="sxs-lookup"><span data-stu-id="a4a9e-189">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="a4a9e-190">Bu adım gereklidir çünkü <xref:System.Windows.Forms.BindingSource> etkinleştirecek **DeleteItem** düğmesi geçerli kayıtta değişiklikleri her zaman.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-190">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="a4a9e-191">Uygulamayı çalıştırmak için F5'e basın.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-191">Press F5 to run the application.</span></span> <span data-ttu-id="a4a9e-192">Dikkat **DeleteItem** düğmesi devre dışıdır ve DELETE tuşuna basarak öğeleri, silemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-192">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="a4a9e-193">DataRepeater denetimine arama özelliği ekleniyor</span><span class="sxs-lookup"><span data-stu-id="a4a9e-193">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="a4a9e-194">İsteğe bağlı Bu adımda, bir değer için arama olanağı uygulamak <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-194">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="a4a9e-195">Arama dizesi bulunursa denetim öğesi görünüme gelene ve değeri içeren öğeyi seçer.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-195">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="a4a9e-196">Arama özelliği eklemek için</span><span class="sxs-lookup"><span data-stu-id="a4a9e-196">To add search capability</span></span>  
  
1.  <span data-ttu-id="a4a9e-197">Sürükleme bir <xref:System.Windows.Forms.TextBox> denetimi **araç kutusu** içeren form üzerine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-197">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="a4a9e-198">Altında konumlandırın <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-198">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="a4a9e-199">Özellikler penceresinde değişiklik **adı** özelliğini **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-199">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="a4a9e-200">Sürükleme bir <xref:System.Windows.Forms.Button> denetimi **araç kutusu** içeren form üzerine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-200">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="a4a9e-201">Altında konumlandırın <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-201">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="a4a9e-202">Özellikler penceresinde değişiklik **adı** özelliğini **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-202">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="a4a9e-203">Değişiklik **metin** özelliğini **arama**.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-203">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="a4a9e-204">Çift <xref:System.Windows.Forms.Button> Kod Düzenleyicisi'ni açmak için Denetim ve aşağıdaki kodu ekleyin `SearchButton_Click` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-204">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  <span data-ttu-id="a4a9e-205">Uygulamayı çalıştırmak için F5'e basın.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-205">Press F5 to run the application.</span></span> <span data-ttu-id="a4a9e-206">Bir müşteri kimliği türü **SearchTextBox** tıklatıp **arama** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-206">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="a4a9e-207">Bir ana ve ayrıntı tablosunu DataRepeater için ekleme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-207">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="a4a9e-208">Bu isteğe bağlı adımda eklediğiniz ikinci <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> her bir müşterinin ilgili siparişlerini görüntülemek üzere Denetim.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-208">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="a4a9e-209">Bir ana ve ayrıntı tablosunu eklemek için</span><span class="sxs-lookup"><span data-stu-id="a4a9e-209">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="a4a9e-210">İkinci sürükleyin <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi **Visual Basic PowerPacks** sekmesinde **araç kutusu** forma.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-210">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="a4a9e-211">Özellikler penceresinde ayarlayın **konumu** özelliğini `465, 25`.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-211">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="a4a9e-212">Ayarlama **boyutu** özelliğini `315, 600`.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-212">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="a4a9e-213">İçinde **veri kaynakları** penceresini genişletin **müşteriler** ayrıntı düğüm için düğüm tablosunu seçip **siparişler** tablo.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-213">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="a4a9e-214">Bırakma türünü bu değiştirme **siparişler** ayrıntıları tabloya tıklayarak **ayrıntıları** Tablo düğümü aşağı açılan listesinde.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-214">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="a4a9e-215">Bu sürükleyin **siparişler** ikinci öğe şablonu bölgesi (üst bölge) tablo düğüme <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-215">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="a4a9e-216">Bir **OrdersBindingSource** bileşeni ve bir **OrdersTableAdapter** bileşeni bileşen tepsisine eklenir.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-216">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="a4a9e-217">Uygulamayı çalıştırmak için F5'e basın.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-217">Press F5 to run the application.</span></span> <span data-ttu-id="a4a9e-218">İlk her müşteri seçtiğinizde, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetlemek, siparişler, müşteri görüntülenir için ikinci <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-218">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a9e-219">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a4a9e-219">See also</span></span>
- [<span data-ttu-id="a4a9e-220">DataRepeater Denetimine Giriş</span><span class="sxs-lookup"><span data-stu-id="a4a9e-220">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="a4a9e-221">Nasıl yapılır: DataRepeater denetiminde bağlı verileri görüntüleme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-221">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="a4a9e-222">Nasıl yapılır: DataRepeater denetimindeki ilişkisiz denetimleri görüntüleme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-222">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="a4a9e-223">Nasıl yapılır: DataRepeater denetimi düzenini değiştirme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-223">How to: Change the Layout of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="a4a9e-224">Nasıl yapılır: DataRepeater denetiminde öğe üstbilgilerini görüntüleme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-224">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="a4a9e-225">Nasıl yapılır: DataRepeater denetiminde veri arama</span><span class="sxs-lookup"><span data-stu-id="a4a9e-225">How to: Search Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="a4a9e-226">Nasıl yapılır: (Visual Studio) iki DataRepeater denetimi kullanarak ana/ayrıntı formu oluşturma</span><span class="sxs-lookup"><span data-stu-id="a4a9e-226">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [<span data-ttu-id="a4a9e-227">Nasıl yapılır: DataRepeater denetiminin görünümünü değiştirme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-227">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="a4a9e-228">Nasıl yapılır: DataRepeater öğelerini eklemeyi ve silmeyi devre dışı bırak</span><span class="sxs-lookup"><span data-stu-id="a4a9e-228">How to: Disable Adding and Deleting DataRepeater Items</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)
- [<span data-ttu-id="a4a9e-229">DataRepeater Denetiminde Sorun Giderme</span><span class="sxs-lookup"><span data-stu-id="a4a9e-229">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
