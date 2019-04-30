---
title: Kurtarılabilir XSLT Hataları
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 484929b0-fefb-4629-87ee-ebdde70ff1f8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 215fb807aa27b8a544351d26fd0c9500c76b6ead
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698778"
---
# <a name="recoverable-xslt-errors"></a>Kurtarılabilir XSLT Hataları
W3C XSLT Dönüşümleri (XSLT) sürüm 1.0 öneri uygulama sağlayıcısı bir durumu işlemek nasıl karar verebilir alanları içerir. Bu alanlar isteğe bağlı bir davranış olarak değerlendirilir. Örneğin, bu içeriği, örnekleme, bir hata olduğunu Bölüm 7.3 oluşturma işleme yönergeleri, XSLT 1.0 öneri eyaletler `xsl:processing-instruction` metin düğümleri dışındaki düğümlerde oluşturur. İşlemci hatadan kurtarmayı karar verirse, bazı sorunlar için öneri ne karar gösterir XSLT 1.0 yapılmalıdır. 7.3 bölümde verilen sorun için uygulama bu hatadan düğümleri ve içeriklerini yoksayarak kurtarabilirsiniz W3C diyor.  
  
## <a name="discretionary-behaviors"></a>İsteğe bağlı davranışların uygulanması  
 Aşağıdaki tabloda her XSLT 1.0 öneri ve bu davranışların tarafından nasıl işlendiğini tarafından izin verilen isteğe bağlı davranışların listeler <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı.  
  
- Kurtarma gösterir <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı bu hatadan kurtarır. <xref:System.Xml.Xsl.XsltArgumentList.XsltMessageEncountered?displayProperty=nameWithType> Olay, XSLT işlemci tüm olayları bildirmek için kullanılabilir.  
  
- Bu koşul için bir özel durum, hata olduğunu gösterir.  
  
- Bölüm başvuruları bulunabilir [W3C XSLT Dönüşümleri (XSLT) sürüm 1.0 öneri](https://www.w3.org/TR/xslt) ve [W3C XSLT Dönüşümleri (XSLT) sürüm 1.0 belirtimi Errata](https://www.w3.org/1999/11/REC-xslt-19991116-errata/).  
  
|XSLT koşulu|Bölüm|XslCompiledTransform behavior|  
|--------------------|-------------|-----------------------------------|  
|Bir metin düğümü her ikisi de eşleşen `xsl:strip-space` ve `xsl:preserve-space`.|3.4|Kurtarma|  
|Kaynak düğüm, birden fazla şablon kuralı eşleşir.|5.5|Kurtarma|  
|Bir ad alanı URI için tüm aynı alma önceliğe sahip birden çok ad alanı URI, bir diğer ad olarak bildirilir.|7.1.1|Kurtarma|  
|`name` Özniteliğini `xsl:attribute` ve `xsl:element` oluşturulan bir öznitelik değeri bir QName değil.|7.1.2, 7.1.3|Hata *|  
|İki öznitelik aynı alma kümeleriyle genişletilmiş ada sahip bir öznitelik ortak ve daha yüksek önem derecesi ile aynı ada sahip genel öznitelik içeren diğer öznitelik ödenmez.|7.1.4|Kurtarma|  
|Alt öğe eklendikten sonra bir öznitelik bir öğe ekleme.|7.1.3|Hata *|  
|Bir öznitelik adı 'xmlns' ile oluşturma|7.1.3|Hata *|  
|Öznitelik bir öğe değil bir düğüme ekleniyor.|7.1.3|Hata *|  
|Metin düğümleri dışındaki düğümlerde içeriği örnek oluşturma sırasında oluşturma `xsl:attribute` özniteliği.|7.1.3|Hata *|  
|`name` Özniteliği bir `xsl:processing-instruction` NCName hem de bir işleme yönergesi hedefi vermez.|7.3|Hata *|  
|İçeriği, örnekleme `xsl:processing-instruction` metin düğümleri dışındaki düğümlerde oluşturur.|7.3|Hata *|  
|İçeriği, örnekleme sonucunu `xsl:processing-instruction` dizesini içeren "? >"|7.3|Kurtarma|  
|İçeriği, örnekleme sonucunu `xsl:processing-instruction` dizesini içeren "--" veya ile biter "-".|7.4|Kurtarma|  
|İçeriği, örnekleme sonucunu `xsl:comment` metin düğümleri dışındaki düğümlerde oluşturur.|7.4|Hata *|  
|Bir değişkeni bağlama öğenin şablonda bir öznitelik düğümü veya ad alanı düğümü döndürür.|11.2|Hata *|  
|Belge işleve geçirilen URI'deki kaynağı alınırken bir hata yoktur.|12.1|Hata|  
|Bir parça tanımlayıcı belge işlevindeki URI başvuru içeren ve parça tanımlayıcı işlenirken bir hata yoktur.|12.1|Recover*|  
|Aynı adı taşıyan ancak cdata bölümü öğelerinde adlı değil, farklı değerler ile birden çok öznitelik `xsl:output` ile aynı öncelik içeri aktarın.|16|Kurtarma|  
|İşlemci içinde kodlamasını desteklemediğini `xsl:output` kodlama özniteliği.|16.1|Kurtarma|  
|Bir metin düğümü sonucu ağacında dışında bir şey için kullanılan bir metin düğümü için çıkış kaçış devre dışı bırakılıyor.|16.4|Recover*|  
|Sonuç ağacı parçası etkin çıkış kaçış ile bir metin düğümü içeriyorsa, bir sayı veya dize bir sonuç ağacı parçası dönüştürülüyor.|16.4|Recover*|  
|Çıkış kaçış XSLT işlemci için çıkış kullandığını kodlama temsil edilemeyen bir karakter için devre dışı bırakıldı.|16.4|Recover*|  
|Alt öğeler veya öznitelikleri eklendikten sonra onu eklendikten sonra bir ad alanı düğümü için bir öğe ekleme.|errata 25|Hata *|  
|`value` Özniteliği bir `xsl:number` sonsuz veya daha az 0,5 NAN olup|errata 24|Kurtarma|  
|Düğüm kümesi belge işleve ikinci bağımsız değişken boş ve göreli URI referansı.|errata 14|Kurtarma|  
  
 <sup>*</sup> Bu daha farklı, davranıştır <xref:System.Xml.Xsl.XslTransform> sınıfı. Daha fazla bilgi için [uygulama, isteğe bağlı davranışların XslTransform sınıfında](../../../../docs/standard/data/xml/implementation-of-discretionary-behaviors-in-the-xsltransform-class.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [XSLT Dönüşümleri](../../../../docs/standard/data/xml/xslt-transformations.md)
