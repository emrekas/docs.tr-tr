---
title: "İzlenecek yol: Windows Forms Uygulaması'nda Veri Akışı Kullanma"
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- TPL dataflow library, in Windows Forms
- Task Parallel Library, dataflows
- Windows Forms, and TPL
ms.assetid: 9c65cdf7-660c-409f-89ea-59d7ec8e127c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbe5b5db580e06bfd3e5723addd404eae7950e6c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946346"
---
# <a name="walkthrough-using-dataflow-in-a-windows-forms-application"></a>İzlenecek yol: Windows Forms Uygulaması'nda Veri Akışı Kullanma
Bu belgede, Windows Forms uygulamasında görüntü işlemeyi gerçekleştiren bir veri akışı bloğu ağı oluşturma işlemi gösterilir.  
  
 Bu örnek, belirtilen klasörden görüntü dosyalarını yükler, bileşik bir görüntü oluşturur ve sonucu görüntüler. Örnek, görüntüleri ağ üzerinden yönlendirmek için veri akışı modelini kullanır. Veri akışı modelinde, bir programın bağımsız bileşenleri ileti göndererek birbirleriyle iletişim kurar. Bir bileşen bir ileti aldığında, bazı işlemleri gerçekleştirir ve sonucu başka bir bileşene geçirir. Bunu, bir uygulamanın bir programdaki işlem sırasını denetlemek için denetim yapılarını (örneğin, koşullu deyimler, döngüler vb.) kullandığı denetim akışı modeliyle karşılaştırın.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu yönergeyi başlamadan önce [veri akışını](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) okuyun.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="sections"></a>Bölümler  
 Bu izlenecek yol aşağıdaki bölümleri içerir:  
  
- [Windows Forms uygulaması oluşturma](#winforms)  
  
- [Veri akışı ağını oluşturma](#network)  
  
- [Veri akışı ağını Kullanıcı arabirimine bağlama](#ui)  
  
- [Tüm örnek](#complete)  
  
<a name="winforms"></a>   
## <a name="creating-the-windows-forms-application"></a>Windows Forms uygulaması oluşturma  
 Bu bölümde temel Windows Forms uygulamasının nasıl oluşturulacağı ve ana forma nasıl denetim ekleneceği açıklanmaktadır.  
  
### <a name="to-create-the-windows-forms-application"></a>Windows Forms uygulamasını oluşturmak için  
  
1. Visual Studio 'da bir görsel C# veya Visual Basic **Windows Forms uygulama** projesi oluşturun. Bu belgede, proje adlandırılır `CompositeImages`.  
  
2. Ana form için form tasarımcısında, Form1.cs (Visual Basic için Form1. vb), bir <xref:System.Windows.Forms.ToolStrip> denetim ekleyin.  
  
3. <xref:System.Windows.Forms.ToolStrip> Denetime <xref:System.Windows.Forms.ToolStripButton> denetim ekleyin. Özelliğini olarak <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> ayarlayın ve<xref:System.Windows.Forms.ToolStripItem.Text%2A> **klasörü seçin**. <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>  
  
4. <xref:System.Windows.Forms.ToolStrip> Denetime ikinci <xref:System.Windows.Forms.ToolStripButton> bir denetim ekleyin. <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> Özelliğini,<xref:System.Windows.Forms.ToolStripItem.Text%2A>iptaledilecek özelliğive<xref:System.Windows.Forms.ToolStripItem.Enabled%2A> özelliğini olarak ayarlayın .`False` <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>  
  
5. Ana forma <xref:System.Windows.Forms.PictureBox> bir nesne ekleyin. Ayarlama <xref:System.Windows.Forms.Control.Dock%2A> özelliğini <xref:System.Windows.Forms.DockStyle.Fill>.  
  
<a name="network"></a>   
## <a name="creating-the-dataflow-network"></a>Veri akışı ağını oluşturma  
 Bu bölümde, görüntü işlemeyi gerçekleştiren veri akışı ağının nasıl oluşturulacağı açıklanmaktadır.  
  
### <a name="to-create-the-dataflow-network"></a>Veri akışı ağını oluşturmak için  
  
1. Projenize System. Threading. Tasks. Dataflow. dll başvurusunu ekleyin.  
  
2. Form1.cs (Visual Basic için Form1. vb) 'in aşağıdaki `using` (`Using` Visual Basic) deyimlerini içerdiğinden emin olun:  
  
     [!code-csharp[TPLDataflow_CompositeImages#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#1)]  
  
3. `Form1` Sınıfına aşağıdaki veri üyelerini ekleyin:  
  
     [!code-csharp[TPLDataflow_CompositeImages#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#2)]  
  
4. Aşağıdaki yöntemini `CreateImageProcessingNetwork` `Form1` sınıfına ekleyin. Bu yöntem, görüntü işleme ağını oluşturur.  
  
     [!code-csharp[TPLDataflow_CompositeImages#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#3)]  
  
5. `LoadBitmaps` Yöntemini uygulayın.  
  
     [!code-csharp[TPLDataflow_CompositeImages#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#4)]  
  
6. `CreateCompositeBitmap` Yöntemini uygulayın.  
  
     [!code-csharp[TPLDataflow_CompositeImages#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#5)]  
  
    > [!NOTE]
    > `CreateCompositeBitmap` Yöntemin C# sürümü, <xref:System.Drawing.Bitmap?displayProperty=nameWithType> nesneleri verimli bir şekilde işlemeyi etkinleştirmek için işaretçiler kullanır. Bu nedenle, [unsafe](../../csharp/language-reference/keywords/unsafe.md) anahtar sözcüğünü kullanabilmeniz için projenizdeki **güvenli olmayan koda izin ver** seçeneğini etkinleştirmeniz gerekir. Visual C# projesinde güvenli olmayan kodun nasıl etkinleştirileceği hakkında daha fazla bilgi için bkz. [derleme sayfası, proje Tasarımcısı (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
 Aşağıdaki tablo, ağın üyelerini açıklar.  
  
|Üye|Tür|Açıklama|  
|------------|----------|-----------------|  
|`loadBitmaps`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Bir klasör yolunu girdi olarak alır ve çıktı olarak bir <xref:System.Drawing.Bitmap> nesne koleksiyonu oluşturur.|  
|`createCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Bir <xref:System.Drawing.Bitmap> nesne koleksiyonunu girdi olarak alır ve çıkış olarak bileşik bir bit eşlem üretir.|  
|`displayCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Form üzerinde bileşik bit eşlemi görüntüler.|  
|`operationCancelled`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|İşlemin iptal edildiğini belirten bir resim görüntüler ve kullanıcının başka bir klasör seçmesini sağlar.|  
  
 Veri akışı bloklarını bir ağ oluşturacak şekilde bağlamak için bu örnek <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> yöntemini kullanır. Yöntemi, hedef bloğunun bir iletiyi kabul edip etmeyeceğini <xref:System.Predicate%601> belirleyen bir nesneyi alan aşırı yüklenmiş bir sürüm içerir. <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> Bu filtreleme mekanizması ileti bloklarının yalnızca belirli değerleri almasına olanak sağlar. Bu örnekte, ağ iki şekilde dallandırma yapabilir. Ana dal görüntüleri diskten yükler, bileşik görüntüyü oluşturur ve bu görüntüyü form üzerinde görüntüler. Alternatif dal geçerli işlemi iptal eder. <xref:System.Predicate%601> Nesneler, Ana daldaki veri akışı bloklarını, belirli iletileri reddeterek alternatif dala geçiş yapmak üzere etkinleştirir. Örneğin, Kullanıcı işlemi iptal ederse, veri akışı bloğu `createCompositeBitmap` çıkış olarak (`Nothing` Visual Basic) `null` üretir. Veri akışı bloğu `displayCompositeBitmap` giriş değerlerini `null` reddeder ve bu nedenle ileti sunulur `operationCancelled`. Veri akışı bloğu `operationCancelled` tüm iletileri kabul eder ve bu nedenle işlemin iptal edildiğini göstermek için bir resim görüntüler.  
  
 Aşağıdaki çizim görüntü işleme ağını göstermektedir:  
  
 ![Görüntü işleme ağını gösteren çizim.](./media/walkthrough-using-dataflow-in-a-windows-forms-application/dataflow-winforms-image-processing.png)  
  
 `displayCompositeBitmap` Ve`operationCancelled` veri akışı blokları Kullanıcı arabiriminde işlem yaptığından, bu eylemlerin Kullanıcı arabirimi iş parçacığında gerçekleştirilmesi önemlidir. Bunu gerçekleştirmek için, oluşturma sırasında, bu nesnelerin her biri, <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> özelliği olarak <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>ayarlanmış bir nesne sağlar. Yöntemi <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> , geçerli eşitleme <xref:System.Threading.Tasks.TaskScheduler> bağlamında çalışmayı gerçekleştiren bir nesnesi oluşturur. Yöntemi, Kullanıcı arabirimi iş parçacığında çalışan **Klasör Seç** düğmesinin işleyicisinden çağrıldığı için, `displayCompositeBitmap` ve `operationCancelled` veri akışı blokları için Eylemler kullanıcı arabirimi iş parçacığında da çalışır. `CreateImageProcessingNetwork`  
  
 Bu örnek, özelliği ayarlamak <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> yerine paylaşılan bir iptal belirteci kullanır, <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> çünkü Özellik kalıcı olarak veri akışı blok yürütmeyi iptal eder. İptal belirteci, Kullanıcı bir veya daha fazla işlemi iptal ettiğinde bile, bu örneğin aynı veri akışı ağını birden çok kez yeniden kullanmasına olanak sağlar. Bir veri akışı bloğunun yürütülmesini <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> kalıcı olarak iptal etmek için kullanan bir örnek için bkz [. nasıl yapılır: Veri akışı bloğunu](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md)iptal edin.  
  
<a name="ui"></a>   
## <a name="connecting-the-dataflow-network-to-the-user-interface"></a>Veri akışı ağını Kullanıcı arabirimine bağlama  
 Bu bölümde, veri akışı ağının Kullanıcı arabirimine nasıl bağlanacağı açıklanmaktadır. Bileşik görüntünün ve işlemin iptalinin oluşturulması, **Klasör Seç** ve **iptal** düğmelerinden başlatılır. Kullanıcı bu düğmelerden birini seçtiğinde, uygun eylem zaman uyumsuz bir şekilde başlatılır.  
  
### <a name="to-connect-the-dataflow-network-to-the-user-interface"></a>Veri akışı ağını Kullanıcı arabirimine bağlamak için  
  
1. Ana form için form tasarımcısında, <xref:System.Windows.Forms.ToolStripItem.Click> **Klasör Seç** düğmesine yönelik olay için bir olay işleyicisi oluşturun.  
  
2. **Klasör Seç** düğmesine yönelik olayıuygulayın.<xref:System.Windows.Forms.ToolStripItem.Click>  
  
     [!code-csharp[TPLDataflow_CompositeImages#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#6)]  
  
3. Ana form için form tasarımcısında, <xref:System.Windows.Forms.ToolStripItem.Click> **iptal** düğmesine yönelik olay için bir olay işleyicisi oluşturun.  
  
4. **İptal düğmesi** için olayı<xref:System.Windows.Forms.ToolStripItem.Click> uygulayın.  
  
     [!code-csharp[TPLDataflow_CompositeImages#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#7)]  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a>Tam Örnek  
 Aşağıdaki örnekte bu izlenecek yol için tüm kod gösterilmektedir.  
  
 [!code-csharp[TPLDataflow_CompositeImages#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#100)]  
  
 Aşağıdaki çizimde ortak \ örnek resimler \ klasörü için tipik çıkış gösterilmektedir.  
  
 ![Windows Forms uygulaması](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow_CompositeImages")  

## <a name="see-also"></a>Ayrıca bkz.

- [Veri akışı](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
