---
title: 'Nasıl yapılır: Kaydırıcı Üzerinde İşaretleri Özelleştirme'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: b6ade07b0b4c04578d2523d6d8ba992b8b2d31f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696678"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="40325-102">Nasıl yapılır: Kaydırıcı Üzerinde İşaretleri Özelleştirme</span><span class="sxs-lookup"><span data-stu-id="40325-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="40325-103">Bu örnek nasıl oluşturulacağını gösterir. bir <xref:System.Windows.Controls.Slider> çizgilerinin olan denetim.</span><span class="sxs-lookup"><span data-stu-id="40325-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40325-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="40325-104">Example</span></span>  
 <span data-ttu-id="40325-105"><xref:System.Windows.Controls.Primitives.TickBar> Ayarladığınızda görüntüler <xref:System.Windows.Controls.Slider.TickPlacement%2A> dışında bir değere <xref:System.Windows.Controls.Primitives.TickPlacement.None>, varsayılan değer olan.</span><span class="sxs-lookup"><span data-stu-id="40325-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="40325-106">Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir <xref:System.Windows.Controls.Slider> ile bir <xref:System.Windows.Controls.Primitives.TickBar> işaretleri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="40325-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="40325-107"><xref:System.Windows.Controls.Slider.TickPlacement%2A> Ve <xref:System.Windows.Controls.Slider.TickFrequency%2A> özelliklerini değer çizgilerinin ve aralarındaki aralığı konumunu tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="40325-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="40325-108">Taşıdığınızda <xref:System.Windows.Controls.Primitives.Thumb>, araç ipuçlarını görüntüleme değerini <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="40325-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="40325-109"><xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> Özelliği, araç ipucunun nerede gerçekleştiği tanımlar.</span><span class="sxs-lookup"><span data-stu-id="40325-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="40325-110"><xref:System.Windows.Controls.Primitives.Thumb> Hareketleri çünkü çizgilerinin konumuna karşılık gelen <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> ayarlanır `true`.</span><span class="sxs-lookup"><span data-stu-id="40325-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="40325-111">Aşağıdaki örnek nasıl kullanılacağını gösterir <xref:System.Windows.Controls.Slider.Ticks%2A> boyunca değer çizgisi oluşturmak için özellik <xref:System.Windows.Controls.Slider> düzensiz aralıklarla.</span><span class="sxs-lookup"><span data-stu-id="40325-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="40325-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="40325-112">See also</span></span>
- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [<span data-ttu-id="40325-113">Kaydırıcı ile ilgili nasıl yapılır konuları</span><span class="sxs-lookup"><span data-stu-id="40325-113">Slider How-to Topics</span></span>](https://msdn.microsoft.com/library/534be86c-afb2-425d-8186-631278a9925e)
