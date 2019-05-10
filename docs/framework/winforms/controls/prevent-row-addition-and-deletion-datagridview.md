---
title: 'Nasıl yapılır: Windows Forms DataGridView Denetiminde Satır Ekleme ve Silmeyi Engelleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: d361b0791691fa6a3e1720538c7bf22b14397579
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64654475"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a>Nasıl yapılır: Windows Forms DataGridView Denetiminde Satır Ekleme ve Silmeyi Engelleme
Bazen kullanıcıların yeni veri satırı girme veya var olan satır silme önlemek istersiniz, <xref:System.Windows.Forms.DataGridView> denetimi. <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> Özelliği gösteren yeni kayıtlar için satır denetimi altındaki mevcut olup olmadığını, while <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> özelliği satırları kaldırılıp kaldırılamayacağını belirtir. Aşağıdaki kod örneği, bu özellikleri kullanan ve ayrıca ayarlar <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> salt okunur tamamen denetimi yapma özelliği.  
  
 Visual Studio'da bu görevi için desteği yoktur. Ayrıca bkz: [nasıl yapılır: Engelleme satır eklemeyi ve silmeyi Windows Forms DataGridView denetiminde Tasarımcısı'nı kullanarak](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).  
  
## <a name="example"></a>Örnek  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
- A <xref:System.Windows.Forms.DataGridView> adlı Denetim `dataGridView1`.  
  
- Başvurular <xref:System?displayProperty=nameWithType> ve <xref:System.Windows.Forms?displayProperty=nameWithType> derlemeler.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView Denetimindeki Temel Sütun, Satır ve Hücre Özellikleri](basic-column-row-and-cell-features-wf-datagridview-control.md)
