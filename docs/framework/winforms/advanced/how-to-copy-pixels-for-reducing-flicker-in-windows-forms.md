---
title: 'Nasıl yapılır: Windows Forms’da Titreşimi Azaltmak için Piksel Kopyalama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: 5a18539153c64a5059d8079f6e245115b026bb91
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950143"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="d9643-102">Nasıl yapılır: Windows Forms’da Titreşimi Azaltmak için Piksel Kopyalama</span><span class="sxs-lookup"><span data-stu-id="d9643-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="d9643-103">Basit bir grafiğe animasyon uyguladığınızda, kullanıcılar bazen titreşmeye veya diğer istenmeyen görsel efektlere de karşılaşabilir.</span><span class="sxs-lookup"><span data-stu-id="d9643-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="d9643-104">Bu sorunu sınırlamanın bir yolu, grafikte bir "BitBlt" işlemi kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="d9643-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="d9643-105">BitBlt, piksellerin kaynak dikdörtgenindeki renk verisinin "bit bloktan blok aktarımı", piksellerin hedef dikdörtgenine kadar olur.</span><span class="sxs-lookup"><span data-stu-id="d9643-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="d9643-106">Windows Forms ile BitBlt, <xref:System.Drawing.Graphics.CopyFromScreen%2A> <xref:System.Drawing.Graphics> sınıfının yöntemi kullanılarak gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="d9643-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="d9643-107">Yönteminin parametrelerinde, kaynak ve hedef (as noktaları), kopyalanacak alanın boyutu ve yeni şekli çizmek için kullanılan grafik nesnesi belirtirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d9643-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="d9643-108">Aşağıdaki örnekte, bir şekil <xref:System.Windows.Forms.Control.Paint> olay işleyicisindeki formda çizilir.</span><span class="sxs-lookup"><span data-stu-id="d9643-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="d9643-109">Sonra, <xref:System.Drawing.Graphics.CopyFromScreen%2A> şekli yinelemek için yöntemi kullanılır.</span><span class="sxs-lookup"><span data-stu-id="d9643-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9643-110">Formun <xref:System.Windows.Forms.Control.DoubleBuffered%2A> özelliğinin özelliği olarak `true` ayarlanması, <xref:System.Windows.Forms.Control.Paint> olaydaki grafik tabanlı kodun çift arabellekli olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="d9643-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="d9643-111">Bu, aşağıdaki kodu kullanırken herhangi bir ayrılabilir performans kazancı olmasa da, daha karmaşık grafik işleme kodu ile çalışırken göz önünde bulundurmanız gereken bir şeydir.</span><span class="sxs-lookup"><span data-stu-id="d9643-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9643-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="d9643-112">Example</span></span>  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d9643-113">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="d9643-113">Compiling the Code</span></span>  
 <span data-ttu-id="d9643-114">Yukarıdaki kod formun <xref:System.Windows.Forms.Control.Paint> olay işleyicisinde çalıştırılır, böylece grafik form yeniden çizilene kadar devam eder.</span><span class="sxs-lookup"><span data-stu-id="d9643-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="d9643-115">Bu nedenle, form başka bir form tarafından yeniden boyutlandırılmışsa veya <xref:System.Windows.Forms.Form.Load> gizlendiyse çizilen içerik yeniden çizilmez olduğundan, olay işleyicisinde grafik ile ilgili yöntemleri çağırmayın.</span><span class="sxs-lookup"><span data-stu-id="d9643-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9643-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d9643-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d9643-117">Windows Forms’da Grafikler ve Çizim</span><span class="sxs-lookup"><span data-stu-id="d9643-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="d9643-118">Çizgiler ve Şekiller Çizmek için Kalem Kullanma</span><span class="sxs-lookup"><span data-stu-id="d9643-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
