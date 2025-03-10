---
title: XslCompiledTransform Sınıfına Girişler
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 834049f1-ab41-449e-9f10-4a1d0701bc48
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 043c37a17375bf2dcdad9e4b429cfca7b96ef7cb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966967"
---
# <a name="inputs-to-the-xslcompiledtransform-class"></a>XslCompiledTransform Sınıfına Girişler
Yöntemi, kaynak belge için üç giriş türü kabul eder: <xref:System.Xml.XPath.IXPathNavigable> arabirimi uygulayan bir nesne, kaynak belgeyi okuyan <xref:System.Xml.XmlReader> bir nesne veya dize URI 'si. <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>  
  
> [!NOTE]
> <xref:System.Xml.Xsl.XslCompiledTransform> Sınıfı varsayılan olarak boşluğu korur. Bu, [W3C XSLT 1,0 önerisi 3,4 bölümüne](https://www.w3.org/TR/xslt.html#strip)göre belirlenir.  
  
## <a name="ixpathnavigable-interface"></a>Ixpathgezinebilir arabirimi  
 Arabirim, <xref:System.Xml.XmlNode> ve<xref:System.Xml.XPath.XPathDocument>sınıflarındauygulanır. <xref:System.Xml.XPath.IXPathNavigable> Bu sınıflar, XML verilerinin bellek içi önbelleğini temsil eder.  
  
- <xref:System.Xml.XmlNode> Sınıfı, W3C belge nesne modeli (DOM) temel alır ve Düzenle özelliklerini içerir.  
  
- <xref:System.Xml.XPath.XPathDocument> Sınıfı, XPath veri modelini temel alan bir salt okuma veri deposudur. <xref:System.Xml.XPath.XPathDocument>XSLT işleme için önerilen sınıftır. <xref:System.Xml.XmlNode> Sınıfla karşılaştırıldığında daha hızlı performans sağlar.  
  
> [!NOTE]
> Dönüşümler belgeye bir bütün olarak uygulanır. Diğer bir deyişle, belge kök düğümü dışında bir düğüm geçirirseniz, bu, dönüşüm işleminin yüklenen belgedeki tüm düğümlere erişmesini engellemez. Bir düğüm parçasını dönüştürmek için, yalnızca düğüm parçasını içeren bir nesne oluşturmanız ve bu nesneyi <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> yöntemine iletmeniz gerekir. Daha fazla bilgi için [nasıl yapılır: Düğüm parçasını](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)dönüştürme.  
  
 Aşağıdaki örnek,. xml <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> dosyasını, Transform. xsl stil sayfasını kullanarak Books. html dosyasına dönüştürmek için yöntemini kullanır. Books. xml ve Transform. XSL dosyaları bu konuda bulunabilir: [Nasıl yapılır: Bir derlemeyi](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md)kullanarak XSLT dönüştürmesi gerçekleştirin.  
  
 [!code-csharp[XslCompiledTransform.Transform2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#1)]
 [!code-vb[XslCompiledTransform.Transform2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#1)]  
  
## <a name="xmlreader-object"></a>XmlReader nesnesi  
 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> Yöntemi ,<xref:System.Xml.XmlReader> öğesinin geçerli düğümünden tüm alt öğeleri aracılığıyla yüklenir. Bu, bir belgenin bir kısmını bağlam belgesi olarak kullanmanıza olanak sağlar. <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> Yöntem<xref:System.Xml.XmlReader> çağrıldıktan sonra, bir sonraki düğümde bağlam belgesi sonundan sonra konumlandırılır. Belgenin sonuna ulaşılırsa <xref:System.Xml.XmlReader> , dosyanın sonuna (EOF) yerleştirilir.  
  
 Aşağıdaki örnek,. xml <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> dosyasını, Transform. xsl stil sayfasını kullanarak Books. html dosyasına dönüştürmek için yöntemini kullanır. Books. xml ve Transform. XSL dosyaları bu konuda bulunabilir: [Nasıl yapılır: Bir derlemeyi](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md)kullanarak XSLT dönüştürmesi gerçekleştirin.  
  
 [!code-csharp[XslCompiledTransform.Transform2#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#2)]
 [!code-vb[XslCompiledTransform.Transform2#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#2)]  
  
## <a name="string-uri"></a>Dize URI 'SI  
 Ayrıca, XSLT girdisi olarak kaynak belge URI 'sini de belirtebilirsiniz. <xref:System.Xml.XmlResolver> , URI 'yi çözümlemek için kullanılır. <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> Yöntemini yöntemine geçirerek belirtebilirsiniz <xref:System.Xml.XmlResolver> . Belirtilmemişse, yöntemi kimlik bilgileri olmayan bir varsayılan <xref:System.Xml.XmlUrlResolver> kullanır. <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> <xref:System.Xml.XmlResolver>  
  
 Aşağıdaki örnek,. xml <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> dosyasını, Transform. xsl stil sayfasını kullanarak Books. html dosyasına dönüştürmek için yöntemini kullanır. Books. xml ve Transform. XSL dosyaları bu konuda bulunabilir: [Nasıl yapılır: Bir derlemeyi](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md)kullanarak XSLT dönüştürmesi gerçekleştirin.  
  
 [!code-csharp[XslCompiledTransform.Transform2#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#3)]
 [!code-vb[XslCompiledTransform.Transform2#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#3)]  
  
 Daha fazla bilgi için bkz. [XSLT Işleme sırasında dış kaynakları çözümleme](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [XSLT Dönüşümleri](../../../../docs/standard/data/xml/xslt-transformations.md)
