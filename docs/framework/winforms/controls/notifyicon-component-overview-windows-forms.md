---
title: NotifyIcon Bileşenine Genel Bakış (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
ms.openlocfilehash: def109799ddfb25b6f56a4f18d52bb19f62842f5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645705"
---
# <a name="notifyicon-component-overview-windows-forms"></a><span data-ttu-id="5e0b8-102">NotifyIcon Bileşenine Genel Bakış (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5e0b8-102">NotifyIcon Component Overview (Windows Forms)</span></span>

<span data-ttu-id="5e0b8-103">Windows Forms <xref:System.Windows.Forms.NotifyIcon> bileşeni genellikle çoğu zaman arka planda çalışan ve bir kullanıcı gösterme işlemleri arabiriminin simgeleri göstermek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component is typically used to display icons for processes that run in the background and do not show a user interface much of the time.</span></span> <span data-ttu-id="5e0b8-104">Görev çubuğu durum bildirim alanındaki simgeye tıklayarak erişilebilir bir virüs koruma programı örnek verilebilir.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-104">An example would be a virus protection program that can be accessed by clicking an icon in the status notification area of the taskbar.</span></span>

## <a name="key-properties-of-notifyicons"></a><span data-ttu-id="5e0b8-105">NotifyIcons anahtar özellikleri</span><span class="sxs-lookup"><span data-stu-id="5e0b8-105">Key Properties of NotifyIcons</span></span>

<span data-ttu-id="5e0b8-106">Her <xref:System.Windows.Forms.NotifyIcon> bileşeni durum alanında tek bir simge görüntüler.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-106">Each <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status area.</span></span> <span data-ttu-id="5e0b8-107">Üç arka plan işlemleri ve her biri için bir simge görüntülemek istediğiniz varsa, üç eklemelisiniz <xref:System.Windows.Forms.NotifyIcon> forma bileşenleri.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-107">If you have three background processes and wish to display an icon for each, you must add three <xref:System.Windows.Forms.NotifyIcon> components to the form.</span></span> <span data-ttu-id="5e0b8-108">Anahtar özelliklerini <xref:System.Windows.Forms.NotifyIcon> bileşenidir <xref:System.Windows.Forms.NotifyIcon.Icon%2A> ve <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-108">The key properties of the <xref:System.Windows.Forms.NotifyIcon> component are <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span></span> <span data-ttu-id="5e0b8-109"><xref:System.Windows.Forms.NotifyIcon.Icon%2A> Özelliğini ayarlar durum alanında görüntülenen simge.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-109">The <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property sets the icon that appears in the status area.</span></span> <span data-ttu-id="5e0b8-110">Simgesinin görünmesi sırayla <xref:System.Windows.Forms.NotifyIcon.Visible%2A> özelliği ayarlanmalıdır `true`.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-110">In order for the icon to appear, the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property must be set to `true`.</span></span>

## <a name="notifyicons-options"></a><span data-ttu-id="5e0b8-111">NotifyIcons seçenekleri</span><span class="sxs-lookup"><span data-stu-id="5e0b8-111">NotifyIcons Options</span></span>

<span data-ttu-id="5e0b8-112">Balon ipuçları, kısayol menüleri ve araç ipuçları ile ilişkilendirebilirsiniz bir <xref:System.Windows.Forms.NotifyIcon> kullanıcı yardımcı olmak için.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-112">You can associate balloon tips, shortcut menus, and ToolTips with a <xref:System.Windows.Forms.NotifyIcon> to assist the user.</span></span>

<span data-ttu-id="5e0b8-113">Balon ipuçları görüntüleyebileceğiniz bir <xref:System.Windows.Forms.NotifyIcon> çağırarak <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> zaman span belirtme yöntemi görüntülenecek balon ipucu istiyor.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-113">You can display balloon tips for a <xref:System.Windows.Forms.NotifyIcon> by calling the <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> method specifying the time span you wish the balloon tip to display.</span></span> <span data-ttu-id="5e0b8-114">Metin, simge ve balon ucuyla başlığının belirtebilirsiniz <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> ve <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>sırasıyla.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-114">You can also specify the text, icon and title of the balloon tip with the <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> and <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectively.</span></span> <span data-ttu-id="5e0b8-115"><xref:System.Windows.Forms.NotifyIcon> bileşenleri araç ipuçları ve kısayol menüleri ilişkili.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-115"><xref:System.Windows.Forms.NotifyIcon> components can also have associated ToolTips and shortcut menus.</span></span> <span data-ttu-id="5e0b8-116">Daha fazla bilgi için [ToolTip bileşenine genel bakış](tooltip-component-overview-windows-forms.md) ve [ContextMenu bileşenine genel bakış](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5e0b8-116">For more information, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md) and [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e0b8-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5e0b8-117">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- [<span data-ttu-id="5e0b8-118">NotifyIcon Bileşeni</span><span class="sxs-lookup"><span data-stu-id="5e0b8-118">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
