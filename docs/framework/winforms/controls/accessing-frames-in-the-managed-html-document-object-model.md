---
title: Yönetilen HTML Belgesi Nesne Modelindeki Çerçevelere Erişme
ms.date: 03/30/2017
helpviewer_keywords:
- HTML [Windows Forms], dOM
- managed HTML DOM
- HTML [Windows Forms], managed
- HTML DOM [Windows Forms], managed
- frames [Windows Forms], accessing
- DOM [Windows Forms], accessing frames in managed HTML
ms.assetid: cdeeaa22-0be4-4bbf-9a75-4ddc79199f8d
ms.openlocfilehash: 9b2719ca000ab86b9ca40f9e78af46cbf598d16e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337636"
---
# <a name="accessing-frames-in-the-managed-html-document-object-model"></a>Yönetilen HTML Belgesi Nesne Modelindeki Çerçevelere Erişme
Bazı HTML belgeleri tanesi oluşur *çerçeveler*, ya da kendi ayrı HTML belgeleri içerebileceği windows. Çerçeveleri kullanarak diğer çerçeveler sürekli içeriklerini değiştirme sırasında bir veya daha fazla parça sayfanın bir gezinti çubuğu gibi statik kalır HTML sayfaları oluşturmak kolaylaştırır.  
  
 HTML yazarlar çerçeveler iki yoldan biriyle oluşturabilirsiniz:  
  
-   Kullanarak `FRAMESET` ve `FRAME` sabit windows oluşturma etiketler.  
  
 -veya-  
  
-   Kullanarak `IFRAME` etiketini, çalışma zamanında konumlandırılabilir kayan bir pencere oluşturur.  
  
1. Çerçeve HTML belgeleri içerdiğinden, bunlar belge nesne modeli (DOM) pencere öğeleri ve çerçeve öğeleri gösterilir.  
  
2. Eriştiğinizde bir `FRAME` veya `IFRAME` çerçeveler koleksiyonunu kullanarak etiket <xref:System.Windows.Forms.HtmlWindow>, çerçeveye karşılık gelen pencere öğesinin alıyor. Bu, tüm geçerli URL, belge ve boyutu gibi çerçeve dinamik özelliklerini temsil eder.  
  
3. Eriştiğinizde bir `FRAME` veya `IFRAME` kullanarak etiket <xref:System.Windows.Forms.HtmlWindow.WindowFrameElement%2A> özelliği <xref:System.Windows.Forms.HtmlWindow>, <xref:System.Windows.Forms.HtmlElement.Children%2A> koleksiyonu veya yöntemler gibi <xref:System.Windows.Forms.HtmlElementCollection.GetElementsByName%2A> veya <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>, çerçeve öğesi alıyor. Bu, orijinal HTML dosyasında belirtilen URL çerçevenin statik özelliklerini temsil eder.  
  
## <a name="frames-and-security"></a>Çerçeve ve güvenlik  
 Çerçeve erişimi karmaşık yönetilen HTML DOM olarak bilinen bir güvenlik önlemi uyguladığını olgu tarafından *çerçeveler betik güvenlik*. Bir belge içeriyorsa bir `FRAMESET` iki veya daha fazlasıyla `FRAME`s farklı etki alanlarında bu `FRAME`s birbiriyle etkileşim olamaz. Diğer bir deyişle, bir `FRAME` Web sitenizin içeriğini görüntüler bilgilerinde erişemiyor bir `FRAME` gibi bir üçüncü taraf site sunan `http://www.adatum.com/`. Bu güvenlik düzeyinde uygulanır <xref:System.Windows.Forms.HtmlWindow> sınıfı. Hakkında genel bilgiler elde edebilirsiniz bir `FRAME` URL'sini, ancak gibi başka bir Web sitesi barındırma erişemiyor olacaktır, <xref:System.Windows.Forms.HtmlWindow.Document%2A> veya, barındırma konumunu ve boyutunu değiştirme `FRAME` veya `IFRAME`.  
  
 Bu kural kullanarak açın ve windows için de geçerlidir. <xref:System.Windows.Forms.HtmlWindow.Open%2A> ve <xref:System.Windows.Forms.HtmlWindow.OpenNew%2A> yöntemleri. Açtığınız pencere barındırılan sayfasından farklı bir etki alanında ise <xref:System.Windows.Forms.WebBrowser> denetimi, kullanılamaz bu pencereyi taşımak ya da içeriğini inceleyin. Kullanıyorsanız bu sınırlamalar da uygulanır <xref:System.Windows.Forms.WebBrowser> denetimini Windows Forms tabanlı uygulamanızı dağıtmak için kullanılan Web sitesinden farklı bir Web sitesini görüntülemek için. Kullanırsanız [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] uygulamanızı bir Web sitesinden ve yüklemek için dağıtım teknolojisini <xref:System.Windows.Forms.WebBrowser> Web sitesi B görüntülemek için access Web sitesinin B'nin veri mümkün olmayacaktır.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [\<Çerçeve > öğesi](https://developer.mozilla.org/docs/Web/HTML/Element/frame)
- [Yönetilen HTML Belgesi Nesne Modelini Kullanma](using-the-managed-html-document-object-model.md)
