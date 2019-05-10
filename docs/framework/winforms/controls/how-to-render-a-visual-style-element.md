---
title: 'Nasıl yapılır: Görsel Stilde Öğe İşleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: a2b9524b6a3e3c77d3c68c4d9e138b8c0e2a9373
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662303"
---
# <a name="how-to-render-a-visual-style-element"></a><span data-ttu-id="24499-102">Nasıl yapılır: Görsel Stilde Öğe İşleme</span><span class="sxs-lookup"><span data-stu-id="24499-102">How to: Render a Visual Style Element</span></span>
<span data-ttu-id="24499-103"><xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> Ad alanı sunan <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> arabirimi (UI) öğeleri görsel stilleri tarafından desteklenen Windows kullanıcı temsil eden nesneleri.</span><span class="sxs-lookup"><span data-stu-id="24499-103">The <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespace exposes <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> objects that represent the Windows user interface (UI) elements supported by visual styles.</span></span> <span data-ttu-id="24499-104">Bu konu nasıl kullanılacağını gösterir <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> sınıf, işlenecek <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> temsil eden **Oturumu Kapat** ve **Kapat** başlangıç menüsünde düğmeleri.</span><span class="sxs-lookup"><span data-stu-id="24499-104">This topic demonstrates how to use the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> class to render the <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> that represents the **Log Off** and **Shut Down** buttons of the Start menu.</span></span>  
  
### <a name="to-render-a-visual-style-element"></a><span data-ttu-id="24499-105">Bir görsel stilde öğe işleme için</span><span class="sxs-lookup"><span data-stu-id="24499-105">To render a visual style element</span></span>  
  
1. <span data-ttu-id="24499-106">Oluşturma bir <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> çizmek istediğiniz öğesine ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="24499-106">Create a <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> and set it to the element you want to draw.</span></span> <span data-ttu-id="24499-107">Kullanımına dikkat edin <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> özelliği ve <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> yöntemi; <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> görsel stillerini devre dışı bırakıldı veya bir öğe tanımlanmamış Oluşturucusu bir özel durum oluşturur.</span><span class="sxs-lookup"><span data-stu-id="24499-107">Note the use of the <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> property and the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> method; the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> constructor will throw an exception if visual styles are disabled or an element is undefined.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2. <span data-ttu-id="24499-108">Çağrı <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> yöntem, öğe işleme <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> şu anda temsil eder.</span><span class="sxs-lookup"><span data-stu-id="24499-108">Call the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> method to render the element that the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> currently represents.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="24499-109">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="24499-109">Compiling the Code</span></span>  
 <span data-ttu-id="24499-110">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="24499-110">This example requires:</span></span>  
  
- <span data-ttu-id="24499-111">Öğesinden türetilen özel denetim <xref:System.Windows.Forms.Control> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="24499-111">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
- <span data-ttu-id="24499-112">A <xref:System.Windows.Forms.Form> özel denetimi barındıran.</span><span class="sxs-lookup"><span data-stu-id="24499-112">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
- <span data-ttu-id="24499-113">Başvurular <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, ve <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> ad alanları.</span><span class="sxs-lookup"><span data-stu-id="24499-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24499-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="24499-114">See also</span></span>

- [<span data-ttu-id="24499-115">Denetimleri Görsel Stilde İşleme</span><span class="sxs-lookup"><span data-stu-id="24499-115">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
