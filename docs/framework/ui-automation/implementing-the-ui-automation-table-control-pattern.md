---
title: UI Otomasyonu Tablo Denetim Düzenini Uygulama
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: ece031a25241ffe07eca1bcb99eb6f50984d0cc0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700562"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a>UI Otomasyonu Tablo Denetim Düzenini Uygulama
> [!NOTE]
>  Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı. En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Bu konu, yönergeleri ve uygulama kuralları tanıtır <xref:System.Windows.Automation.Provider.ITableProvider>, özellikler, yöntemler ve olaylar hakkında bilgiler dahil olmak üzere. Ek başvurular bağlantılar genel bakış sonunda listelenmiştir.  
  
 <xref:System.Windows.Automation.TablePattern> Denetim düzeni, alt öğelerinin koleksiyonu için kapsayıcı işlevi gören denetimleri desteklemek için kullanılır. Bu öğenin alt öğeleri uygulamalıdır <xref:System.Windows.Automation.Provider.ITableItemProvider> ve satır ve sütun tarafından çevrilebilen bir iki boyutlu mantıksal koordinat sisteminde düzenlenir. Bu denetim düzeni benzer <xref:System.Windows.Automation.Provider.IGridProvider>, tüm uygulama denetim ayrım ile <xref:System.Windows.Automation.Provider.ITableProvider> her alt öğesi için bir sütun ve/veya satır üst bilgisi ilişkisi kullanıma sunması gerekir. Bu denetim düzeni uygulama denetimleri örnekleri için bkz: [denetim düzeni eşlemesi için UI Otomasyonu istemcileri](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Uygulama yönergeleri ve kuralları  
 Tablo denetim düzeni uygularken aşağıdaki yönergeler ve kuralları dikkat edin:  
  
-   Tek tek hücreleri içeriği erişimi olan bir iki boyutlu bir mantıksal koordinat sistemini veya gerekli eşzamanlı uygulaması tarafından sağlanan dizi aracılığıyla <xref:System.Windows.Automation.Provider.IGridProvider>.  
  
-   Bir sütun veya satır üst bilgisi bir tablo nesnesi içinde yer alabilir ya da bir tablo nesnesi ile ilişkili olan bir ayrı üstbilgi nesne.  
  
-   Sütun ve satır üst bilgileri, hem birincil üstbilgi, hem de destekleyen üst bilgileri içerebilir.  
  
> [!NOTE]
>  Bu kavram, yetkisiz değiştirmeye karşı korumalı hale bir [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] burada bir kullanıcının belirlediği bir "Ad" sütununu elektronik tablo. Bu sütun, artık iki üstbilgi sahiptir — kullanıcı ve uygulama tarafından atanan söz konusu sütun için alfasayısal belirtimi tarafından tanımlanan "Ad" üst bilgisi.  
  
-   Bkz: [UI Otomasyonu Grid denetim desenini uygulama](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) için ilgili kılavuz işlevselliği.  
  
 ![Karmaşık üstbilgi öğeleri içeren tablo. ](../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")  
Karmaşık sütun üst bilgilerini içeren bir tablo örneği  
  
 ![Tablo Belirsiz RowOrColumnMajor özelliğine sahip. ](../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")  
Belirsiz RowOrColumnMajor özelliğine sahip bir tablo örneği  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a>Gerekli üyeleri ITableProvider için  
 Aşağıdaki özellikleri ve yöntemleri ITableProvider arabirimi gerekli değildir.  
  
|Gerekli üyeleri|Üye türü|Notlar|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|Özellik|Hiçbiri|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|Yöntem|Hiçbiri|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|Yöntem|Hiçbiri|  
  
 Bu denetim düzeni, ilişkili olay vardır.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Özel Durumlar  
 Bu denetim düzeni ilişkili hiçbir özel durum vardır.  
  
## <a name="see-also"></a>Ayrıca bkz.
- [UI Otomasyonu Denetim Desenlerine Genel Bakış](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [UI Otomasyonu Sağlayıcıda Denetim Düzenleri Desteği](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [İstemciler İçin UI Otomasyonu Denetim Düzenleri](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [UI Otomasyonu TableItem Denetim Desenini Uygulama](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)
- [UI Otomasyonu Grid Denetim Desenini Uygulama](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)
- [UI Otomasyon Ağacına Genel Bakış](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [UI Otomasyonunda Önbelleğe Almayı Kullanma](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
