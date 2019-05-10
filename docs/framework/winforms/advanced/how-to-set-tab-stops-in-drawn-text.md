---
title: 'Nasıl yapılır: Çizilmiş Metinde Sekme Durakları Ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 8e8f1bf193a41530a19e1046e3907b4c926b779f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64637029"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="851f9-102">Nasıl yapılır: Çizilmiş Metinde Sekme Durakları Ayarlama</span><span class="sxs-lookup"><span data-stu-id="851f9-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="851f9-103">Metin için sekme durakları çağırarak ayarlayabilirsiniz <xref:System.Drawing.StringFormat.SetTabStops%2A> yöntemi bir <xref:System.Drawing.StringFormat> nesnesi ve ardından geçirmeden <xref:System.Drawing.StringFormat> nesnesini <xref:System.Drawing.Graphics.DrawString%2A> yöntemi <xref:System.Drawing.Graphics> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="851f9-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="851f9-104"><xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> Sekme duraklarını çizilen metni, mevcut sekmesini genişletebilirsiniz rağmen ekleme desteği kullanarak durdurur mu <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> bayrağı.</span><span class="sxs-lookup"><span data-stu-id="851f9-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="851f9-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="851f9-105">Example</span></span>  
 <span data-ttu-id="851f9-106">Aşağıdaki örnek, 150, 250 ve 350 sekme durakları ayarlar.</span><span class="sxs-lookup"><span data-stu-id="851f9-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="851f9-107">Ardından, kod adları ve test puanlarını sekmeli listesini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="851f9-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="851f9-108">Sekmeli metin aşağıda gösterilmiştir:</span><span class="sxs-lookup"><span data-stu-id="851f9-108">The following illustration shows the tabbed text:</span></span>  
  
 ![Ad ve puanlar sekmeli listesini gösteren ekran görüntüsü.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 <span data-ttu-id="851f9-110">Aşağıdaki kod iki bağımsız değişken geçirir <xref:System.Drawing.StringFormat.SetTabStops%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="851f9-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="851f9-111">İkinci bağımsız değişkeni sekmesini uzaklıkları içeren bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="851f9-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="851f9-112">Geçirilen ilk bağımsız değişken <xref:System.Drawing.StringFormat.SetTabStops%2A> dizideki ilk uzaklığını konumu 0, sınırlayıcı dikdörtgenini sol kenarı ölçülür belirten, 0'dır.</span><span class="sxs-lookup"><span data-stu-id="851f9-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="851f9-113">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="851f9-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="851f9-114">Yukarıdaki örnekte, Windows Forms ile kullanılmak üzere tasarlanmıştır ve gerektirir <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olduğu <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="851f9-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="851f9-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="851f9-115">See also</span></span>

- [<span data-ttu-id="851f9-116">Yazı Tipleri ve Metin Kullanma</span><span class="sxs-lookup"><span data-stu-id="851f9-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="851f9-117">Nasıl yapılır: GDI ile metin çizme</span><span class="sxs-lookup"><span data-stu-id="851f9-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
