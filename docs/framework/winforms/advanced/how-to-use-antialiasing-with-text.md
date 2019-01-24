---
title: 'Nasıl yapılır: Metinle düzgünleştirme kullanma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 64b1c27b9e8b7d405dde5add105ff2e682f8ad87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534114"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="b7356-102">Nasıl yapılır: Metinle düzgünleştirme kullanma</span><span class="sxs-lookup"><span data-stu-id="b7356-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="b7356-103">*Düzgünleştirme* düzensiz çizilen grafik ve bunların görünümünü ve okunabilirliğini geliştirmek için metni kenarlarına düzgünleştirme ifade eder.</span><span class="sxs-lookup"><span data-stu-id="b7356-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="b7356-104">İle yönetilen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sınıflar, daha düşük kaliteli metin yanı sıra, yüksek kaliteli antialiased metin işleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b7356-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="b7356-105">Genellikle, daha yüksek kalite işleme daha fazla işleme zaman daha düşük kaliteli işleme alır.</span><span class="sxs-lookup"><span data-stu-id="b7356-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="b7356-106">Metin kalite düzeyini ayarlamak için ayarlayın <xref:System.Drawing.Graphics.TextRenderingHint%2A> özelliği bir <xref:System.Drawing.Graphics> öğelerinden birine <xref:System.Drawing.Text.TextRenderingHint> numaralandırması</span><span class="sxs-lookup"><span data-stu-id="b7356-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7356-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="b7356-107">Example</span></span>  
 <span data-ttu-id="b7356-108">Aşağıdaki kod örneği, iki farklı ayarlarla metin çizer.</span><span class="sxs-lookup"><span data-stu-id="b7356-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 <span data-ttu-id="b7356-109">Örnek kodun çıktısı aşağıdaki çizimde gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="b7356-109">The following illustration shows the output of the example code:</span></span>  
  
 <span data-ttu-id="b7356-110">![Yazı tipleri metin](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="b7356-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b7356-111">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="b7356-111">Compiling the Code</span></span>  
 <span data-ttu-id="b7356-112">Yukarıdaki kod örneğinde, Windows Forms ile kullanılmak üzere tasarlanmıştır ve gerektirir <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olduğu <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="b7356-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7356-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b7356-113">See also</span></span>
- [<span data-ttu-id="b7356-114">Yazı Tipleri ve Metin Kullanma</span><span class="sxs-lookup"><span data-stu-id="b7356-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
