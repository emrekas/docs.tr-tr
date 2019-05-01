---
title: 'Nasıl yapılır: Windows Forms DataGridView Denetimi İçin Varsayılan Hücre Stillerini Ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: e52729a4ff5b95cd45a970068f1874ad77f8ce35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912892"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a>Nasıl yapılır: Windows Forms DataGridView Denetimi İçin Varsayılan Hücre Stillerini Ayarlama
İle <xref:System.Windows.Forms.DataGridView> denetimi tüm denetim ve özel sütunlar ve satırlar için varsayılan hücre stilleri belirtebilirsiniz. Bu varsayılan aşağı sütun düzeyi sonra satır düzeyinde sonra hücre düzeyi denetim düzeyden filtreleyin. Belirli bir varsa <xref:System.Windows.Forms.DataGridViewCellStyle> hücre düzeyinde özelliği ayarlı değil, satır düzeyinde varsayılan özellik ayarı kullanılır. Özellik ayrıca satır düzeyinde ayarlanmazsa, varsayılan sütun ayarı kullanılır. Son olarak, özellik ayrıca, varsayılan sütun düzeyinde ayarlanmazsa @encryptor_type <xref:System.Windows.Forms.DataGridView> ayarı kullanılır. Bu ayar, yinelenen özellik ayarları farklı düzeylere gerek kalmadan önleyebilirsiniz. Her düzeyde yukarıdaki düzeyleri farklı stilleri belirtmeniz yeterlidir. Daha fazla bilgi için [Windows Forms DataGridView denetimindeki hücre stilleri](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Visual Studio'da bu görevi için kapsamlı desteği yoktur.  Ayrıca bkz: [nasıl yapılır: DataGridView denetimi Tasarımcı kullanarak Windows formları için varsayılan hücre stilleri ve veri biçimleri ayarlama](default-cell-styles-datagridview.md).  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a>Varsayılan hücre stilleri program üzerinden ayarlamak için  
  
1. Özelliklerini ayarlama <xref:System.Windows.Forms.DataGridViewCellStyle> üzerinden alınan <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> özelliği.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2. Oluşturma ve başlatma yeni <xref:System.Windows.Forms.DataGridViewCellStyle> birden çok satır ve sütun tarafından kullanılmak üzere nesneleri.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3. Ayarlama `DefaultCellStyle` belirli satırlar ve sütunlar özelliği.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a>Örnek  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
- A <xref:System.Windows.Forms.DataGridView> adlı Denetim `dataGridView1`.  
  
- Başvurular <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, ve <xref:System.Windows.Forms?displayProperty=nameWithType> derlemeler.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Çok büyük veri kümeleriyle çalışırken maksimum ölçeklenebilirlik elde etmek için paylaşmalıdır <xref:System.Windows.Forms.DataGridViewCellStyle> birden çok satır, sütun veya ayrı ayrı ayrı ayrı öğeler stil özelliklerini ayarlama yerine aynı stilleri kullanıp hücreleri nesneleri. Ayrıca, paylaşılan satırlar oluşturmak ve bunları kullanarak erişim <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> özelliği. Daha fazla bilgi için [Windows Forms DataGridView denetimini ölçeklendirme için en iyi yöntemler](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView Denetimindeki Temel Biçim ve Stiller](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView Denetimindeki Hücre Stilleri](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView Denetimini Ölçeklendirme için En İyi Yöntemler](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Nasıl yapılır: Windows Forms DataGridView denetimi için alternatif satır stillerini ayarlama](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
