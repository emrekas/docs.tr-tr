---
title: Liste Öğesi İçin UI Otomasyon Öğesi Bulma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 4cc4c976f8e9eb7f1779139f8266e22477d269e4
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57673775"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>Liste Öğesi İçin UI Otomasyon Öğesi Bulma
> [!NOTE]
>  Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı. En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Bu konu nasıl alınacağını gösterir. bir <xref:System.Windows.Automation.AutomationElement> öğenin dizinini bilindiğinde listesindeki bir öğe için.  
  
## <a name="example"></a>Örnek  
 Belirtilen öğe bir listeden birini kullanarak almanın iki yolu aşağıdaki örnekte <xref:System.Windows.Automation.TreeWalker> ve diğer kullanma <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.  
  
 İlk yöntem için daha hızlı olma eğilimindedir [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] kontrol eder, ancak ikinci Windows Presentation Foundation (WPF) denetimler için daha hızlı.  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- [UI Otomasyonu Öğelerini Alma](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
