---
title: 'İzlenecek yol: WPF İçeriği için Stil Oluşturma'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: 887a157494c2992c1ae5868229c442f31fafb276
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781309"
---
# <a name="walkthrough-styling-wpf-content"></a>İzlenecek yol: WPF İçeriği için Stil Oluşturma
Bu izlenecek yol, bir Windows Form üzerinde barındırılan bir Windows Presentation Foundation (WPF) denetimine stil uygulamak nasıl gösterir.

 Bu kılavuzda, aşağıdaki görevleri gerçekleştirin:

- Projeyi oluşturun.

- WPF denetim türü oluşturun.

- Bir stil WPF denetimi için geçerlidir.

> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
- Visual Studio 2012.  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
 İlk adım Windows Forms projesi oluşturmaktır.  
  
> [!NOTE]
>  WPF içeriği barındırma, yalnızca C# ve Visual Basic projelerinde desteklenir.  
  
#### <a name="to-create-the-project"></a>Proje oluşturmak için  
  
- Visual Basic veya Visual C# adlı yeni bir Windows Forms uygulaması projesi oluşturma `StylingWpfContent`.  
  
## <a name="creating-the-wpf-control-types"></a>WPF denetim türleri oluşturma  
 WPF denetim türü projeye ekledikten sonra içinde barındırabilirsiniz bir <xref:System.Windows.Forms.Integration.ElementHost> denetimi.  
  
#### <a name="to-create-wpf-control-types"></a>WPF denetim türleri oluşturmak için  
  
1. Yeni bir WPF ekleme <xref:System.Windows.Controls.UserControl> çözüme bir proje. Denetim türü için varsayılan adı kullanacak `UserControl1.xaml`. Daha fazla bilgi için [izlenecek yol: Yeni bir WPF içeriği Windows formlarında tasarım zamanında oluşturma](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2. Tasarım görünümünde emin `UserControl1` seçilir. Daha fazla bilgi için [nasıl yapılır: Seçin ve tasarım yüzeyine öğeleri Taşı](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).  
  
3. İçinde **özellikleri** penceresinde değerini ayarlayın <xref:System.Windows.FrameworkElement.Width%2A> ve <xref:System.Windows.FrameworkElement.Height%2A> özelliklerine `200`.  
  
4. Ekleme bir <xref:System.Windows.Controls.Button?displayProperty=nameWithType> denetimini <xref:System.Windows.Controls.UserControl> ve değerini ayarlama <xref:System.Windows.Controls.ContentControl.Content%2A> özelliğini **iptal**.  
  
5. İkinci bir ekleme <xref:System.Windows.Controls.Button?displayProperty=nameWithType> denetimini <xref:System.Windows.Controls.UserControl> ve değerini ayarlama <xref:System.Windows.Controls.ContentControl.Content%2A> özelliğini **Tamam**.  
  
6. Projeyi oluşturun.  
  
## <a name="applying-a-style-to-a-wpf-control"></a>WPF denetime stil uygulama  
 Farklı görünümünü ve davranışını değiştirmek için bir WPF denetimi stil uygulayabilirsiniz.  
  
#### <a name="to-apply-a-style-to-a-wpf-control"></a>Bir WPF denetimine stil uygulamak için  
  
1. Açık `Form1` Windows Forms Tasarımcısı'nda.  
  
2. İçinde **araç kutusu**, çift `UserControl1` bir örneğini oluşturmak için `UserControl1` form üzerinde.  
  
     Örneği `UserControl1` yeni bir barındırılan <xref:System.Windows.Forms.Integration.ElementHost> adlı Denetim `elementHost1`.  
  
3. Akıllı etiket panelinde `elementHost1`, tıklayın **barındırılan içerik Düzenle** aşağı açılan listeden.  
  
     `UserControl1` açılır [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4. XAML Görünümü'nde, aşağıdaki XAML sonra Ekle `<UserControl>` etiketiyle.  
  
     Bu XAML gradyan karşıt gradyan kenarlıklı oluşturur. Denetim tıklandığında gradyanlar basılan düğme görünümünü oluşturmak için değiştirilir. Daha fazla bilgi için [stil ve şablon oluşturma](../../wpf/controls/styling-and-templating.md).  
  
```xaml  
<UserControl.Resources>  
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#FFF" Offset="0.0"/>  
        <GradientStop Color="#CCC" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#BBB" Offset="0.0"/>  
        <GradientStop Color="#EEE" Offset="0.1"/>  
        <GradientStop Color="#EEE" Offset="0.9"/>  
        <GradientStop Color="#FFF" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#444" Offset="0.0"/>  
        <GradientStop Color="#888" Offset="1.0"/>  
    </LinearGradientBrush>  
  
    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>  
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>  
        <Setter Property="Template">  
            <Setter.Value>  
                <ControlTemplate TargetType="{x:Type Button}">  
                    <Grid x:Name="Grid">  
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>  
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>  
                    </Grid>  
                    <ControlTemplate.Triggers>  
                        <Trigger Property="IsPressed" Value="true">  
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>  
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>  
                        </Trigger>  
                    </ControlTemplate.Triggers>  
                </ControlTemplate>  
            </Setter.Value>  
        </Setter>  
    </Style>  
</UserControl.Resources>  
```  
  
1. Uygulama `SimpleButton` aşağıdaki XAML içinde ekleyerek iptal düğmesi için önceki adımda tanımlanan stil `<Button>` İptal düğmesinin etiketi.  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     Düğme bildirimi, aşağıdaki XAML andıracaktır.  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1. Projeyi oluşturun.  
  
2. Açık `Form1` Windows Forms Tasarımcısı'nda.  
  
3. Düğme denetimine yeni stil uygulanır.  
  
4. Gelen **hata ayıklama** menüsünde **hata ayıklamayı Başlat** uygulamayı çalıştırın.  
  
5. Tamam ve İptal düğmeleri tıklatabilir ve farkları görüntüleyin.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Geçiş ve Birlikte Çalışabilirlik](../../wpf/advanced/migration-and-interoperability.md)
- [WPF Denetimlerini Kullanma](using-wpf-controls.md)
- [Visual Studio’da XAML tasarlama](/visualstudio/designers/designing-xaml-in-visual-studio)
- [XAML'ye Genel Bakış (WPF)](../../wpf/advanced/xaml-overview-wpf.md)
- [Stil ve Şablon Oluşturma](../../wpf/controls/styling-and-templating.md)
