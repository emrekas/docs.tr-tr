---
title: 'Nasıl yapılır: Kılavuzlar Arasında Boyutlandırma Özelliklerini Paylaşma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: bd0f812ce9a15628bd0bddf3a88e898311f0a9d3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373133"
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Nasıl yapılır: Kılavuzlar Arasında Boyutlandırma Özelliklerini Paylaşma
Bu örnek arasında satır ve sütunların boyutlandırma verilerini paylaşma gösterir <xref:System.Windows.Controls.Grid> tutarlı boyutlandırma tutmak için öğeleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek iki tanıtır <xref:System.Windows.Controls.Grid> öğeleri bir üst öğenin alt öğeleri olarak <xref:System.Windows.Controls.DockPanel>. <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> Özelliği bağlı <xref:System.Windows.Controls.Grid> üst öğede tanımlanan <xref:System.Windows.Controls.DockPanel>.  
  
 Örneğin, iki kullanarak özellik değeri yönetir <xref:System.Windows.Controls.Button> öğeleri; bir Boolean özelliği değerlerinin her öğe temsil. Zaman <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> özellik değeri ayarı `true`, her sütunda veya satırda üyesi bir <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> bir satır veya sütun içeriğini bağımsız olarak boyutlandırma bilgi paylaşır.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 Aşağıdaki arka plan kod örnek yöntemleri işler, düğmeyi <xref:System.Windows.Controls.Primitives.ButtonBase.Click> olayını başlatır. Bu yöntem çağrılarının sonuçlarını örnek Yazar <xref:System.Windows.Controls.TextBlock> kullanımı ilgili öğeleri al yeni özellik değerlerinin dizeler olarak çıkış yöntemleri.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [Panellere Genel Bakış](panels-overview.md)
