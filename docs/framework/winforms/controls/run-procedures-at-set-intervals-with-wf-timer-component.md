---
title: 'Nasıl yapılır: Windows Forms Süreölçer Bileşeni ile Belirlenen Aralıklarda Yordamları Çalıştırma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], timers
- timers [Windows Forms], event intervals
- initialization [Windows Forms], Timer components
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], initializing
- procedures [Windows Forms], specific time intervals
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
ms.openlocfilehash: ac2f89619c3e87ebfe5e568bbf27274834b0866d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012457"
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a>Nasıl yapılır: Windows Forms Süreölçer Bileşeni ile Belirlenen Aralıklarda Yordamları Çalıştırma
Bazen bir döngü sona veya bir kümesi zaman aralığı süresi sona erdiğinde çalıştırılan kadar belirli aralıklarla çalışan bir yordam oluşturmak isteyebilirsiniz. <xref:System.Windows.Forms.Timer> Bileşeni gibi bir yordam mümkün kılar.  
  
 Bu bileşen, bir Windows Forms ortamı için tasarlanmıştır. Bir sunucu ortamı için uygun olan bir zamanlayıcı gerekirse bkz [sunucu tabanlı zamanlayıcılar giriş](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
> [!NOTE]
>  Kullanırken bazı sınırlamalar uygulanır <xref:System.Windows.Forms.Timer> bileşeni. Daha fazla bilgi için [Windows Forms süreölçer bileşeninin aralık özelliğiyle ilgili sınırlamalar](limitations-of-the-timer-component-interval-property.md).  
  
## <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a>Süreölçer bileşeni ile belirlenen aralıklarda bir yordamı çalıştırmak için  
  
1. Ekleme bir <xref:System.Windows.Forms.Timer> formunuza. Bu program aracılığıyla yapmak nasıl bir gösterimi için aşağıdaki örnek bölümüne bakın. Visual Studio, bileşenlerin bir forma ekleme desteği de sahiptir. Ayrıca bkz: [nasıl yapılır: Windows Forms'a kullanıcı arabirimi olmadan denetimler ekleme](how-to-add-controls-without-a-user-interface-to-windows-forms.md).  
  
2. Ayarlama <xref:System.Windows.Forms.Timer.Interval%2A> Zamanlayıcı özelliği (milisaniye cinsinden). Bu özellik, yordam yeniden çalıştırmadan önce ne kadar süre geçer belirler.  
  
    > [!NOTE]
    >  Bir zamanlayıcı olaylarının daha sık, daha fazla işlemci zamanı olaya yanıt olarak kullanılır. Bu genel performansını yavaşlatabilir. İhtiyacınız olandan daha küçük bir aralık ayarlamayın.  
  
3. Uygun kod yazmaya <xref:System.Windows.Forms.Timer.Tick> olay işleyicisi. Bu olay, yazdığınız kod içinde belirtilen aralıkta çalışacak <xref:System.Windows.Forms.Timer.Interval%2A> özelliği.  
  
4. Ayarlama <xref:System.Windows.Forms.Timer.Enabled%2A> özelliğini `true` zamanlayıcıyı başlatmak için. <xref:System.Windows.Forms.Timer.Tick> Olay başlayacak gerçekleşmesi, belirlenen aralıkta yordamınız çalıştırma.  
  
5. Uygun ayarlarken <xref:System.Windows.Forms.Timer.Enabled%2A> özelliğini `false` yordamı yeniden çalışmasını durdurmak için. Aralığı ayarını `0` durdurmak Zamanlayıcı neden olmaz.  
  
## <a name="example"></a>Örnek  
 Bu ilk kod örneği, bir saniyelik artışlarla günün saatini izler. Bunu kullanan bir <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.Label>ve <xref:System.Windows.Forms.Timer> formdaki bileşen. <xref:System.Windows.Forms.Timer.Interval%2A> Değerini 1000'e (bir saniyeye eşit) özelliğini ayarlayın. İçinde <xref:System.Windows.Forms.Timer.Tick> olay, etiketin açıklamalı alt yazı geçerli saate ayarlanır. Düğme tıklandığında <xref:System.Windows.Forms.Timer.Enabled%2A> özelliği `false`, etiketin açıklamalı alt yazı güncelleştirme gelen zamanlayıcı durduruluyor. Aşağıdaki kod örneği, bir form olmasını gerektirir bir <xref:System.Windows.Forms.Button> adlı Denetim `Button1`, <xref:System.Windows.Forms.Timer> adlı Denetim `Timer1`ve <xref:System.Windows.Forms.Label> adlı Denetim `Label1`.  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)     
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,    
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,   
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
```  
  
## <a name="example"></a>Örnek  
 Bir döngü tamamlanana kadar bu ikinci kod örneğinde bir yordam her 600 milisaniye çalıştırır. Aşağıdaki kod örneği, bir form olmasını gerektirir bir <xref:System.Windows.Forms.Button> adlı Denetim `Button1`, <xref:System.Windows.Forms.Timer> adlı Denetim `Timer1`ve <xref:System.Windows.Forms.Label> adlı Denetim `Label1`.  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)     
{  
   if (counter >= 10)   
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)   
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.Timer>
- [Süreölçer Bileşeni](timer-component-windows-forms.md)
- [Süreölçer Bileşenine Genel Bakış](timer-component-overview-windows-forms.md)
