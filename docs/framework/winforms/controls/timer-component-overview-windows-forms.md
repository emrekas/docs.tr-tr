---
title: Süreölçer Bileşenine Genel Bakış (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 4b0b9a8d57eae774a62c7807bfa071508bb78c54
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660963"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="ddeb4-102">Süreölçer Bileşenine Genel Bakış (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ddeb4-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="ddeb4-103">Windows Forms <xref:System.Windows.Forms.Timer> düzenli aralıklarla bir olayı oluşturan bir bileşendir.</span><span class="sxs-lookup"><span data-stu-id="ddeb4-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="ddeb4-104">Bu bileşen, bir Windows Forms ortamı için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="ddeb4-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="ddeb4-105">Bir sunucu ortamı için uygun olan bir zamanlayıcı gerekirse bkz [sunucu tabanlı zamanlayıcılar giriş](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="ddeb4-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="ddeb4-106">Anahtar özellikleri, yöntemleri ve olayları</span><span class="sxs-lookup"><span data-stu-id="ddeb4-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="ddeb4-107">Aralıkların uzunluğunu tarafından tanımlanan <xref:System.Windows.Forms.Timer.Interval%2A> özelliği, değeri olan milisaniye cinsinden.</span><span class="sxs-lookup"><span data-stu-id="ddeb4-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="ddeb4-108">Bileşen etkinleştirildiğinde <xref:System.Windows.Forms.Timer.Tick> olayı her aralığı.</span><span class="sxs-lookup"><span data-stu-id="ddeb4-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="ddeb4-109">Burada yürütülecek kodu eklersiniz budur.</span><span class="sxs-lookup"><span data-stu-id="ddeb4-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="ddeb4-110">Daha fazla bilgi için [nasıl yapılır: Windows Forms süreölçer bileşeni ile belirlenen aralıklarda yordamları çalıştırma](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="ddeb4-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="ddeb4-111">Anahtar yöntemlerini <xref:System.Windows.Forms.Timer> bileşenidir <xref:System.Windows.Forms.Timer.Start%2A> ve <xref:System.Windows.Forms.Timer.Stop%2A>, açma ve kapatma Zamanlayıcı açın.</span><span class="sxs-lookup"><span data-stu-id="ddeb4-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="ddeb4-112">Zamanlayıcı kapalı olduğunda sıfırlar; duraklatmak için bir yolu yoktur bir <xref:System.Windows.Forms.Timer> bileşeni.</span><span class="sxs-lookup"><span data-stu-id="ddeb4-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddeb4-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ddeb4-113">See also</span></span>
- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="ddeb4-114">Süreölçer Bileşeni</span><span class="sxs-lookup"><span data-stu-id="ddeb4-114">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)
- [<span data-ttu-id="ddeb4-115">Windows Forms Süreölçer Bileşeninin Aralık Özelliğiyle İlgili Sınırlamalar</span><span class="sxs-lookup"><span data-stu-id="ddeb4-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
