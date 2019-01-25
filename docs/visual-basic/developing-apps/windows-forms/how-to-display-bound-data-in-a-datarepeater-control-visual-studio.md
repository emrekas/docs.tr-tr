---
title: 'Nasıl yapılır: Görüntüleme (Visual Studio) DataRepeater denetiminde veri bağlama'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: dbcd814edb78c54ce5629a1a8761142674fe6135
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684625"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="64278-102">Nasıl yapılır: Görüntüleme (Visual Studio) DataRepeater denetiminde veri bağlama</span><span class="sxs-lookup"><span data-stu-id="64278-102">How to: Display Bound Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="64278-103">En yaygın kullanımı <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> bir veritabanı veya başka bir veri kaynağı ilişkili verileri görüntülemek için denetimidir.</span><span class="sxs-lookup"><span data-stu-id="64278-103">The most common use of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control is to display bound data from a database or other data source.</span></span>  
  
 <span data-ttu-id="64278-104">Bağlama denetimleri ek olarak, statik bir etiket ya da her öğesine yinelenen görüntü gibi başka denetimler eklemek isteyebilirsiniz <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="64278-104">In addition to bound controls, you may want to add other controls, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="64278-105">Daha fazla bilgi için [nasıl yapılır: DataRepeater denetiminde denetimleri ilişkisiz](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="64278-105">For more information, see [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
 <span data-ttu-id="64278-106">Ayarlayarak çalışma zamanında bir veri kaynağına bağlayabilirsiniz <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> özelliğini `True` ve bir veri kaynağına atama <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="64278-106">You can also bind to a data source at run time by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> property to `True` and assigning a data source to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> property.</span></span> <span data-ttu-id="64278-107">Bu durumda, tüm etkileşimi veri kaynağı ile yönetmek gerekir.</span><span class="sxs-lookup"><span data-stu-id="64278-107">In this case, you will need to manage all interaction with the data source.</span></span> <span data-ttu-id="64278-108">Daha fazla bilgi için [DataRepeater denetiminde sanal mod](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="64278-108">For more information, see [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a><span data-ttu-id="64278-109">Verilere bağlı DataRepeater oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="64278-109">To create a data-bound DataRepeater</span></span>  
  
1.  <span data-ttu-id="64278-110">Sürükleme bir <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi **Visual Basic PowerPacks** sekmesinde **araç kutusu** bir form veya kapsayıcı denetlemek için.</span><span class="sxs-lookup"><span data-stu-id="64278-110">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="64278-111">Boyut ve konum tutamaçları boyutuna sürükleyin ve denetimi konumlandırın.</span><span class="sxs-lookup"><span data-stu-id="64278-111">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="64278-112">Denetim dikdörtgen iki bölgeleri olduğuna dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="64278-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="64278-113">Üst bölgenin *öğe şablonu*; şablonuna eklenen denetimler yinelenen her öğesinde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> çalışma zamanında denetim.</span><span class="sxs-lookup"><span data-stu-id="64278-113">The upper region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="64278-114">Alt bölgenin *Görünüm penceresi*öğeleri burada görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="64278-114">The lower region is the *viewport*, where the items will be displayed.</span></span>  
  
     <span data-ttu-id="64278-115">Ayrıca boyutu ve denetimi veya öğe şablonu değiştirerek konumunu **boyutu** ve **konumu** özellikleri Özellikler penceresinde.</span><span class="sxs-lookup"><span data-stu-id="64278-115">You can also size and position the control or the item template by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="64278-116">Üzerinde **veri** menüsünü tıklatın **veri kaynaklarını Göster**.</span><span class="sxs-lookup"><span data-stu-id="64278-116">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64278-117">Varsa **veri kaynakları** penceresi boş ise, bir veri kaynağı ekleyin.</span><span class="sxs-lookup"><span data-stu-id="64278-117">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="64278-118">Daha fazla bilgi için [yeni veri kaynağı ekleme](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="64278-118">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="64278-119">İçinde **veri kaynakları** penceresinde bağlamak istediğiniz verileri içeren bir tablo için üst düzey düğümü seçin.</span><span class="sxs-lookup"><span data-stu-id="64278-119">In the **Data Sources** window, select the top-level node for the table that contains the data that you want to bind.</span></span>  
  
5.  <span data-ttu-id="64278-120">Tabloya bırakma türünü değiştirme `Details` tıklayarak `Details` Tablo düğümü aşağı açılan listesinde.</span><span class="sxs-lookup"><span data-stu-id="64278-120">Change the drop type of the table to `Details` by clicking `Details` in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="64278-121">Tablo düğümü seçin ve öğe şablonu bölgesi sürükleyin <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> denetimi.</span><span class="sxs-lookup"><span data-stu-id="64278-121">Select the table node and drag it onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="64278-122">Tür denetimler her alan için görüntülenen belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="64278-122">You can specify which types of controls are displayed for each field.</span></span> <span data-ttu-id="64278-123">Daha fazla bilgi için [veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimi ayarlama](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span><span class="sxs-lookup"><span data-stu-id="64278-123">For more information, see [Set the control to be created when dragging from the Data Sources window](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64278-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="64278-124">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="64278-125">DataRepeater Denetimine Giriş</span><span class="sxs-lookup"><span data-stu-id="64278-125">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="64278-126">Nasıl yapılır: DataRepeater denetimindeki ilişkisiz denetimleri görüntüleme</span><span class="sxs-lookup"><span data-stu-id="64278-126">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="64278-127">Nasıl yapılır: (Visual Studio) iki DataRepeater denetimi kullanarak ana/ayrıntı formu oluşturma</span><span class="sxs-lookup"><span data-stu-id="64278-127">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [<span data-ttu-id="64278-128">Nasıl yapılır: DataRepeater denetiminin görünümünü değiştirme</span><span class="sxs-lookup"><span data-stu-id="64278-128">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="64278-129">DataRepeater Denetiminde Sorun Giderme</span><span class="sxs-lookup"><span data-stu-id="64278-129">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
