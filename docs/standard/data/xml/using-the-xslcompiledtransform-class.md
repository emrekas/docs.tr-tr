---
title: XslCompiledTransform sınıfını kullanma
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce9a06c14141bb658eb665e643d8da27e18dd94f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590385"
---
# <a name="using-the-xslcompiledtransform-class"></a>XslCompiledTransform sınıfını kullanma
<xref:System.Xml.Xsl.XslCompiledTransform> Microsoft .NET Framework XSLT işlemci bir sınıftır. Bu sınıf, stil sayfaları derlemek ve XSLT dönüşümleri yürütmek için kullanılır.  
  
> [!NOTE]
>  Ancak genel performansını <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı, daha iyi <xref:System.Xml.Xsl.XslTransform> sınıfı <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> yöntemi <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı daha gerçekleştirebileceğiniz daha yavaş <xref:System.Xml.Xsl.XslTransform.Load%2A> yöntemi <xref:System.Xml.Xsl.XslTransform> sınıfı ilk kez bir dönüştürme üzerinde çağrılır. XSLT dosyası, yüklenmeden önce derlenmesi gereken olmasıdır. Daha fazla bilgi için için şu blog yayınına bakın: [XslCompiledTransform XslTransform yavaş?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/)  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [XslCompiledTransform Sınıfına Girişler](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 Kullanılabilir XSLT giriş seçenekleri açıklar.  
  
 [XslCompiledTransform Sınıfındaki Çıkış Seçenekleri](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 XSLT çıkış seçeneklerini açıklar.  
  
 [XSLT İşleme Sırasında Dış Kaynakları Çözümleme](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 Kullanımını açıklar <xref:System.Xml.XmlResolver> dış kaynaklara çözmek için sınıf.  
  
 [XSLT Stil Sayfalarını Genişletme](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 XSLT uzantılarının nasıl desteklendiğini açıklar.  
  
|||  
|-|-|  
|[Kurtarılabilir XSLT Hataları](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|Bu davranışların tarafından nasıl işlendiğini açıklar ve isteğe bağlı davranışların tarafından World Wide Web Consortium (W3C) XSLT 1.0 öneri izin listeler <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı.|  
|[Nasıl yapılır: Düğüm parçasını dönüştürme](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|Düğüm parçasını dönüştürme işlemini açıklamaktadır.|  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [XslTransform Sınıfından Geçirme](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 Nasıl koddan geçirileceği anlatılmaktadır <xref:System.Xml.Xsl.XslTransform> sınıfı  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
