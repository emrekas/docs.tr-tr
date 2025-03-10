---
title: "İzlenecek yol: C# ile beraber Windows Forms Denetimi'nden Devralma"
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4a9a4b9bc15d2579837c3f4969a8d85293f10967
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015674"
---
# <a name="walkthrough-inherit-from-a-windows-forms-control-with-c"></a>İzlenecek yol: C ile Windows Forms denetiminden devralma\#

Visual C#ile *Devralma*aracılığıyla güçlü özel denetimler oluşturabilirsiniz. Devralma aracılığıyla standart Windows Forms denetimlerinin tüm devralınan işlevlerini koruyan ancak özel işlevleri de birleştiren denetimler oluşturabilirsiniz. Bu kılavuzda, adlı `ValueButton`basit bir devralınmış denetim oluşturacaksınız. Bu düğme standart Windows Forms <xref:System.Windows.Forms.Button> denetiminden işlevselliği devralacak ve adlı `ButtonValue`özel bir özelliği kullanıma sunacaktır.

## <a name="create-the-project"></a>Projeyi Oluşturma

Yeni bir proje oluşturduğunuzda, kök ad alanı, derleme adı ve proje adını ayarlamak ve varsayılan bileşenin doğru ad alanında yer aldığından emin olmak için adını belirtin.

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a>ValueButtonLib denetim kitaplığını ve ValueButton denetimini oluşturmak için

1. Visual Studio 'da yeni bir **Windows Forms denetim kitaplığı** projesi oluşturun ve **ValueButtonLib**olarak adlandırın.

     Proje adı `ValueButtonLib`, varsayılan olarak kök ad alanına da atanır. Kök ad alanı, derlemedeki bileşenlerin adlarını nitelemek için kullanılır. Örneğin, iki derleme adlı `ValueButton`bileşenler içeriyorsa, `ValueButton` bileşenini kullanarak `ValueButtonLib.ValueButton`belirtebilirsiniz. Daha fazla bilgi için bkz. [ad alanları](../../../csharp/programming-guide/namespaces/index.md).

2. **Çözüm Gezgini**' de, **UserControl1.cs**' a sağ tıklayıp kısayol menüsünden **Yeniden Adlandır** ' ı seçin. Dosya adını **ValueButton.cs**olarak değiştirin. '`UserControl1`' Kod öğesine yapılan tüm başvuruları yeniden adlandırmak Isteyip istemediğiniz sorulduğunda **Evet** düğmesine tıklayın.

3. **Çözüm Gezgini**' de, **ValueButton.cs** ' a sağ tıklayın ve **kodu görüntüle**' yi seçin.

4. Bildiri satırını bulun ve bu denetimin devraldığı <xref:System.Windows.Forms.UserControl> türü olarak <xref:System.Windows.Forms.Button>değiştirin. `public partial class ValueButton` `class` Bu, <xref:System.Windows.Forms.Button> devralınan denetiminizin tüm denetim işlevlerini devralmasını sağlar.

5. **Çözüm Gezgini**, tasarımcı tarafından oluşturulan kod dosyasını göstermek için **ValueButton.cs** düğümünü açın, **ValueButton.Designer.cs**. Bu dosyayı **kod düzenleyicisinde**açın.

6. Yöntemini bulun ve <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> özelliği atayan çizgiyi kaldırın. `InitializeComponent` Bu özellik <xref:System.Windows.Forms.Button> denetimde yok.

7. Projeyi kaydetmek için **Dosya** menüsünden **Tümünü Kaydet** ' i seçin.

    > [!NOTE]
    > Görsel tasarımcı artık kullanılamıyor. <xref:System.Windows.Forms.Button> Denetim kendi boyadığı için tasarımcıda görünümünü değiştiremedik. Görsel temsili, kodda değiştirilmediği sürece (yani, <xref:System.Windows.Forms.Button>) devraldığı sınıftan tamamen aynı olacaktır. Tasarım yüzeyine, UI öğesi içermeyen bileşenler ekleyebilirsiniz.

## <a name="add-a-property-to-your-inherited-control"></a>Devralınan denetimi bir özellik ekleyin

Devralınan Windows Forms denetimlerinin olası bir kullanımı, standart Windows Forms denetimlerinin görünümü ve hisde aynı olan, ancak özel özellikler sunan denetimlerin oluşturulması. Bu bölümde, denetimi adlı `ButtonValue` bir özellik ekleyeceksiniz.

### <a name="to-add-the-value-property"></a>Değer özelliğini eklemek için

1. **Çözüm Gezgini**' de, **ValueButton.cs**' a sağ tıklayın ve ardından kısayol menüsünde **kodu görüntüle** ' ye tıklayın.

2. `class` İfadesini bulun. Hemen sonra `{`, aşağıdaki kodu yazın:

    ```csharp
    // Creates the private variable that will store the value of your
    // property.
    private int varValue;
    // Declares the property.
    public int ButtonValue
    {
       // Sets the method for retrieving the value of your property.
       get
       {
          return varValue;
       }
       // Sets the method for setting the value of your property.
       set
       {
          varValue = value;
       }
    }
    ```

     Bu kod, `ButtonValue` özelliğin depolanacağı ve alındığı yöntemleri ayarlar. İfade, döndürülen değeri özel değişkende `varValue`depolanan değere ayarlar ve `set` ifade ise `value` anahtar sözcüğünün kullanımıyla özel değişkenin değerini ayarlar. `get`

3. Projeyi kaydetmek için **Dosya** menüsünden **Tümünü Kaydet** ' i seçin.

## <a name="test-the-control"></a>Denetimi test etme

Denetimler tek başına projeler değildir; Bunlar bir kapsayıcıda barındırılmalıdır. Denetiminizi test etmek için, içinde çalışması için bir test projesi sağlamanız gerekir. Ayrıca, denetimi (derleyerek) oluşturarak denetiminizi test projesi için de erişilebilir yapmanız gerekir. Bu bölümde, denetiminizi oluşturacak ve bir Windows formunda test edersiniz.

### <a name="to-build-your-control"></a>Denetiminizi oluşturmak için

Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**. Derleme, derleyici hataları veya uyarıları olmadan başarılı olmalıdır.

### <a name="to-create-a-test-project"></a>Bir test projesi oluşturmak için

1. **Dosya** menüsünde, **Ekle** ' nin üzerine gelin ve yeni proje ' ye tıklayarak yeni proje **Ekle** iletişim kutusunu açın.

2. **Görsel C#**  düğümün altında **Windows** düğümünü seçin ve **Windows Forms uygulama**' ya tıklayın.

3. **Ad** kutusuna **Test**girin.

4. **Çözüm Gezgini**, test projeniz için **Başvurular** düğümüne sağ tıklayın ve ardından kısayol menüsünden **Başvuru Ekle** ' yi seçerek **Başvuru Ekle** iletişim kutusunu görüntüleyin.

5. Etiketli **Projeler**sekmesine tıklayın. ValueButtonLib projeniz **Proje adı**altında listelenecektir. Başvuruyu test projesine eklemek için projeye çift tıklayın.

6. **Çözüm Gezgini** ' de **Test** ' e sağ tıklayın ve **Oluştur**' u seçin.

### <a name="to-add-your-control-to-the-form"></a>Formunuza denetim eklemek için

1. **Çözüm Gezgini**' de, **Form1.cs** ' ye sağ tıklayıp kısayol menüsünden **tasarımcıyı görüntüle** ' yi seçin.

2. **Araç kutusunda** **ValueButtonLib bileşenleri**' ni seçin. **ValueButton**öğesine çift tıklayın.

     Formda bir **ValueButton** görünür.

3. **ValueButton** öğesine sağ tıklayın ve kısayol menüsünden **Özellikler** ' i seçin.

4. **Özellikler** penceresinde, bu denetimin özelliklerini inceleyin. Bunlar, bir standart düğme tarafından sunulan özelliklerle aynıdır, ancak ek bir özellik, ButtonValue olur.

5. **ButtonValue** özelliğini **5**olarak ayarlayın.

6. Formunuza bir<xref:System.Windows.Forms.Label> denetim eklemek için **araç kutusunun** **tüm Windows Forms** sekmesinde etiket ' e çift tıklayın.

7. Etiketi formun merkezine yeniden yerleştir.

8. Çift tıklayın `valueButton1`.

     **Kod Düzenleyicisi** `valueButton1_Click` olay olarak açılır.

9. Aşağıdaki kod satırını ekleyin.

    ```csharp
    label1.Text = valueButton1.ButtonValue.ToString();
    ```

10. **Çözüm Gezgini**' de **Test**' e sağ tıklayın ve kısayol menüsünde **Başlangıç projesi olarak ayarla** ' yı seçin.

11. **Hata Ayıkla** menüsünden **hata ayıklamayı Başlat**' ı seçin.

     `Form1`görüneceği.

12. Tıklatın `valueButton1`.

     ' 5 ' rakamı `label1`, devralınan `label1` denetiminizin `ButtonValue` özelliğinin `valueButton1_Click` yöntemi aracılığıyla geçirildiğini gösteren içinde görüntülenir. `ValueButton` Böylece denetiminiz standart Windows Forms düğmesinin tüm işlevlerini devralır, ancak ek, özel bir özellik sunar.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Araç kutusu öğelerini Seç Iletişim kutusunda bir denetim görüntüle](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [İzlenecek yol: Visual ile bileşik denetim yazmaC#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
