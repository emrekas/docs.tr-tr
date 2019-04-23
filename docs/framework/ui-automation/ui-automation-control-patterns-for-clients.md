---
title: İstemciler İçin UI Otomasyon Denetim Düzenleri
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control patterns for clients
- control patterns, UI Automation clients
ms.assetid: 571561d8-5f49-43a9-a054-87735194e013
ms.openlocfilehash: 1b0d374c9dc3e24302a8acfbc56cd9468f41def5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159842"
---
# <a name="ui-automation-control-patterns-for-clients"></a>İstemciler İçin UI Otomasyon Denetim Düzenleri
> [!NOTE]
>  Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı. En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Bu genel bakış istemciler için UI Otomasyonu denetim düzenleri ortaya çıkarır. UI Otomasyonu istemci hakkında bilgilere erişmek için Denetim düzenleri nasıl kullanabileceğinizi bilgi içeren [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].  
  
 Denetim desenlerini kategorilere ayırmak ve denetim türünü veya denetimin görünümünü bağımsız bir denetimin işlevselliği göstermek için bir yol sağlar. UI Otomasyon istemcileri inceleyebilirsiniz bir <xref:System.Windows.Automation.AutomationElement> denetleyen belirlemek için desenler desteklenir ve denetimin davranışını yararlandığından emin.  
  
 Denetim desenlerini tam bir listesi için bkz. [UI Otomasyon denetim düzenlerine genel bakış](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
<a name="uiautomation_getting_control_patterns"></a>   
## <a name="getting-control-patterns"></a>Denetim desenlerini alma  
 İstemciler bir denetim deseni almak bir <xref:System.Windows.Automation.AutomationElement> ya da çağırarak <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> veya <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType>.  
  
 İstemcileri <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> yöntemi veya bireysel `IsPatternAvailable` özelliği (örneğin, <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>) üzerinde bir desen veya grup desenlerinin desteklenip desteklenmediğini belirlemek için <xref:System.Windows.Automation.AutomationElement>. Bununla birlikte, Denetim düzeni alın ve test etme girişiminde daha verimli bir `null` desteklenen özellikleri kontrol edin ve daha az çapraz işlem aramaları sonuçları bu yana denetim düzeni almak için daha başvuru.  
  
 Aşağıdaki örnek nasıl alındığını anlatan bir <xref:System.Windows.Automation.TextPattern> denetimi deseni bir <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIATextPattern_snip#1037](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#1037)]  
  
<a name="uiautomation_properties_on_control_patterns"></a>   
## <a name="retrieving-properties-on-control-patterns"></a>Denetim desenlerini alma özellikleri  
 İstemciler, özellik değerlerine göre denetim desenlerini ya da çağırarak alabilir <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> veya <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> ve nesne atama için uygun bir tür döndürdü. Daha fazla bilgi için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] özellikleri görmek [istemciler için UI Otomasyon özellikleri](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
 Ek olarak `GetPropertyValue` yöntem, özellik değerlerini alınabilir aracılığıyla [!INCLUDE[TLA#tla_clr](../../../includes/tlasharptla-clr-md.md)] erişmek için erişimciler [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] desen özellikleri.  
  
<a name="uiautomation_with_variable_patterns"></a>   
## <a name="controls-with-variable-patterns"></a>Değişken desenler denetimleriyle  
 Bazı denetim türleri durumlarına ya da Denetim kullanılıyor şekilde bağlı olarak farklı desenleri destekler. Örnekler denetimlerin değişken desenler olabilir liste görünümleri (küçük resimleri, kutucukları, simgeler, listesi, Ayrıntılar) [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] grafikleri (pasta, çubuk, hücre değerini bir formülle bir çizgi), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)]ait belge alan (Normal, Web düzeni anahat, yazdırma düzeni, yazdırma Önizleme) ve [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] css'li dış görünümler.  
  
 Özel denetim türlerini uygulayan denetimlerin işlevleri temsil etmek için gereken denetim düzenleri herhangi bir kümesi olabilir.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [UI Otomasyonu Denetim Desenleri](../../../docs/framework/ui-automation/ui-automation-control-patterns.md)
- [UI Otomasyonu Metin Deseni](../../../docs/framework/ui-automation/ui-automation-text-pattern.md)
- [UI Otomasyonu Kullanarak Denetim Çağırma](../../../docs/framework/ui-automation/invoke-a-control-using-ui-automation.md)
- [UI Otomasyonunu Kullanarak Onay Kutusunun Değiştir Durumunu Alma](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [UI Otomasyonu İstemcileri İçin Denetim Düzeni Eşlemesi](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)
- [Metin örnek textpattern öğesine Ekle](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText)
- [TextPattern arama ve seçim örneği](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/FindText)
- [InvokePattern'ı, ExpandCollapsePattern'ı ve TogglePattern'ı örneği](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
