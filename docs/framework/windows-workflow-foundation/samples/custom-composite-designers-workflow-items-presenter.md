---
title: Özel Bileşik Tasarımcılar - İş Akışı Öğeleri Sunucu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
ms.openlocfilehash: f4db3325081a820a37a8791849d2ad9697d15151
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118111"
---
# <a name="custom-composite-designers---workflow-items-presenter"></a><span data-ttu-id="048ac-102">Özel Bileşik Tasarımcılar - İş Akışı Öğeleri Sunucu</span><span class="sxs-lookup"><span data-stu-id="048ac-102">Custom Composite Designers - Workflow Items Presenter</span></span>
<span data-ttu-id="048ac-103"><xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> Düzenlemek kapsanan öğelerin koleksiyonunu için izin veren WF Tasarımcı programlama modeli içinde bir anahtar türü.</span><span class="sxs-lookup"><span data-stu-id="048ac-103">The <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> is a key type in the WF designer programming model that allows for the editing of a collection of contained elements.</span></span> <span data-ttu-id="048ac-104">Bu örnek, düzenlenebilir bir koleksiyon ortaya çıkarır bir etkinlik Tasarımcısı oluşturma gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="048ac-104">This sample shows how to build an activity designer that surfaces such an editable collection.</span></span>

 <span data-ttu-id="048ac-105">Bu örnek gösterir:</span><span class="sxs-lookup"><span data-stu-id="048ac-105">This sample demonstrates:</span></span>

-   <span data-ttu-id="048ac-106">Özel Etkinlik Tasarımcısı ile oluşturma bir <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="048ac-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span>

-   <span data-ttu-id="048ac-107">Bir etkinlik Tasarımcısı ile "daraltılmış" ve "genişletilmiş" Görünüm oluşturuluyor.</span><span class="sxs-lookup"><span data-stu-id="048ac-107">Creating an activity designer with a "collapsed" and "expanded" view.</span></span>

-   <span data-ttu-id="048ac-108">Yeniden barındırılan bir uygulamanın varsayılan tasarımcıda geçersiz kılma.</span><span class="sxs-lookup"><span data-stu-id="048ac-108">Overriding a default designer in a rehosted application.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="048ac-109">Ayarlamak için derleme ve örneği çalıştırma</span><span class="sxs-lookup"><span data-stu-id="048ac-109">To set up, build, and run the sample</span></span>

1.  <span data-ttu-id="048ac-110">Açık **UsingWorkflowItemsPresenter.sln** için C# veya VB Visual Studio 2010 için örnek çözümü.</span><span class="sxs-lookup"><span data-stu-id="048ac-110">Open the **UsingWorkflowItemsPresenter.sln** sample solution for C# or for VB in Visual Studio 2010.</span></span>

2.  <span data-ttu-id="048ac-111">Derleme ve çözümü çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="048ac-111">Build and run the solution.</span></span> <span data-ttu-id="048ac-112">Yeniden barındırılan iş akışı Tasarımcısı uygulamayı açmalıdır ve etkinlikleri tuvale sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="048ac-112">A rehosted workflow designer application should open, and you can drag activities onto the canvas.</span></span>

## <a name="sample-highlights"></a><span data-ttu-id="048ac-113">Örnek öne çıkan özellikleri</span><span class="sxs-lookup"><span data-stu-id="048ac-113">Sample Highlights</span></span>
 <span data-ttu-id="048ac-114">Bu örneğe yönelik kodun aşağıda gösterilmiştir:</span><span class="sxs-lookup"><span data-stu-id="048ac-114">The code for this sample shows the following:</span></span>

-   <span data-ttu-id="048ac-115">Bir tasarımcı etkinlik oluşturulmuştur:</span><span class="sxs-lookup"><span data-stu-id="048ac-115">The activity a designer is built for:</span></span>  `Parallel`

-   <span data-ttu-id="048ac-116">Özel Etkinlik Tasarımcısı ile oluşturulmasını bir <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="048ac-116">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span> <span data-ttu-id="048ac-117">Tablonuzu gereken bazı noktalar:</span><span class="sxs-lookup"><span data-stu-id="048ac-117">A few things to point out:</span></span>

    -   <span data-ttu-id="048ac-118">WPF verilerini bağlama bağlamak için kullanımına dikkat edin `ModelItem.Branches`.</span><span class="sxs-lookup"><span data-stu-id="048ac-118">Note the use of WPF data binding to bind to `ModelItem.Branches`.</span></span> `ModelItem` <span data-ttu-id="048ac-119">özelliği açıktır `WorkflowElementDesigner` Tasarımcı kullanılmıştır, bu durumda, arka plandaki nesneye başvuran bizim `Parallel`.</span><span class="sxs-lookup"><span data-stu-id="048ac-119">is the property on `WorkflowElementDesigner` that refers to the underlying object the designer is being used for, in this case, our `Parallel`.</span></span>

    -   <span data-ttu-id="048ac-120"><xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> Koleksiyondaki bireysel öğeleri arasında görüntülemek için bir görsel yerleştirme için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="048ac-120">The <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> can be used to put a visual to display between the individual items in the collection.</span></span>

    -   <xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> <span data-ttu-id="048ac-121">koleksiyondaki öğelerin düzeni belirlemek için sağlanan bir şablonudur.</span><span class="sxs-lookup"><span data-stu-id="048ac-121">is a template that can be provided to determine the layout of the items in the collection.</span></span> <span data-ttu-id="048ac-122">Bu durumda, yatay yığın paneli kullanılır.</span><span class="sxs-lookup"><span data-stu-id="048ac-122">In this case, a horizontal stack panel is used.</span></span>

 <span data-ttu-id="048ac-123">Bu aşağıdaki kod örneği bunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="048ac-123">This following example code shows this.</span></span>

```xaml
<sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                              Items="{Binding Path=ModelItem.Branches}">
    <sad:WorkflowItemsPresenter.SpacerTemplate>
      <DataTemplate>
        <Ellipse Width="10" Height="10" Fill="Black"/>
      </DataTemplate>
    </sad:WorkflowItemsPresenter.SpacerTemplate>
    <sad:WorkflowItemsPresenter.ItemsPanel>
      <ItemsPanelTemplate>
        <StackPanel Orientation="Horizontal"/>
      </ItemsPanelTemplate>
    </sad:WorkflowItemsPresenter.ItemsPanel>
  </sad:WorkflowItemsPresenter>
```

-   <span data-ttu-id="048ac-124">İlişkilendirmesini gerçekleştirmek `DesignerAttribute` için `Parallel` türü ve ardından çıkış öznitelikleri bildirdi.</span><span class="sxs-lookup"><span data-stu-id="048ac-124">Perform an association of the `DesignerAttribute` to the `Parallel` type and then output the attributes reported.</span></span>

    -   <span data-ttu-id="048ac-125">İlk olarak, tüm varsayılan tasarımcıları kaydedin.</span><span class="sxs-lookup"><span data-stu-id="048ac-125">First, register all of the default designers.</span></span>

 <span data-ttu-id="048ac-126">Kod örneği verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="048ac-126">The following is the code example.</span></span>

```csharp
// register metadata
(new DesignerMetadata()).Register();
RegisterCustomMetadata();
```

```vb
' register metadata
Dim metadata = New DesignerMetadata()
metadata.Register()
' register custom metadata
RegisterCustomMetadata()
```

    -   <span data-ttu-id="048ac-127">Ardından, paralel olarak geçersiz kılma `RegisterCustomMetadata` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="048ac-127">Then, override the parallel in `RegisterCustomMetadata` method.</span></span>

 <span data-ttu-id="048ac-128">Aşağıdaki kod, C# ve Visual Basic'te bu gösterir.</span><span class="sxs-lookup"><span data-stu-id="048ac-128">The following code shows this in C# and Visual Basic.</span></span>

```csharp
void RegisterCustomMetadata()
{
      AttributeTableBuilder builder = new AttributeTableBuilder();
      builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
      MetadataStore.AddAttributeTable(builder.CreateTable());
}
```

```vb
Sub RegisterCustomMetadata()
   Dim builder As New AttributeTableBuilder()
   builder.AddCustomAttributes(GetType(Parallel), New DesignerAttribute(GetType(CustomParallelDesigner)))
   MetadataStore.AddAttributeTable(builder.CreateTable())
End Sub
```

-   <span data-ttu-id="048ac-129">Son olarak, farklı veri şablonları ve temel uygun şablonu seçmek için Tetikleyiciler kullanımına dikkat edin `IsRootDesigner` özelliği.</span><span class="sxs-lookup"><span data-stu-id="048ac-129">Finally, note the use of differing data templates and triggers to select the appropriate template based on the `IsRootDesigner` property.</span></span>

 <span data-ttu-id="048ac-130">Kod örneği verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="048ac-130">The following is the code example.</span></span>

```xaml
<sad:ActivityDesigner x:Class="Microsoft.Samples.CustomParallelDesigner"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:sad="clr-namespace:System.Activities.Design;assembly=System.Activities.Design"
    xmlns:sadv="clr-namespace:System.Activities.Design.View;assembly=System.Activities.Design">
  <sad:ActivityDesigner.Resources>
    <DataTemplate x:Key="Expanded">
      <StackPanel>
        <TextBlock>This is the Expanded View</TextBlock>
        <sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                                    Items="{Binding Path=ModelItem.Branches}">
          <sad:WorkflowItemsPresenter.SpacerTemplate>
            <DataTemplate>
              <Ellipse Width="10" Height="10" Fill="Black"/>
            </DataTemplate>
          </sad:WorkflowItemsPresenter.SpacerTemplate>
          <sad:WorkflowItemsPresenter.ItemsPanel>
            <ItemsPanelTemplate>
              <StackPanel Orientation="Horizontal"/>
            </ItemsPanelTemplate>
          </sad:WorkflowItemsPresenter.ItemsPanel>
        </sad:WorkflowItemsPresenter>
      </StackPanel>
    </DataTemplate>
    <DataTemplate x:Key="Collapsed">
      <TextBlock>This is the Collapsed View</TextBlock>
    </DataTemplate>
    <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
      <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
      <Style.Triggers>
        <DataTrigger Binding="{Binding Path=IsRootDesigner}" Value="true">
          <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
        </DataTrigger>
      </Style.Triggers>
    </Style>
  </sad: ActivityDesigner.Resources>
  <Grid>
    <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
  </Grid>
</sad: ActivityDesigner>
```

> [!IMPORTANT]
>  <span data-ttu-id="048ac-131">Örnekler, makinenizde zaten yüklü.</span><span class="sxs-lookup"><span data-stu-id="048ac-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="048ac-132">Devam etmeden önce şu (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="048ac-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="048ac-133">Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="048ac-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="048ac-134">Bu örnek, şu dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="048ac-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="048ac-135">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="048ac-135">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- [<span data-ttu-id="048ac-136">İş Akışı Tasarımcısı ile uygulama geliştirme</span><span class="sxs-lookup"><span data-stu-id="048ac-136">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
