---
title: UI Otomasyon İstemcileri İçin Denetim Düzeni Eşleştirmesi
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 829df66f49d5df5f5c8cf8d2b6cfa74f0a2172dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609899"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>UI Otomasyon İstemcileri İçin Denetim Düzeni Eşleştirmesi
> [!NOTE]
>  Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı. En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Bu konu, denetim türlerini ve bunların ilişkili denetim düzenleri listeler.  
  
 Aşağıdaki tabloda, Denetim düzenleri aşağıdaki kategorilere göre düzenler:  
  
- Desteklenen. Denetim, bu denetim düzenini desteklemelidir.  
  
- Koşullu desteği. Denetim, denetimin durumunun bağlı olarak bu denetim düzeni destekleyebilir.  
  
- Desteklenmez. Denetim, bu denetim düzeni desteklemiyor; özel denetimler, bu denetim düzeni destekleyebilir.  
  
> [!NOTE]
>  Bazı denetimler, denetimi işlevlerini bağlı olarak birkaç denetim desenleri için koşullu destek vardır. Örneğin, menü öğesi denetimi için koşullu destek sahip <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>, veya <xref:System.Windows.Automation.SelectionItemPattern> menü denetimi, işlev bağlı olarak, Denetim düzeni.  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>İstemciler İçin UI Otomasyon Denetim Düzenleri  
  
|Denetim türü|Desteklenir|Koşullu destek|Desteklenmez|  
|------------------|---------------|-------------------------|-------------------|  
|Düğme|Yok.|Çağırma, Değiştir, Genişlet ve Daralt|Yok.|  
|Takvim|Kılavuz, tablo|Seçim, kaydırma|Değer|  
|Onay kutusu|İki Durumlu Düğme|Yok.|None|  
|Birleşik Giriş Kutusu|Genişlet ve Daralt|Seçim, değer|Kaydırma|  
|Veri Kılavuzu|Kılavuz|Kaydır, seçimi, tablo|Yok.|  
|Veri Öğesi|Seçim Öğesi|Daraltma, kılavuz öğesi, kaydırma öğesi, tablo, geçiş, değer'ı genişletin.|Yok.|  
|Belge|Metin|Kaydırma, değer|Yok.|  
|Düzenle|Yok.|Aralık değeri, bir metin değeri|Yok.|  
|Grup|Yok.|Genişlet ve Daralt|Yok.|  
|Üstbilgi|Yok.|Dönüştürme|Yok.|  
|Üstbilgi Öğesi|None|Dönüştürme, çağırma|Yok.|  
|Köprü|Çağır|Değer|Yok.|  
|Görüntü|Yok.|Kılavuz öğesi, Tablo öğesi|Seçim öğesi çağırma|  
|List|Yok.|Kılavuz, birden çok görünüm Kaydır, seçimi|Tablo|  
|Liste öğesi|Seçim Öğesi|Genişlet ve Daralt, kılavuz öğesi çağırmak, kaydırma öğesi, Değiştir, değer|Yok.|  
|Menü|None|Yok.|None|  
|Menü Çubuğu|None|Dönüştürme Daralt, Dock'ı genişletin|Yok.|  
|Menü Öğesi|None|Genişlet ve Daralt, seçim öğesi geçiş çağırma|Yok.|  
|Bölme|None|Dock. Kaydırma, dönüştürme|Pencere|  
|İlerleme Çubuğu|Yok.|Aralık değeri|None|  
|Radyo Düğmesi|Seçim Öğesi|Yok.|İki Durumlu Düğme|  
|Kaydırma Çubuğu|Yok.|Aralık Değeri|Kaydırma|  
|Ayırıcı|Yok.|Yok.|Yok.|  
|Kaydırıcı|None|Aralık değeri, seçim, değeri|Yok.|  
|Değer Değiştirici|None|Aralık değeri, seçim, değeri|Yok.|  
|Bölünmüş Düğme|Çağırma, Genişlet ve Daralt|None|None|  
|Durum Çubuğu|None|Kılavuz|None|  
|Tab|Seçim|Kaydırma|Yok.|  
|Sekme Öğesi|Seçim Öğesi|Yok.|Çağır|  
|Tablo|Kılavuz, kılavuz öğesi, tablo, Tablo öğesi|Yok.|Yok.|  
|Metin|None|Kılavuz öğesi, Tablo öğesi metni|Değer|  
|Parmak|Dönüştürme|Yok.|Yok.|  
|Başlık Çubuğu|None|Yok.|Yok.|  
|Araç çubuğu|None|Yerleştirme, genişletme daraltma, dönüştürme|None|  
|Araç İpucu|None|Pencere metni|Yok.|  
|Ağaç|Yok.|Kaydır, seçimi|Yok.|  
|Ağaç Öğesi|Genişlet ve Daralt|Kaydırma öğesi seçim öğesi, geçiş çağırma|None|  
|Pencere|Dönüştürme, penceresi|Dock|Yok.|  
  
> [!NOTE]
>  Bir denetim türü listelenen herhangi bir desteklenen denetimi desen varken bu koşullu denetim desenlerden birini hiç desteklenecek koşullu olarak desteklenen denetim düzenleri, bir veya daha fazla varsa zaman.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [UI Otomasyonuna Genel Bakış](../../../docs/framework/ui-automation/ui-automation-overview.md)
