---
title: Veri Şablonu Oluşturmaya Genel Bakış
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], templates
- binding data [WPF], templates
- templates [WPF], data
- data templates [WPF]
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
ms.openlocfilehash: 58d723ccf86e4195674c132f9fb1b76f689f57b2
ms.sourcegitcommit: 68eb5c4928e2b082f178a42c16f73fedf52c2ab8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59055345"
---
# <a name="data-templating-overview"></a>Veri Şablonu Oluşturmaya Genel Bakış
WPF veri şablonu oluşturma modeli, verilerinizin sunumu tanımlamak için büyük esneklik sağlar. WPF denetimleri verilerini sunumu özelleştirmeyi desteklemek için yerleşik işlevselliğe sahiptir. Bu konu öncelikle nasıl tanımlanacağını gösterir bir <xref:System.Windows.DataTemplate> ve ardından özel mantığı ve hiyerarşik veri görüntüleme desteği göre şablonları seçimini gibi diğer veri şablonu oluşturma özellikleri sunar.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Önkoşullar  
 Bu konu, üzerinde veri şablonu oluşturma özelliklerine odaklanır ve veri bağlama kavramlarını bir giriş değil. Temel veri bağlama kavramları hakkında daha fazla bilgi için bkz. [Data Binding Overview](data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate> verilerini sunumu hakkında olduğunu ve WPF stil ve şablon oluşturma modeli tarafından sağlanan birçok özelliklerinden biridir. WPF stil ve şablon oluşturma modelinin nasıl kullanılacağını gibi bir giriş için bir <xref:System.Windows.Style> denetimlere özelliklerini ayarlamak için bkz: [stil ve şablon oluşturma](../controls/styling-and-templating.md) konu.  
  
 Ayrıca, anlaşılması önemlidir `Resources`, olan temelde ne gibi nesneleri etkinleştirme <xref:System.Windows.Style> ve <xref:System.Windows.DataTemplate> yeniden kullanılabilir olması için. Kaynaklar hakkında daha fazla bilgi için bkz. [XAML kaynakları](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Veri şablonu oluşturma temelleri  
  
 Neden göstermek için <xref:System.Windows.DataTemplate> veri bağlama ilişkin bir örneği atalım önemlidir. Bu örnekte, sahip olduğumuz bir <xref:System.Windows.Controls.ListBox> listesine bağlı `Task` nesneleri. Her `Task` nesnesinin bir `TaskName` (dize), bir `Description` (dize), bir `Priority` (int) ve vlastnost typu `TaskType`, olduğu bir `Enum` değerlerle `Home` ve `Work`.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>DataTemplate  
 Olmadan bir <xref:System.Windows.DataTemplate>, bizim <xref:System.Windows.Controls.ListBox> şu anda şöyle görünür:  
  
 ![Veri şablonu oluşturmaya örnek ekran](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Herhangi bir özel yönergeler olan neler olduğunu <xref:System.Windows.Controls.ListBox> varsayılan çağrılar tarafından `ToString` koleksiyondaki nesneleri görüntülemek çalışırken. Bu nedenle, `Task` Nesne geçersiz kılmaları `ToString` yöntemi, ardından <xref:System.Windows.Controls.ListBox> temel koleksiyon içindeki her kaynak nesnenin dize gösterimini görüntüler.  
  
 Örneğin, varsa `Task` sınıf geçersiz kılmalarını `ToString` yöntemi bu şekilde, burada `name` alanı `TaskName` özelliği:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 Ardından <xref:System.Windows.Controls.ListBox> aşağıdaki gibi görünür:  
  
 ![Veri şablonu oluşturmaya örnek ekran](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Ancak, sınırlama ve faaliyetini olmasıdır. Ayrıca, için bağlıyorsanız [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] verileri, mıydı devre dışı `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Basit bir DataTemplate'ı tanımlama  
 Çözüm tanımlamaktır bir <xref:System.Windows.DataTemplate>. Bunu yapmanın bir yolu olan ayarlanacak <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> özelliği <xref:System.Windows.Controls.ListBox> için bir <xref:System.Windows.DataTemplate>. İçinde belirttiğiniz, <xref:System.Windows.DataTemplate> görsel yapı veri nesne haline gelir. Aşağıdaki <xref:System.Windows.DataTemplate> oldukça basittir. Biz, her bir öğe üç görüntülenen yönergeleri vermiş olursunuz <xref:System.Windows.Controls.TextBlock> öğeleri içinde bir <xref:System.Windows.Controls.StackPanel>. Her <xref:System.Windows.Controls.TextBlock> bir özelliğine bağlı öğe `Task` sınıfı.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Bu konudaki örnekler için temel alınan verileri oluşan bir koleksiyondur [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] nesneleri. İçin bağlıyorsanız [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] verileri temel kavramları aynıdır, ancak küçük bir söz dizimi fark yoktur. Yerine örneğin `Path=TaskName`, ayarlarsınız <xref:System.Windows.Data.Binding.XPath%2A> için `@TaskName` (varsa `TaskName` bir özniteliğidir, [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] düğümü).  
  
 Artık bizim <xref:System.Windows.Controls.ListBox> aşağıdaki gibi görünür:  
  
 ![Veri şablonu oluşturmaya örnek ekran](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Bir kaynak olarak DataTemplate oluşturma  
 Yukarıdaki örnekte tanımladığımız <xref:System.Windows.DataTemplate> satır içi. Aşağıdaki örnekte olduğu gibi yeniden kullanılabilir bir nesne olamaz kaynakları bölümünde tanımlamak için daha yaygın:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Artık `myTaskTemplate` aşağıdaki örnekteki gibi bir kaynak olarak:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Çünkü `myTaskTemplate` bir kaynaktır, artık alan bir özelliği olan diğer denetimler kullanabilirsiniz bir <xref:System.Windows.DataTemplate> türü. Yukarıda gösterildiği, için <xref:System.Windows.Controls.ItemsControl> gibi nesneleri <xref:System.Windows.Controls.ListBox>, bu <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> özelliği. İçin <xref:System.Windows.Controls.ContentControl> nesneler, bu <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> özelliği.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>DataType özelliği  
 <xref:System.Windows.DataTemplate> Sınıfında bir <xref:System.Windows.DataTemplate.DataType%2A> çok benzer özelliği <xref:System.Windows.Style.TargetType%2A> özelliği <xref:System.Windows.Style> sınıfı. Bu nedenle, belirtmek yerine bir `x:Key` için <xref:System.Windows.DataTemplate> yukarıdaki örnekte, şunları yapabilirsiniz:  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Bu <xref:System.Windows.DataTemplate> tümüne otomatik olarak uygulanan `Task` nesneleri. Bu durumda unutmayın `x:Key` örtük olarak ayarlanır. Bu nedenle, bu atarsanız <xref:System.Windows.DataTemplate> bir `x:Key` değeri örtük geçersiz kıldıkları `x:Key` ve <xref:System.Windows.DataTemplate> otomatik olarak uygulanmamış.  
  
 Bağlıyorsanız bir <xref:System.Windows.Controls.ContentControl> koleksiyonuna `Task` nesneleri <xref:System.Windows.Controls.ContentControl> yukarıdaki kullanmaz <xref:System.Windows.DataTemplate> otomatik olarak. Bunun nedeni, bağlama üzerinde bir <xref:System.Windows.Controls.ContentControl> bir koleksiyonun tamamını veya tek tek nesneler için bağlama isteyip istemediğinizi ayırt etmek için daha fazla bilgi gerekiyor. Varsa, <xref:System.Windows.Controls.ContentControl> seçimini izleme bir <xref:System.Windows.Controls.ItemsControl> ayarlayabileceğiniz türü <xref:System.Windows.Data.Binding.Path%2A> özelliği <xref:System.Windows.Controls.ContentControl> bağlama "`/`" geçerli öğe ilgilenen olduğunu belirtmek için. Bir örnek için bkz. [bağlama toplama ve görüntüleme bilgileri seçimi temel](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). Aksi takdirde, belirtmeniz gereken <xref:System.Windows.DataTemplate> ayarlayarak açıkça <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> özelliği.  
  
 <xref:System.Windows.DataTemplate.DataType%2A> Varsa özelliği özellikle yararlı bir <xref:System.Windows.Data.CompositeCollection> farklı türde veri nesneleri. Bir örnek için bkz. [CompositeCollection uygulama](how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Daha fazla için DataTemplate ekleme  
 Veriler gerekli olan bilgileri şu anda görünür, ancak kesinlikle geliştirme yer yoktur. Şimdi ekleyerek sunuyu geliştirmek bir <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Grid>ve bazı <xref:System.Windows.Controls.TextBlock> görüntülenen verileri tanımlayan öğeleri.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Aşağıdaki ekran görüntüsü gösterildiği <xref:System.Windows.Controls.ListBox> bu değişiklik <xref:System.Windows.DataTemplate>:  
  
 ![Veri şablonu oluşturmaya örnek ekran](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Biz ayarlayabilirsiniz <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> için <xref:System.Windows.HorizontalAlignment.Stretch> üzerinde <xref:System.Windows.Controls.ListBox> öğelerin genişliğini tüm yer alan emin olmak için:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 İle <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> özelliğini <xref:System.Windows.HorizontalAlignment.Stretch>, <xref:System.Windows.Controls.ListBox> artık şöyle görünür:  
  
 ![Veri şablonu oluşturmaya örnek ekran](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Özellik değerleri uygulamak için DataTriggers kullanın  
 Geçerli sunu olup olmadığını bize değil bir `Task` Giriş bir görev veya bir office görev. Unutmayın `Task` nesnesinin bir `TaskType` türünün özelliği `TaskType`, bir sabit listesi değerlerine sahip olduğu `Home` ve `Work`.  
  
 Aşağıdaki örnekte, <xref:System.Windows.DataTrigger> ayarlar <xref:System.Windows.Controls.Border.BorderBrush%2A> adlı öğe `border` için `Yellow` varsa `TaskType` özelliği `TaskType.Home`.  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Uygulamamızı artık aşağıdaki gibi görünür. Giriş görevleri ile bir sarı kenarlık görünür ve office görevlerini Deniz Mavisi bir kenarlık görünür:  
  
 ![Veri şablonu oluşturmaya örnek ekran](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 Bu örnekte <xref:System.Windows.DataTrigger> kullanan bir <xref:System.Windows.Setter> özellik değerini ayarlamak için. Tetikleyici sınıfları de <xref:System.Windows.TriggerBase.EnterActions%2A> ve <xref:System.Windows.TriggerBase.ExitActions%2A> animasyonları gibi eylemleri bir dizi Başlat olanak tanıyan özellikler. Ayrıca, de mevcuttur bir <xref:System.Windows.MultiDataTrigger> değişiklikleri uygulamak sağlar sınıfını tabanlı birden fazla veriye bağlı özellik değerlerine göre.  
  
 Aynı etkiyi elde etmek için alternatif bir yolu bağlamaktır <xref:System.Windows.Controls.Border.BorderBrush%2A> özelliğini `TaskType` özelliği ve renk döndürülecek bir değer dönüştürücü temel kullanım `TaskType` değeri. Bir dönüştürücü kullanarak yukarıdaki etkisi oluşturmak, performans açısından biraz daha verimlidir. Kendi mantığınızı sağladığınız çünkü ek olarak, kendi dönüştürücü oluşturma, daha fazla esneklik sağlar. Sonuç olarak, seçtiğiniz yöntemden senaryonuza ve tercihinize bağlıdır. Bir dönüştürücü yazma hakkında daha fazla bilgi için bkz: <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Ne bir DataTemplate ait?  

Önceki örnekte, biz tetikleyici içinde yerleştirilen <xref:System.Windows.DataTemplate> kullanarak <xref:System.Windows.DataTemplate>.<xref:System.Windows.DataTemplate.Triggers%2A> özellik. <xref:System.Windows.Setter> Tetikleyicisi bir öğenin bir özelliğinin değerini ayarlar ( <xref:System.Windows.Controls.Border> öğe) içinde olan <xref:System.Windows.DataTemplate>. Ancak, özellikleri, `Setters` ile endişe geçerli öğelerini özelliklerinin <xref:System.Windows.DataTemplate>, kullanarak özelliklerini ayarlamak daha uygun olabilir bir <xref:System.Windows.Style> için olan <xref:System.Windows.Controls.ListBoxItem> sınıfı (varsa dosyalar bağladığınız denetimi bir <xref:System.Windows.Controls.ListBox>). Örneğin, isterseniz, <xref:System.Windows.Trigger> animasyon uygulamak için <xref:System.Windows.UIElement.Opacity%2A> değeri öğesinin fare bir öğeye işaret ettiğinde içinde tetikleyicilerini tanımlayın bir <xref:System.Windows.Controls.ListBoxItem> stili. Bir örnek için bkz. [stil ve şablon oluşturma örnek giriş](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).
  
 Genel olarak, aklınızda <xref:System.Windows.DataTemplate> her oluşturulan uygulanan <xref:System.Windows.Controls.ListBoxItem> (aslında nerede ve nasıl uygulandığı hakkında daha fazla bilgi için bkz. <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> sayfası.). <xref:System.Windows.DataTemplate> Yalnızca sunu ve veri nesneleri görünümünü endişelenmiştir. Çoğu durumda, sunum, hangi bir öğe gibi diğer tüm yönleri gibi görünen seçildiğinde veya nasıl <xref:System.Windows.Controls.ListBox> öğeleri düzenlediğinden ait olmayan tanımında bir <xref:System.Windows.DataTemplate>. Bir örnek için bkz. [stil ve şablon oluşturma ItemsControl](#DataTemplating_ItemsControl) bölümü.  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Veri nesnesinin özelliklerine bağlı bir DataTemplate'ı seçme  
 İçinde [DataType özelliği](#Styling_DataType) bölümde Bahsettiğimiz farklı veri nesneleri için farklı veri şablonları tanımlayabilirsiniz. Varsa, özellikle kullanışlı olan bir <xref:System.Windows.Data.CompositeCollection> farklı türler veya koleksiyonlar farklı türlerde öğelerle. İçinde [DataTriggers kullanmak için geçerli özellik değerlerini](#DataTrigger_to_Apply_Property_Values) bölümünde, size göstermiştir veri nesneleri aynı türde bir koleksiyonu varsa oluşturabileceğiniz bir <xref:System.Windows.DataTemplate> ve sonra özellik değerlerine göre değişiklikleri uygulamak için Tetikleyiciler kullanma Her bir veri nesnesi. Özellik değerleri uygulamak veya animasyon başlangıç Tetikleyiciler sağlar ancak bunlar veri nesnelerinizi yapısını yeniden oluşturmak için esneklik vermeyin. Bazı senaryolar farklı bir oluşturmanızı gerektirebilir <xref:System.Windows.DataTemplate> veriler için aynı olan nesneler yazın, ancak farklı özelliklere sahip.  
  
 Örneğin, bir `Task` nesnesinin bir `Priority` değerini `1`, kendiniz için bir uyarı sunmak için tamamen farklı bir görünüm vermek isteyebilirsiniz. Bu durumda, oluşturduğunuz bir <xref:System.Windows.DataTemplate> yüksek öncelikli görüntüsü için `Task` nesneleri. Aşağıdaki ekleyelim <xref:System.Windows.DataTemplate> kaynaklar bölümüne:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Bu örnekte fark <xref:System.Windows.DataTemplate>.<xref:System.Windows.FrameworkTemplate.Resources%2A> özellik. Bölüm paylaşılır, içerdiği öğeler tarafından tanımlanan kaynakları <xref:System.Windows.DataTemplate>.  
  
 Seçim mantığını sağlamak <xref:System.Windows.DataTemplate> kullanılacak temel `Priority` değeri veri nesnesinin öğesinin oluşturma <xref:System.Windows.Controls.DataTemplateSelector> ve geçersiz kılma <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> yöntemi. Aşağıdaki örnekte, <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> yöntemi değerine göre uygun şablonu döndürülecek mantığı sağlar `Priority` özelliği. Döndürülecek şablon işlevleri, kaynakları bulunur <xref:System.Windows.Window> öğesi.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Biz ardından bildirebilirsiniz `TaskListDataTemplateSelector` bir kaynak olarak:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Şablon seçiciyi kaynağı kullanmak için kendisine atayın <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> özelliği <xref:System.Windows.Controls.ListBox>. <xref:System.Windows.Controls.ListBox> Çağrıları <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> yöntemi `TaskListDataTemplateSelector` temel alınan bir koleksiyondaki öğelerin her biri için. Çağrı veri nesnesi öğesini parametre olarak geçirir. <xref:System.Windows.DataTemplate> Tarafından döndürülen yöntemi daha sonra bu veri nesnesine uygulanır.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Şablon seçiciyi bir yerde ile <xref:System.Windows.Controls.ListBox> artık aşağıdaki gibi görünür:  
  
 ![Veri şablonu oluşturmaya örnek ekran](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Bu örnekte bizim tartışılması, burada sona eriyor. Tam bir örnek için bkz. [veri şablonu oluşturmaya örnek giriş](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Stil ve şablon oluşturma ItemsControl  
 Olsa da <xref:System.Windows.Controls.ItemsControl> kullanabileceğiniz tek bir denetim türü değil bir <xref:System.Windows.DataTemplate> bağlamak için çok yaygın bir senaryo olduğu, bir <xref:System.Windows.Controls.ItemsControl> koleksiyonuna. İçinde [ne ait bir DataTemplate içinde](#what_belongs_in_datatemplate) bölümü, Bahsettiğimiz tanımı, <xref:System.Windows.DataTemplate> yalnızca verilerini sunumu önceliğiniz olması gerektiğini. Ne zaman kullanmak uygun değil öğrenmek için bir <xref:System.Windows.DataTemplate> tarafından sağlanan farklı stil ve şablon özelliklerini anlamak önemlidir <xref:System.Windows.Controls.ItemsControl>. Aşağıdaki örnek, bu özelliklerin her biri işlevi göstermek için tasarlanmıştır. <xref:System.Windows.Controls.ItemsControl> Bu örnekte aynı bağlı `Tasks` koleksiyonu önceki örnekte olduğu gibi. İçin tanıtım amacıyla, stilleri ve şablonları Bu örnekte bildirilen tüm satır içi olan.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 İşlendiğinde örnek görüntüsü verilmiştir:  
  
 ![ItemsControl örnek ekran](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Kullanarak yerine unutmayın <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, kullanabileceğiniz <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>. Bir örnek için önceki bölüme bakın. Benzer şekilde, kullanmak yerine <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>, kullanılacak seçeneğiniz <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>.  
  
 İki diğer stil özelliklerini <xref:System.Windows.Controls.ItemsControl> değil gösterilen burada <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> ve <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Hiyerarşik veriler için destek  
 Şu ana kadar yalnızca bağlamak ve tek bir koleksiyonu görüntülemek nasıl incelemiştik. Bazen diğer koleksiyonları içeren bir koleksiyon var. <xref:System.Windows.HierarchicalDataTemplate> Sınıfı ile kullanılmak üzere tasarlanmıştır <xref:System.Windows.Controls.HeaderedItemsControl> türleri bu tür verileri görüntülemek için. Aşağıdaki örnekte, `ListLeagueList` listesidir `League` nesneleri. Her `League` nesnesinin bir `Name` ve koleksiyonu `Division` nesneleri. Her `Division` sahip bir `Name` ve koleksiyonu `Team` nesneleri ve her `Team` nesnesinin bir `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 Kullanımını gösteren örnek <xref:System.Windows.HierarchicalDataTemplate>, diğer listeleri içeren liste verilerini kolayca görüntüleyebilirsiniz. Örneğin bir ekran görüntüsü aşağıda verilmiştir.  
  
 ![Örnek ekran HierarchicalDataTemplate](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Veri Bağlama](../advanced/optimizing-performance-data-binding.md)
- [DataTemplate ile Oluşturulan Öğeleri Bulma](how-to-find-datatemplate-generated-elements.md)
- [Stil ve Şablon Oluşturma](../controls/styling-and-templating.md)
- [Veri Bağlamaya Genel Bakış](data-binding-overview.md)
- [GridView Sütun Üstbilgi Stil ve Şablonlarına Genel Bakış](../controls/gridview-column-header-styles-and-templates-overview.md)
