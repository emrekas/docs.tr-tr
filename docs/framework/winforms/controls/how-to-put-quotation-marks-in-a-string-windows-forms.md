---
title: 'Nasıl yapılır: Bir dizeye tırnak Işareti koyma (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
ms.openlocfilehash: 20828f75eeae9df33fcc22d8558b26a8a1ab2bdc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910429"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a>Nasıl yapılır: Bir dizeye tırnak Işareti koyma (Windows Forms)
Bazen bir metin dizesinde tırnak işaretleri ("") yerleştirmek isteyebilirsiniz. Örneğin:  
  
 "Bir işleme hak duymuş olursunuz!" diyor  
  
 Alternatif olarak, <xref:Microsoft.VisualBasic.ControlChars.Quote> alanı bir sabit olarak da kullanabilirsiniz.  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a>Kodunuzda bir dizeye tırnak işareti koymak için  
  
1. Visual Basic, bir satıra gömülü tırnak işareti olarak iki tırnak işareti ekleyin. Visual C# ve Visual C++' te, kaçış sırasını \\"gömülü tırnak işareti olarak ekleyin. Örneğin, önceki dizeyi oluşturmak için aşağıdaki kodu kullanın.  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     -veya-  
  
2. Tırnak işareti için ASCII veya Unicode karakteri ekleyin. Visual Basic, ASCII karakterini (34) kullanın. Görselde C#Unicode karakterini kullanın (\u0022).  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    > Bu örnekte, temel karakter kümesinde bir karakter atayan bir evrensel karakter adı kullanamadığından, \u0022 kullanamazsınız. Aksi takdirde, C3851 üretebilirsiniz. Daha fazla bilgi için bkz. [derleyici hatası C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).  
  
     -veya-  
  
3. Ayrıca karakter için bir sabit tanımlayabilir ve gerektiğinde kullanabilirsiniz.  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [TextBox Denetimine Genel Bakış](textbox-control-overview-windows-forms.md)
- [Nasıl yapılır: Windows Forms TextBox denetimindeki ekleme noktasını denetleme](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Nasıl yapılır: Windows Forms TextBox denetimiyle bir parola metin kutusu oluşturma](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Nasıl yapılır: Salt okunurdur metin kutusu oluşturma](how-to-create-a-read-only-text-box-windows-forms.md)
- [Nasıl yapılır: Windows Forms metin kutusu denetimindeki metni seçme](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Nasıl yapılır: Windows Forms TextBox denetiminde birden çok satırı görüntüleme](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox Denetimi](textbox-control-windows-forms.md)
