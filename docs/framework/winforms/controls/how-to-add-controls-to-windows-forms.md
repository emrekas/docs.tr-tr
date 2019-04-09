---
title: 'Nasıl yapılır: Windows Forms’a Denetimler Ekleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 72b5931a79284a93a4e0fdf3cb2cc3b03157f5f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106489"
---
# <a name="how-to-add-controls-to-windows-forms"></a>Nasıl yapılır: Windows Forms’a Denetimler Ekleme
Çoğu forms formunun yüzeyine denetimler ekleyerek, bir kullanıcı arabirimi (UI) tanımlamak için tasarlanmıştır. A *denetimi* bilgilerini görüntülemek veya kullanıcı girişi kabul etmek için kullanılan bir form üzerinde bir bileşendir. Denetimleri hakkında daha fazla bilgi için bkz. [Windows Forms denetimleri](index.md).  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-draw-a-control-on-a-form"></a>Formda bir denetim çizmek için  
  
1.  Formu açın. Daha fazla bilgi için [nasıl yapılır: Tasarımcıda Windows formlarını görüntüleme](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).  
  
2.  İçinde **araç kutusu**, formunuza eklemek istediğiniz denetim tıklayın.  
  
3.  Formunda bulunmasını denetimin sol üst köşesinde istediğiniz tıklayın ve konum için denetimin sağ alt köşedeki istediğiniz yere sürükleyin.  
  
     Denetimin form belirtilen konumu ve boyutu ile eklenir.  
  
    > [!NOTE]
    >  Her denetim tanımlanan varsayılan boyutuna sahiptir. Buradan sürükleyerek formunuza denetimin varsayılan boyutunda denetim ekleyebilirsiniz **araç kutusu** form.  
  
### <a name="to-drag-a-control-to-a-form"></a>Bir forma bir denetimi sürükleyin  
  
1.  Formu açın. Daha fazla bilgi için [nasıl yapılır: Tasarımcıda Windows formlarını görüntüleme](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).  
  
2.  İçinde **araç kutusu**, formunuza sürükleyin ve istediğiniz denetim tıklayın.  
  
     Denetimin varsayılan boyutunda belirtilen konumda forma eklenir.  
  
    > [!NOTE]
    >  Bir denetimde çift tıkladığınızda **araç kutusu** varsayılan boyutunda biçiminde sol üst köşesinde eklemek için.  
  
     Ayrıca denetimlerini dinamik olarak bir forma çalışma zamanında ekleyebilirsiniz. Aşağıdaki kod örneğinde, bir <xref:System.Windows.Forms.TextBox> denetimi forma eklenecektir olduğunda bir <xref:System.Windows.Forms.Button> denetim tıklandığında.  
  
    > [!NOTE]
    >  Aşağıdaki yordam bir formla gerekir bir **düğmesi** denetimi `Button1`, üzerindeki zaten yapıldı.  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>Bir denetimin program aracılığıyla bir forma eklemek için  
  
1.  Düğmenin işleyen yöntem içinde `Click` formunuzun sınıftaki kod ekleme, denetim değişkeni bir başvuru eklemek için aşağıdakine benzer bir olay kümesi denetimin `Location`ve denetimi ekleyin.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  Ayrıca, denetimin diğer özelliklerini başlatmak için kod ekleyebilirsiniz.  
  
    > [!IMPORTANT]
    >  Yerel bir güvenlik riski ağ üzerinden bilgisayarınıza bir kötü amaçlı başvurarak sunabileceğinize `UserControl`. Bu, yalnızca, yanlışlıkla bunu projenize ekleyerek ardından zararlı olabilecek özel bir denetim oluşturulamaz kötü amaçlı bir kişinin söz konusu olduğunda önemli hale gelir.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Windows Forms Denetimleri](index.md)
- [Windows Formlarında Denetimleri Düzenleme](arranging-controls-on-windows-forms.md)
- [Nasıl yapılır: Windows Forms’da Denetimleri Yeniden Boyutlandırma](how-to-resize-controls-on-windows-forms.md)
- [Nasıl yapılır: Windows Forms Denetimi Tarafından Görüntülenen Metni Ayarlama](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Windows Forms'ta Kullanılacak Denetimler](controls-to-use-on-windows-forms.md)
