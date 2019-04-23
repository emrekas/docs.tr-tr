---
title: 'Nasıl yapılır: Algılama Enter tuşuna basıldığında'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a99da5804bbc31897198b9b6d9e21da9f17dfe26
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204620"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Nasıl yapılır: Algılama Enter tuşuna basıldığında
Bu örnek nasıl algılanacağını gösterir <xref:System.Windows.Input.Key.Enter> klavyede tuşuna basıldığında.  
  
 Bu örnekte oluşan bir [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] dosyası ve bir arka plan kod dosyası.  
  
## <a name="example"></a>Örnek  
 Kullanıcının bastığında <xref:System.Windows.Input.Key.Enter> anahtarını <xref:System.Windows.Controls.TextBox>, başka bir bölümünde giriş metin kutusunda görüntülenen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 Aşağıdaki [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] oluşur kullanıcı arabirimi oluşturan bir <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock>ve <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Aşağıdaki kod oluşturur <xref:System.Windows.UIElement.KeyDown> olay işleyicisi.  Basıldığında anahtar bulunuyorsa <xref:System.Windows.Input.Key.Enter> anahtar, bir ileti görüntülenir <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Girişe Genel Bakış](input-overview.md)
- [Yönlendirilmiş Olaylara Genel Bakış](routed-events-overview.md)
