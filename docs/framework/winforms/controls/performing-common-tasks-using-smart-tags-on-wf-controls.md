---
title: 'İzlenecek yol: Windows Forms Denetimlerindeki Akıllı Etiketleri Kullanarak Ortak Görevleri Gerçekleştirme'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: a93402be30cb461ac6a0ed9daa4a684598a85da1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932606"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="3d2cf-102">İzlenecek yol: Windows Forms Denetimlerindeki Akıllı Etiketleri Kullanarak Ortak Görevleri Gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="3d2cf-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="3d2cf-103">Windows Forms uygulamanız için formlar ve denetimler oluşturmak gibi art arda gerçekleştirir çok sayıda görev vardır.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="3d2cf-104">Karşınıza çıkacak sık gerçekleştirilen görevlerin bazıları şunlardır:</span><span class="sxs-lookup"><span data-stu-id="3d2cf-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
- <span data-ttu-id="3d2cf-105">Ekleyerek veya bir sekme üzerindeki kaldırarak bir <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
- <span data-ttu-id="3d2cf-106">Bir denetim için üst yerleştirme.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-106">Docking a control to its parent.</span></span>  
  
- <span data-ttu-id="3d2cf-107">Yönünü değiştirme bir <xref:System.Windows.Forms.SplitContainer> denetimi.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="3d2cf-108">Geliştirme hızlandırmak için pek çok denetimi tasarım zamanında bu tek gibi genel görevleri gerçekleştirmenize olanak tanıyan bağlama duyarlı menüler şunlardır akıllı etiketler sunar.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="3d2cf-109">Bu görevleri adlı *akıllı etiket fiilleri*.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="3d2cf-110">Akıllı etiketler Tasarımcısı'nda yaşam süresi'için bir denetim örneğine bağlı kalır ve her zaman kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="3d2cf-111">Bu kılavuzda gösterilen görevler aşağıdakileri içerir:</span><span class="sxs-lookup"><span data-stu-id="3d2cf-111">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="3d2cf-112">Bir Windows Forms projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="3d2cf-112">Creating a Windows Forms project</span></span>  
  
- <span data-ttu-id="3d2cf-113">Akıllı etiketleri kullanarak</span><span class="sxs-lookup"><span data-stu-id="3d2cf-113">Using smart tags</span></span>  
  
- <span data-ttu-id="3d2cf-114">Akıllı etiketler devre dışı bırakma ve etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="3d2cf-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="3d2cf-115">İşlemi tamamladığınızda, bu önemli bir düzen özellikleri tarafından oynadığı rol, bir anlayışa sahip olacaksınız.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d2cf-116">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3d2cf-117">Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3d2cf-118">Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3d2cf-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="3d2cf-119">Projeyi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="3d2cf-119">Creating the Project</span></span>  
 <span data-ttu-id="3d2cf-120">İlk adım projeyi oluşturmak ve formu ayarlamaktır.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="3d2cf-121">Proje oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="3d2cf-121">To create the project</span></span>  
  
1. <span data-ttu-id="3d2cf-122">"SmartTagsExample" adlı bir Windows tabanlı uygulama projesi oluşturun (**dosya** > **yeni** > **proje**  >   **Visual C#** veya **Visual Basic** > **Klasik Masaüstü** > **Windows Forms uygulamalarındaki**).</span><span class="sxs-lookup"><span data-stu-id="3d2cf-122">Create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="3d2cf-123">Formda seçin **Windows Form Tasarımcısı**.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-123">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="3d2cf-124">Akıllı etiketleri kullanarak</span><span class="sxs-lookup"><span data-stu-id="3d2cf-124">Using Smart Tags</span></span>  
 <span data-ttu-id="3d2cf-125">Akıllı etiketler her zaman bunları teklif denetimleri tasarım zamanında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-125">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="3d2cf-126">Akıllı etiketleri kullanma</span><span class="sxs-lookup"><span data-stu-id="3d2cf-126">To use smart tags</span></span>  
  
1. <span data-ttu-id="3d2cf-127">Sürükleme bir <xref:System.Windows.Forms.TabControl> gelen **araç kutusu** formunuza.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-127">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="3d2cf-128">Akıllı etiket karakterini unutmayın (![akıllı etiket karakterini](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) üzerinde yan, görüntülenen <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-128">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2. <span data-ttu-id="3d2cf-129">Akıllı etiket karakterini tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-129">Click the smart-tag glyph.</span></span> <span data-ttu-id="3d2cf-130">Glif yanında görüntülenen kısayol menüsünden seçin **Sekme Ekle** öğesi.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-130">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="3d2cf-131">Yeni bir sekme sayfası eklenir gözlemleyin <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-131">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3. <span data-ttu-id="3d2cf-132">Sürükleme bir <xref:System.Windows.Forms.TableLayoutPanel> denetimi **araç kutusu** formunuza.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-132">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4. <span data-ttu-id="3d2cf-133">Akıllı etiket karakterini tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-133">Click the smart-tag glyph.</span></span> <span data-ttu-id="3d2cf-134">Glif yanında görüntülenen kısayol menüsünden seçin **Sütun Ekle** öğesi.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-134">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="3d2cf-135">Yeni bir sütun eklenir gözlemleyin <xref:System.Windows.Forms.TableLayoutPanel> denetimi.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-135">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5. <span data-ttu-id="3d2cf-136">Sürükleme bir <xref:System.Windows.Forms.SplitContainer> denetimi **araç kutusu** formunuza.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-136">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6. <span data-ttu-id="3d2cf-137">Akıllı etiket karakterini tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-137">Click the smart-tag glyph.</span></span> <span data-ttu-id="3d2cf-138">Glif yanında görüntülenen kısayol menüsünden seçin **Yatay bölümlendirici yönlendirmesini** öğesi.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-138">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="3d2cf-139">Mesajının görüntülendiğini görün <xref:System.Windows.Forms.SplitContainer> denetimin ayırıcıyı, artık yatay odaklıdır.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-139">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d2cf-140">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3d2cf-140">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="3d2cf-141">[İzlenecek yol: Bir Windows Formları bileşenine akıllı etiket ekleme](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="3d2cf-141">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
