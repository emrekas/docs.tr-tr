---
title: 'Nasıl yapılır: FlowLayoutPanel Denetiminde Alt Denetimleri Sabitleme ve Yerleştirme'
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: f67733b89d2bde652449e2338362868fdb84bcf3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592945"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Nasıl yapılır: FlowLayoutPanel Denetiminde Alt Denetimleri Sabitleme ve Yerleştirme
<xref:System.Windows.Forms.FlowLayoutPanel> Denetim destekler <xref:System.Windows.Forms.Control.Anchor%2A> ve <xref:System.Windows.Forms.Control.Dock%2A> kendi alt denetimlerindeki özellikler.  
  
### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Sabitleme ve yerleştirme FlowLayoutPanel denetiminde alt denetimleri için  
  
1. Oluşturma bir <xref:System.Windows.Forms.FlowLayoutPanel> formunuzdaki denetimi.  
  
2. Ayarlama <xref:System.Windows.Forms.Control.Width%2A> , <xref:System.Windows.Forms.FlowLayoutPanel> denetimini **300**ve onun <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> için <xref:System.Windows.Forms.FlowDirection.TopDown>.  
  
3. İki <xref:System.Windows.Forms.Button> denetler ve yerleştirebilirsiniz <xref:System.Windows.Forms.FlowLayoutPanel> denetimi.  
  
4. Ayarlama <xref:System.Windows.Forms.Control.Width%2A> ilk düğmenin **200**.  
  
5. Ayarlama <xref:System.Windows.Forms.Control.Dock%2A> özelliği ikinci düğmenin <xref:System.Windows.Forms.DockStyle.Fill>.  
  
    > [!NOTE]
    >  İlk düğmeyi aynı genişlikte ikinci düğme varsayar. Genişliği boyunca genişlemez <xref:System.Windows.Forms.FlowLayoutPanel> denetimi.  
  
6. Ayarlama <xref:System.Windows.Forms.Control.Dock%2A> özelliği ikinci düğmenin `None`. Bu, özgün genişliği varsaymak düğme neden olur.  
  
7. Ayarlama <xref:System.Windows.Forms.Control.Anchor%2A> özelliği ikinci düğmenin `Left, Right`.  
  
    > [!IMPORTANT]
    >  İlk düğmeyi aynı genişlikte ikinci düğme varsayar. Genişliği boyunca genişlemez <xref:System.Windows.Forms.FlowLayoutPanel> denetimi. Sabitleme ve yerleştirme içinde için genel bir kural budur <xref:System.Windows.Forms.FlowLayoutPanel> denetimi: dikey akış yönergeleri için <xref:System.Windows.Forms.FlowLayoutPanel> denetim geniş bir alt denetimin sütunda bir örtük sütun genişliğini hesaplar. Tüm bu sütunla denetimlerinde <xref:System.Windows.Forms.Control.Anchor%2A> veya <xref:System.Windows.Forms.Control.Dock%2A> hizalı ya da örtük bu sütunu sığdırmak için uzatılmış özellikleri. Davranış yatay akış yönleri için benzer bir şekilde çalışır. <xref:System.Windows.Forms.FlowLayoutPanel> Denetim satırdaki en uzun alt denetiminden örtük bir satırın yüksekliğini hesaplar ve bu satırdaki tüm yerleşik veya bağlantılı alt denetimler hizalı veya zımni satırın sığması için boyutu.  
  
## <a name="example"></a>Örnek  
 Bağlantılı ve göreli mavi bir düğme yerleştirilmiş dört düğme aşağıdaki çizimde bir <xref:System.Windows.Forms.FlowLayoutPanel>. <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> Olduğu <xref:System.Windows.Forms.FlowDirection.LeftToRight>.  
  
 ![FlowLayoutPanel bağlama](./media/net-flpanchorexp.gif "NET_FLPanchorExp")  
  
 Bağlantılı ve göreli mavi bir düğme yerleştirilmiş dört düğme aşağıdaki çizimde bir <xref:System.Windows.Forms.FlowLayoutPanel>. <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> Olduğu <xref:System.Windows.Forms.FlowDirection.TopDown>.  
  
 ![FlowLayoutPanel bağlama](./media/vs-flpanchor2.gif "VS_FLPanchor2")  
  
 Aşağıdaki kod örneği, çeşitli gösterir <xref:System.Windows.Forms.Control.Anchor%2A> özellik değerleri için bir <xref:System.Windows.Forms.Button> denetimine bir <xref:System.Windows.Forms.FlowLayoutPanel> denetimi.  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
- Sistem, System.Data System.Drawing ve System.Windows.Forms derlemelere başvuruları.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [FlowLayoutPanel Denetimine Genel Bakış](flowlayoutpanel-control-overview.md)
