---
title: 'Nasıl yapılır: Olay Tabanlı Zaman Uyumsuz Deseni Destekleyen Bileşenleri Kullanma'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
ms.openlocfilehash: 9ac98b5c576c065f8944714c72b492539e0d2f05
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330889"
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Nasıl yapılır: Olay Tabanlı Zaman Uyumsuz Deseni Destekleyen Bileşenleri Kullanma
Birçok bileşen iş zaman uyumsuz olarak gerçekleştirme seçeneğini içeren sağlar. <xref:System.Media.SoundPlayer> Ve <xref:System.Windows.Forms.PictureBox> bileşenleri, örneğin, yüklemenizi ses ve kesinti olmadan çalışan, ana iş parçacığı devam ederken "arka planda" görüntüleri etkinleştirin.  
  
 Destekleyen bir sınıf üzerinde zaman uyumsuz metotlar kullanma [olay tabanlı zaman uyumsuz desene genel bakış](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) bileşenin bir olay işleyicisi ekleme olarak basit olabilir _MethodName_  **Tamamlanan** olduğu gibi herhangi bir olay için olay. Çağırdığınızda _MethodName_**zaman uyumsuz** yöntemi, uygulamanız çalışmaya devam eder kadar kesintisiz _MethodName_**Tamamlandı** olayı oluşturulur. Olay işleyicisinde, incelemeniz <xref:System.ComponentModel.AsyncCompletedEventArgs> zaman uyumsuz işlem başarıyla tamamlanırsa veya iptal edildi belirlemek için parametre.  
  
 Olay işleyicileri kullanma hakkında daha fazla bilgi için bkz. [olay işleyicilerine genel bakış](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 Aşağıdaki yordam zaman uyumsuz resim yükleme yeteneğini kullanmayı gösterir. bir <xref:System.Windows.Forms.PictureBox> denetimi.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>Zaman uyumsuz olarak görüntü yüklemek bir PictureBox denetimini etkinleştirmek için  
  
1. Bir örneğini oluşturmak <xref:System.Windows.Forms.PictureBox> formunuza bileşen.  
  
2. Bir olay işleyicisi atama <xref:System.Windows.Forms.PictureBox.LoadCompleted> olay.  
  
     Zaman uyumsuz indirme sırasında oluşmuş olabilecek hataları kontrol edin. İptalleri denetlemek burada budur.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3. Adlı iki düğme ekleyin `loadButton` ve `cancelLoadButton`, form. Ekleme <xref:System.Windows.Forms.Control.Click> başlatmak ve yüklemeyi iptal etmek için olay işleyicileri.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4. Uygulamanızı çalıştırın.  
  
     Görüntü yükleme devam ettikçe form serbestçe hareket, simge durumuna küçültün ve, en üst düzeye çıkarın.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Arka Planda İşlem Çalıştırma](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Olay Tabanlı Zaman Uyumsuz Desene Genel Bakış](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
