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
ms.openlocfilehash: beb351ac365694ac909b793bf19adb9fbb8c0274
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968135"
---
# <a name="inputs-to-the-xslcompiledtransform-class"></a>XslCompiledTransform Sınıfına Girişler
<xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> Yöntemi kabul üç tür kaynak belge için giriş: uygulayan bir nesne <xref:System.Xml.XPath.IXPathNavigable> arabirimi, bir <xref:System.Xml.XmlReader> kaynak belge ya da bir dize URI okuduğu nesne.  
  
> [!NOTE]
>  <xref:System.Xml.Xsl.XslCompiledTransform> Sınıfı boşluk varsayılan olarak korur. Dağıtabilirler budur [3.4 W3C XSLT 1.0 önerisi bölümünde](https://www.w3.org/TR/xslt.html#strip).  
  
## <a name="ixpathnavigable-interface"></a>IXPathNavigable arabirimi  
 <xref:System.Xml.XPath.IXPathNavigable> Arabirimi içinde uygulanan <xref:System.Xml.XmlNode> ve <xref:System.Xml.XPath.XPathDocument> sınıfları. Bu sınıfların bir bellek içi önbelleği XML verileri temsil eder.  
  
- <xref:System.Xml.XmlNode> Sınıfı W3C belge nesne modeli (DOM) üzerinde temel alır ve düzenleme özellikleri içerir.  
  
- <xref:System.Xml.XPath.XPathDocument> Sınıftır XPath veri modelini temel alan bir salt okunur veri deposu. <xref:System.Xml.XPath.XPathDocument> XSLT için önerilen sınıf işliyor. Karşılaştırıldığında daha hızlı performans sağlar <xref:System.Xml.XmlNode> sınıfı.  
  
> [!NOTE]
>  Dönüşümler belgenin bir bütün olarak uygular. Belge kök düğümü dışındaki bir düğümde geçirirseniz, diğer bir deyişle, bu dönüştürme süreci yüklenen belgedeki tüm düğümleri erişmesini engellemez. Düğüm parçasını dönüştürme için yalnızca düğüm parçasını içeren bir nesne oluşturun ve gerekir, nesneyi geçirmek <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> yöntemi. Daha fazla bilgi için [nasıl yapılır: Düğüm parçasını dönüştürme](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md).  
  
 Aşağıdaki örnekte <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> books.xml dosyasını transform.xsl stil sayfası kullanılarak books.html dosyasına dönüştürmek için yöntemi. Bu konu başlığında books.xml ve transform.xsl dosyaları bulunabilir: [Nasıl yapılır: Derleme kullanarak XSLT dönüşümü gerçekleştirme](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#1)]
 [!code-vb[XslCompiledTransform.Transform2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#1)]  
  
## <a name="xmlreader-object"></a>XmlReader nesnesi  
 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> Metodunun geçerli düğümünün <xref:System.Xml.XmlReader> aracılığıyla tüm alt öğeleri. Bu, bir belgenin bir bölümünü bağlam belgesi olarak kullanmanıza olanak sağlar. Sonra <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> yöntemi döndüğünde, <xref:System.Xml.XmlReader> bağlam belgenin sonunda sonraki düğümde konumlandırılır. Belgenin sonuna ulaşılırsa <xref:System.Xml.XmlReader> dosya sonunda (EOF) yerleştirilir.  
  
 Aşağıdaki örnekte <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> books.xml dosyasını transform.xsl stil sayfası kullanılarak books.html dosyasına dönüştürmek için yöntemi. Bu konu başlığında books.xml ve transform.xsl dosyaları bulunabilir: [Nasıl yapılır: Derleme kullanarak XSLT dönüşümü gerçekleştirme](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#2)]
 [!code-vb[XslCompiledTransform.Transform2#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#2)]  
  
## <a name="string-uri"></a>Dize URI  
 Kaynak belge URI, XSLT girişi belirtebilirsiniz. Bir <xref:System.Xml.XmlResolver> URI çözmek için kullanılır. Belirtebileceğiniz <xref:System.Xml.XmlResolver> aktararak kullanılacak <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> yöntemi. Varsa bir <xref:System.Xml.XmlResolver> belirtilmezse, <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> yöntemini kullanan bir varsayılan <xref:System.Xml.XmlUrlResolver> ile kimlik bilgileri yok.  
  
 Aşağıdaki örnekte <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> books.xml dosyasını transform.xsl stil sayfası kullanılarak books.html dosyasına dönüştürmek için yöntemi. Bu konu başlığında books.xml ve transform.xsl dosyaları bulunabilir: [Nasıl yapılır: Derleme kullanarak XSLT dönüşümü gerçekleştirme](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#3)]
 [!code-vb[XslCompiledTransform.Transform2#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#3)]  
  
 Daha fazla bilgi için [çözme dış sırasında XSLT işleme kaynaklarına](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [XSLT Dönüşümleri](../../../../docs/standard/data/xml/xslt-transformations.md)
