---
title: Örnek OpenType Yazı Tipi Paketi
ms.date: 03/30/2017
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
ms.openlocfilehash: 0a2db2392c2380a397da42474a311449c8fdf9fb
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412168"
---
# <a name="sample-opentype-font-pack"></a>Örnek OpenType Yazı Tipi Paketi
Bu konu, örneğine genel bakış sağlar. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] ile dağıtılan yazı tipleri [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)]. Genişletilmiş örnek yazı tipi desteği [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] tarafından kullanılabilen özellikler [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] uygulamalar.  
  
  
<a name="overview"></a>   
## <a name="fonts-in-the-opentype-font-pack"></a>OpenType yazı tipi paketi yazı tipleri  
 [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] Örnek takımına [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] oluştururken kullanabileceğiniz yazı tipleri [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] uygulamalar. Örnek yazı tiplerinin lisans Ascender Corporation'ın altında sağlanır. Bu yazı tipleri yalnızca özelliklerinin bir alt kümesi tarafından tanımlanan toplam uygulama [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] biçimi. Aşağıdaki tabloda örnek adlarını listeler [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] yazı tipi.  
  
|**Ad**|**Dosya**|  
|--------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte kalın|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles açık|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero kalın|Pescab.ttf|  
  
 Aşağıdaki çizimde örnek [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] yazı aramak gibi.  
  
 ![Örnek yazı tipi paketi yazı tipi adları listesi](./media/sample-opentype-font-pack/font-names-sample-pack.gif)  
  
 Örnek yazı tiplerinin lisans Ascender Corporation'ın altında sağlanır. Ascender gelişmiş yazı tipi ürünlerinin bir sağlayıcıdır. Örnek yazı tiplerinin genişletilmiş veya özel sürümlerinin lisansı için bkz: [Ascender Corporation'ın Web sitesi](https://go.microsoft.com/fwlink/?LinkId=182627).  
  
> [!NOTE]
>  Bir geliştirici olarak içinde bir uygulamaya ekleme ya da aksi takdirde yeniden dağıtmak istediğiniz yazı tipi için gerekli lisans haklarına sahip olmak sizin sorumluluğunuzdur.  
  
<a name="installing_the_fonts"></a>   
## <a name="installing-the-fonts"></a>Yazı tipleri yükleme  
 Örnek yükleme seçeneğiniz [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] varsayılan yazı tipi [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] yazı tipleri dizini **\WINDOWS\Fonts**. Yazı tiplerini yüklemek için yazı tiplerini Denetim Masası'nı kullanın. Bu yazı tipleri bilgisayarınızda eklendiğinde varsayılan başvuran tüm uygulamalar için erişilebilir olduklarını [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] yazı tipi. Katlama-yazı tipi dosyaya tıklayarak, temsili bir karakter kümesi içinde birden çok yazı tipi boyutlarını görüntüleyebilirsiniz. Aşağıdaki ekran görüntüsünde Linds.ttf Lindsey yazı tipi dosyası gösterir.  
  
 ![Lindsey yazı tipi &#40;OpenType&#41;](./media/typographyinwpf-04.png "TypographyInWPF_04")  
Lindsey yazı tipi görüntüleme  
  
<a name="using_the_fonts"></a>   
## <a name="using-the-fonts"></a>Yazı tiplerini kullanma  
 Uygulamanızda yazı tipleri kullanabileceğiniz iki yolu vardır. Proje derleme içinde kaynak olarak gömülü içerik öğeleri olarak uygulamanıza yazı tipleri ekleyebilirsiniz. Alternatif olarak, yazı tiplerini uygulamanıza uygulamanın derleme dosyaları içinde gömülü proje kaynak öğeler olarak ekleyebilirsiniz. Daha fazla bilgi için [uygulamalarla yazı tiplerini paketleme](packaging-fonts-with-applications.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Documents.Typography>
- [OpenType Yazı Tipi Özellikleri](opentype-font-features.md)
- [Uygulamalarla Yazı Tiplerini Paketleme](packaging-fonts-with-applications.md)
