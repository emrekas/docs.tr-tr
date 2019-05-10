---
title: 'Nasıl yapılır: TableLayoutPanel Denetiminde Bir Denetimi Hizalama ve Uzatma'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210360"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="347da-102">Nasıl yapılır: TableLayoutPanel Denetiminde Bir Denetimi Hizalama ve Uzatma</span><span class="sxs-lookup"><span data-stu-id="347da-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>

<span data-ttu-id="347da-103">Hizalama ve esnetme denetimlerinde bir <xref:System.Windows.Forms.TableLayoutPanel> ile <xref:System.Windows.Forms.Control.Anchor%2A> ve <xref:System.Windows.Forms.Control.Dock%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="347da-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>

## <a name="align-and-stretch-a-control"></a><span data-ttu-id="347da-104">Hizalama ve denetim Uzat</span><span class="sxs-lookup"><span data-stu-id="347da-104">Align and stretch a control</span></span>

1. <span data-ttu-id="347da-105">Visual Studio'da sürükleyin bir <xref:System.Windows.Forms.TableLayoutPanel> denetimi **araç kutusu** formunuza.</span><span class="sxs-lookup"><span data-stu-id="347da-105">In Visual Studio, drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="347da-106">Sürükleme bir <xref:System.Windows.Forms.Button> denetimi **araç kutusu** sol üst hücresine <xref:System.Windows.Forms.TableLayoutPanel> denetimi.</span><span class="sxs-lookup"><span data-stu-id="347da-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="347da-107"><xref:System.Windows.Forms.Button> Denetim hücrede ortalanır.</span><span class="sxs-lookup"><span data-stu-id="347da-107">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>

3. <span data-ttu-id="347da-108">Değerini <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Anchor%2A> özelliğini `Left,Right`.</span><span class="sxs-lookup"><span data-stu-id="347da-108">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="347da-109"><xref:System.Windows.Forms.Button> Denetim genişliği eşleşecek şekilde uzatır.</span><span class="sxs-lookup"><span data-stu-id="347da-109">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>

4. <span data-ttu-id="347da-110">Değerini <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Anchor%2A> özelliğini `Top,Bottom`.</span><span class="sxs-lookup"><span data-stu-id="347da-110">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="347da-111"><xref:System.Windows.Forms.Button> Denetim hücre yüksekliği eşleşecek şekilde uzatır.</span><span class="sxs-lookup"><span data-stu-id="347da-111">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>

5. <span data-ttu-id="347da-112">Değerini <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Dock%2A> özelliğini <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="347da-112">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="347da-113"><xref:System.Windows.Forms.Button> Hücreyi dolduracak şekilde denetimi genişletir.</span><span class="sxs-lookup"><span data-stu-id="347da-113">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>

6. <span data-ttu-id="347da-114">Değerini <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Dock%2A> özelliğini <xref:System.Windows.Forms.DockStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="347da-114">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="347da-115"><xref:System.Windows.Forms.Button> Denetimi tipini özgün boyutuna döner ve hücresinin sol üst köşeye taşır.</span><span class="sxs-lookup"><span data-stu-id="347da-115">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="347da-116">**Windows Form Tasarımcısı** ayarladı <xref:System.Windows.Forms.Control.Anchor%2A> özelliğini `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="347da-116">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>

7. <span data-ttu-id="347da-117">Değerini <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Anchor%2A> özelliğini `Bottom,Right`.</span><span class="sxs-lookup"><span data-stu-id="347da-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="347da-118"><xref:System.Windows.Forms.Button> Denetimi hücrenin sağ alt köşeye taşır.</span><span class="sxs-lookup"><span data-stu-id="347da-118">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>

8. <span data-ttu-id="347da-119">Değerini <xref:System.Windows.Forms.Button> denetimin <xref:System.Windows.Forms.Control.Anchor%2A> özelliğini <xref:System.Windows.Forms.AnchorStyles.None>.</span><span class="sxs-lookup"><span data-stu-id="347da-119">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="347da-120"><xref:System.Windows.Forms.Button> Denetimi hücrenin merkezine taşır.</span><span class="sxs-lookup"><span data-stu-id="347da-120">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>

## <a name="see-also"></a><span data-ttu-id="347da-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="347da-121">See also</span></span>

- [<span data-ttu-id="347da-122">TableLayoutPanel Denetimi</span><span class="sxs-lookup"><span data-stu-id="347da-122">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
