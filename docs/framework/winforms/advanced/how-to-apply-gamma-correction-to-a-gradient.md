---
title: 'Nasıl yapılır: Bir Gradyana Gama Düzeltmesi Uygulama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: 066ccc649105018d20cb86b6e576a1a238e0dc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973272"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="fa1c0-102">Nasıl yapılır: Bir Gradyana Gama Düzeltmesi Uygulama</span><span class="sxs-lookup"><span data-stu-id="fa1c0-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="fa1c0-103">Fırçanın ayarlayarak gama düzeltmesi için doğrusal gradyan fırçası etkinleştirebilirsiniz <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> özelliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="fa1c0-104">Ayarlayarak gama düzeltmesi devre dışı bırakabilirsiniz <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> özelliğini `false`.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="fa1c0-105">Gama düzeltmesi, varsayılan olarak devre dışıdır.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa1c0-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="fa1c0-106">Example</span></span>  

<span data-ttu-id="fa1c0-107">Aşağıdaki örnek, bir denetimin adlı bir yöntem <xref:System.Windows.Forms.Control.Paint> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="fa1c0-108">Örneğin, doğrusal gradyan fırçası oluşturur ve iki dikdörtgenler doldurmak için bu fırça kullanır.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="fa1c0-109">İlk dikdörtgen gama düzeltmesi doldurulur ve İkinci dikdörtgeni gama düzeltmesi ile doldurulur.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="fa1c0-110">Aşağıdaki çizimde, iki Dolu Dikdörtgen gösterilir.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="fa1c0-111">Gama düzeltmesi yok, üst dikdörtgen, ortadaki koyu görünür.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="fa1c0-112">Daha fazla Tekdüzen yoğunluğu olan gama düzeltmesi varsa, alt dikdörtgen görünür.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="fa1c0-113">![Gradyan](./media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="fa1c0-113">![Gradient](./media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa1c0-114">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="fa1c0-114">Compiling the Code</span></span>  
 <span data-ttu-id="fa1c0-115">Yukarıdaki örnekte, Windows Forms ile kullanılmak üzere tasarlanmıştır ve gerektirir <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olduğu <xref:System.Windows.Forms.Control.Paint> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa1c0-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fa1c0-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="fa1c0-117">Şekilleri Doldurmak için Gradyan Fırçası Kullanma</span><span class="sxs-lookup"><span data-stu-id="fa1c0-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
