---
title: 'Nasıl yapılır: (Windows Forms) çalışma zamanında resimleri ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: c7a65bcc65710324a4457c17dd728b4771550c06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694080"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Nasıl yapılır: (Windows Forms) çalışma zamanında resimleri ayarlama
Bir Windows Forms tarafından görüntülenen resmi programla ayarlayabilir miyim <xref:System.Windows.Forms.PictureBox> denetimi.  
  
### <a name="to-set-a-picture-programmatically"></a>Bir resmi program üzerinden ayarlamak için  
  
-   Ayarlama <xref:System.Windows.Forms.PictureBox.Image%2A> özelliğini kullanarak <xref:System.Drawing.Image.FromFile%2A> yöntemi <xref:System.Drawing.Image> sınıfı.  
  
     Aşağıdaki örnekte, görüntüsünün konumunu ayarlayın Belgelerim klasörünü yoludur. Windows işletim sistemi çalıştırılan bilgisayarların çoğu bu dizin içerdiğini varsayar çünkü bu, gerçekleştirilir. Bu, güvenli bir şekilde uygulamayı çalıştırmak minimum sistem erişim düzeylerine sahip kullanıcılar da sağlar. Aşağıdaki örnekte bir form varsayar bir <xref:System.Windows.Forms.PictureBox> denetim zaten eklendi.  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a>Grafik temizlemek için  
  
-   İlk olarak, görüntü tarafından kullanılan belleği serbest ve grafik temizleyin. Bellek yönetimi, bir sorun olduğunda çöp toplama belleği daha sonra ücretsiz.  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    >  Neden hakkında daha fazla bilgi için kullanmalısınız <xref:System.Drawing.Image.Dispose%2A> bkz bu şekilde [Cleaning Up Unmanaged Resources](../../../../docs/standard/garbage-collection/unmanaged.md).  
  
     Grafik tasarım zamanında denetimin içine yüklenen olsa bile bu kodu görüntü temizler.  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [PictureBox Denetimine Genel Bakış](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)
- [Nasıl yapılır: Tasarımcıyı kullanarak resim yükleme](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Nasıl yapılır: Çalışma zamanında resmin yerleştirme ve boyutunu değiştirme](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [PictureBox Denetimi](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
