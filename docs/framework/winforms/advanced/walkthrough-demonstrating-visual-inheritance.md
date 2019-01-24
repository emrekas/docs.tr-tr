---
title: 'İzlenecek yol: Görsel devralmayı gösterme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: 3e1aced8ecb4f85dd81c8a928422cbb7d0b10dcd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564337"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="a3e7e-102">İzlenecek yol: Görsel devralmayı gösterme</span><span class="sxs-lookup"><span data-stu-id="a3e7e-102">Walkthrough: Demonstrating Visual Inheritance</span></span>
<span data-ttu-id="a3e7e-103">Görsel devralma temel form üzerinde denetimleri görmek için ve yeni denetimler eklemek için sağlar.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="a3e7e-104">Bu izlenecek yolda temel bir form oluşturun ve bir sınıf kitaplığı derleyin.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="a3e7e-105">Bu sınıf kitaplığı, başka bir projeye içeri aktarmak ve temel formundan devralan yeni bir form oluşturun.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="a3e7e-106">Bu kılavuz boyunca, öğreneceksiniz nasıl yapılır:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-106">During this walkthrough, you will learn how to:</span></span>  
  
-   <span data-ttu-id="a3e7e-107">Taban form içeren bir sınıf kitaplığı projesi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-107">Create a class library project containing a base form.</span></span>  
  
-   <span data-ttu-id="a3e7e-108">Bir düğme türetilmiş sınıflar temel formun özelliklerini değiştirebilirsiniz ekleyin.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-108">Add a button with properties that derived classes of the base form can modify.</span></span>  
  
-   <span data-ttu-id="a3e7e-109">Taban formun devralanlar tarafından değiştirilemez bir düğme ekleyin.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-109">Add a button that cannot be modified by inheritors of the base form.</span></span>  
  
-   <span data-ttu-id="a3e7e-110">Devralınan form içeren bir proje oluşturma `BaseForm`.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-110">Create a project containing a form that inherits from `BaseForm`.</span></span>  
  
 <span data-ttu-id="a3e7e-111">Sonuç olarak, bu izlenecek yol, devralınmış bir form üzerinde özel ve korumalı denetimler arasındaki farkı gösterilecektir.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3e7e-112">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a3e7e-113">Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a3e7e-114">Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a3e7e-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a3e7e-115">Tüm denetimleri, temel bir formdan görsel devralmayı destekler.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-115">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="a3e7e-116">Bu kılavuzda açıklanan senaryo aşağıdaki denetimleri desteklemez:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-116">The following controls do not support the scenario described in this walkthrough:</span></span>  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  <span data-ttu-id="a3e7e-117">Bu devralınan form denetimlerinde her zaman kullandığınız değiştiriciler bağımsız olarak salt okunurdur (`private`, `protected`, veya `public`).</span><span class="sxs-lookup"><span data-stu-id="a3e7e-117">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>  
  
## <a name="scenario-steps"></a><span data-ttu-id="a3e7e-118">Senaryo adımları</span><span class="sxs-lookup"><span data-stu-id="a3e7e-118">Scenario Steps</span></span>  
 <span data-ttu-id="a3e7e-119">İlk adım, bir taban formunu oluşturmaktır.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-119">The first step is to create the base form.</span></span>  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="a3e7e-120">Taban form içeren bir sınıf kitaplığı projesi oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="a3e7e-120">To create a class library project containing a base form</span></span>  
  
1.  <span data-ttu-id="a3e7e-121">Gelen **dosya** menüsünde seçin **yeni**, ardından **proje** açmak için **yeni proje** iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-121">From the **File** menu, choose **New**, and then **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="a3e7e-122">Adlı bir Windows Forms uygulaması oluşturma `BaseFormLibrary`.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-122">Create a Windows Forms application named `BaseFormLibrary`.</span></span>  
  
3.  <span data-ttu-id="a3e7e-123">Standart bir Windows Forms uygulaması yerine bir sınıf kitaplığı oluşturmak için **Çözüm Gezgini**, sağ **BaseFormLibrary** proje düğümünü ve ardından **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-123">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="a3e7e-124">Proje özelliklerini değiştirmek **çıkış türü** gelen **Windows uygulama** için **sınıf kitaplığı**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-124">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>  
  
5.  <span data-ttu-id="a3e7e-125">Gelen **dosya** menüsünde seçin **Tümünü Kaydet** dosya ve proje varsayılan konuma kaydedin.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-125">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>  
  
 <span data-ttu-id="a3e7e-126">Sonraki iki yordam temel forma düğme ekleyin.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-126">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="a3e7e-127">Görsel devralma göstermek için düğmeler farklı erişim düzeyleri ayarlayarak erişmenizi kendi `Modifiers` özellikleri.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-127">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="a3e7e-128">Taban formun devralanlar değiştirebileceğiniz bir düğme eklemek için</span><span class="sxs-lookup"><span data-stu-id="a3e7e-128">To add a button that inheritors of the base form can modify</span></span>  
  
1.  <span data-ttu-id="a3e7e-129">Açık **Form1** Tasarımcısı'nda.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-129">Open **Form1** in the designer.</span></span>  
  
2.  <span data-ttu-id="a3e7e-130">Üzerinde **tüm Windows Formları** sekmesinde **araç kutusu**, çift **düğmesi** forma bir düğme eklemek için.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-130">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="a3e7e-131">Fare getirin ve düğmeyi yeniden boyutlandırmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-131">Use the mouse to position and resize the button.</span></span>  
  
3.  <span data-ttu-id="a3e7e-132">Özellikler penceresinde düğmenin aşağıdaki özellikleri ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-132">In the Properties window, set the following properties of the button:</span></span>  
  
    -   <span data-ttu-id="a3e7e-133">Ayarlama **metin** özelliğini **Say Hello**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-133">Set the **Text** property to **Say Hello**.</span></span>  
  
    -   <span data-ttu-id="a3e7e-134">Ayarlama **(ad)** özelliğini **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-134">Set the **(Name)** property to **btnProtected**.</span></span>  
  
    -   <span data-ttu-id="a3e7e-135">Ayarlama **değiştiriciler** özelliğini **korumalı**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-135">Set the **Modifiers** property to **Protected**.</span></span> <span data-ttu-id="a3e7e-136">Bu devralınan formlar için mümkün kılar **Form1** özelliklerini değiştirmek için **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-136">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>  
  
4.  <span data-ttu-id="a3e7e-137">Çift **Say Hello** için bir olay işleyicisi eklemek için Ekle düğmesine **tıklayın** olay.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-137">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>  
  
5.  <span data-ttu-id="a3e7e-138">Olay işleyicisine aşağıdaki kod satırını ekleyin:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-138">Add the following line of code to the event handler:</span></span>  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="a3e7e-139">Taban formun devralanlar tarafından değiştirilemez bir düğme eklemek için</span><span class="sxs-lookup"><span data-stu-id="a3e7e-139">To add a button that cannot be modified by inheritors of the base form</span></span>  
  
1.  <span data-ttu-id="a3e7e-140">Tıklayarak Tasarım görünümüne geç **Form1.vb [Design], Form1.cs [Design] veya [Design] Form1.jsl** Kod Düzenleyicisi'ni yukarıda veya F7'ye basarak sekmesi.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-140">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>  
  
2.  <span data-ttu-id="a3e7e-141">İkinci bir düğme ekleyin ve özelliklerini aşağıdaki gibi ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-141">Add a second button and set its properties as follows:</span></span>  
  
    -   <span data-ttu-id="a3e7e-142">Ayarlama **metin** özelliğini **Say güle güle**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-142">Set the **Text** property to **Say Goodbye**.</span></span>  
  
    -   <span data-ttu-id="a3e7e-143">Ayarlama **(ad)** özelliğini **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-143">Set the **(Name)** property to **btnPrivate**.</span></span>  
  
    -   <span data-ttu-id="a3e7e-144">Ayarlama **değiştiriciler** özelliğini **özel**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-144">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="a3e7e-145">Bu, devralınan formlar olanaksız kılar **Form1** özelliklerini değiştirmek için **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-145">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>  
  
3.  <span data-ttu-id="a3e7e-146">Çift **Say güle güle** için bir olay işleyicisi eklemek için Ekle düğmesine **tıklayın** olay.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-146">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="a3e7e-147">Aşağıdaki kod satırını olay yordamda yerleştirin:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-147">Place the following line of code in the event procedure:</span></span>  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  <span data-ttu-id="a3e7e-148">Gelen **derleme** menüsünde seçin **derleme BaseForm Kitaplığı** sınıf kitaplığı oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-148">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>  
  
     <span data-ttu-id="a3e7e-149">Kitaplığı oluşturulduktan sonra yeni oluşturduğunuz formundan devralan yeni bir proje oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-149">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="a3e7e-150">Taban form devralan bir formu içeren bir proje oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="a3e7e-150">To create a project containing a form that inherits from the base form</span></span>  
  
1.  <span data-ttu-id="a3e7e-151">Gelen **dosya** menüsünde seçin **Ekle** ardından **yeni proje** açmak için **Yeni Proje Ekle** iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-151">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="a3e7e-152">Adlı bir Windows Forms uygulaması oluşturma `InheritanceTest`.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-152">Create a Windows Forms application named `InheritanceTest`.</span></span>  
  
#### <a name="to-add-an-inherited-form"></a><span data-ttu-id="a3e7e-153">Devralınmış bir form eklemek için</span><span class="sxs-lookup"><span data-stu-id="a3e7e-153">To add an inherited form</span></span>  
  
1.  <span data-ttu-id="a3e7e-154">İçinde **Çözüm Gezgini**, sağ **InheritanceTest** proje, select **Ekle**ve ardından **yeni öğe**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-154">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select **New Item**.</span></span>  
  
2.  <span data-ttu-id="a3e7e-155">İçinde **Yeni Öğe Ekle** iletişim kutusunda **Windows Forms** kategorisi (kategori listesi varsa) ve ardından **devralınan Form** şablonu.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-155">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>  
  
3.  <span data-ttu-id="a3e7e-156">Varsayılan adı bırakın `Form2` ve ardından **Ekle**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-156">Leave the default name of `Form2` and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="a3e7e-157">İçinde **devralma Seçici** iletişim kutusunda **Form1** gelen **BaseFormLibrary** devralır ve form olarak proje **Tamam** .</span><span class="sxs-lookup"><span data-stu-id="a3e7e-157">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>  
  
     <span data-ttu-id="a3e7e-158">Bu, bir formda oluşturur **InheritanceTest** biçiminde türetildiği proje **BaseFormLibrary**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-158">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>  
  
5.  <span data-ttu-id="a3e7e-159">Devralınan form açın (**Form2**) zaten açık değilse, çift tıklayarak tasarımcıda.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-159">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>  
  
     <span data-ttu-id="a3e7e-160">Tasarımcıda bir sembol devralınan düğmeleri sahip (![VisualBasicInheritanceSymbol ekran](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) devralınan belirten kendi üst köşedeki.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-160">In the designer, the inherited buttons have a symbol (![VisualBasicInheritanceSymbol screenshot](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) in their upper corner, indicating they are inherited.</span></span>  
  
6.  <span data-ttu-id="a3e7e-161">Seçin **Say Hello** düğmesine tıklayın ve yeniden boyutlandırma tutamaçları gözlemleyin.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-161">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="a3e7e-162">Bu düğme korunduğu devralanlar taşıyabilir, yeniden boyutlandırabilir, kendi başlığını değiştirme ve diğer değişiklikleri yapın.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-162">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>  
  
7.  <span data-ttu-id="a3e7e-163">Özel seçin **Say güle güle** düğmesi ve yeniden boyutlandırma tutamaçları yok dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-163">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="a3e7e-164">Buna ek olarak **özellikleri** penceresinde bu düğmenin özelliklerini gri bunlar değiştirilemez belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-164">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>  
  
8.  <span data-ttu-id="a3e7e-165">Visual C# kullanıyorsanız:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-165">If you are using Visual C#:</span></span>  
  
    1.  <span data-ttu-id="a3e7e-166">İçinde **Çözüm Gezgini**, sağ **Form1** içinde **InheritanceTest** proje ve ardından **Sil**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-166">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="a3e7e-167">Görüntülenen ileti kutusunda **Tamam** silme işlemini onaylamak için.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-167">In the message box that appears, click **OK** to confirm the deletion.</span></span>  
  
    2.  <span data-ttu-id="a3e7e-168">Program.cs dosyasını açın ve satırını `Application.Run(new Form1());` için `Application.Run(new Form2());`.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-168">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>  
  
9. <span data-ttu-id="a3e7e-169">İçinde **Çözüm Gezgini**, sağ **InheritanceTest** seçin ve proje **başlangıç projesi olarak ayarla**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-169">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>  
  
10. <span data-ttu-id="a3e7e-170">İçinde **Çözüm Gezgini**, sağ **InheritanceTest** seçin ve proje **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-170">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>  
  
11. <span data-ttu-id="a3e7e-171">İçinde **InheritanceTest** özellik sayfalarını **Başlangıç nesnesi** devralınan form olması (**Form2**).</span><span class="sxs-lookup"><span data-stu-id="a3e7e-171">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>  
  
12. <span data-ttu-id="a3e7e-172">Uygulamayı çalıştırmak ve devralınan form davranışını gözlemlemek için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-172">Press F5 to run the application, and observe the behavior of the inherited form.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a3e7e-173">Sonraki Adımlar</span><span class="sxs-lookup"><span data-stu-id="a3e7e-173">Next Steps</span></span>  
 <span data-ttu-id="a3e7e-174">Kullanıcı denetimleri için devralma kadar aynı şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-174">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="a3e7e-175">Yeni bir sınıf kitaplığı projesi açın ve bir kullanıcı denetimi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-175">Open a new class library project and add a user control.</span></span> <span data-ttu-id="a3e7e-176">Bağlı denetimler üzerindeki yerleştirin ve projeyi derleyin.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-176">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="a3e7e-177">Başka bir yeni sınıf kitaplığı projesi açın ve derlenmiş sınıf kitaplığına bir başvuru ekleyin.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-177">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="a3e7e-178">Ayrıca, devralınan bir denetim ekleyerek deneyin (aracılığıyla **yeni öğe ekleme** iletişim kutusu) projeye ve kullanarak **devralma Seçici**.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-178">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="a3e7e-179">Bir kullanıcı denetimi eklemek ve değiştirmek `Inherits` (`:` Visual C#) deyimi.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-179">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="a3e7e-180">Daha fazla bilgi için [nasıl yapılır: Windows Form devralma](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a3e7e-180">For more information, see [How to: Inherit Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e7e-181">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-181">See also</span></span>
- [<span data-ttu-id="a3e7e-182">Nasıl yapılır: Windows Form devralma</span><span class="sxs-lookup"><span data-stu-id="a3e7e-182">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)
- [<span data-ttu-id="a3e7e-183">Windows Forms Görsel Devralma</span><span class="sxs-lookup"><span data-stu-id="a3e7e-183">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
- [<span data-ttu-id="a3e7e-184">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3e7e-184">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
