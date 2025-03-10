---
title: 'Nasıl yapılır: XslTransform Kodunuzu Geçirme'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 910beb2f-cfb3-4e8e-9936-f7e0c5f4064a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7022a0f55cd7994141148bc6b2faefb10bfea416
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966987"
---
# <a name="how-to-migrate-your-xsltransform-code"></a>Nasıl yapılır: XslTransform Kodunuzu Geçirme
Yeni XSLT sınıfları, mevcut sınıflara çok benzer olacak şekilde tasarlanmıştır. <xref:System.Xml.Xsl.XslCompiledTransform> Sınıfı ,<xref:System.Xml.Xsl.XslTransform> sınıfının yerini alır. Stil sayfaları <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> yöntemi kullanılarak derlenir. Dönüşümler <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> yöntemi kullanılarak yürütülür. Aşağıdaki yordamlarda ortak XSLT görevleri gösterilmektedir ve <xref:System.Xml.Xsl.XslTransform> sınıfı ile sınıf <xref:System.Xml.Xsl.XslCompiledTransform> karşılaştırması kullanılarak kod karşılaştırılır.  
  
### <a name="to-transform-a-file-and-output-to-a-uri"></a>Bir dosyayı ve çıktıyı bir URI 'ye dönüştürmek için  
  
- <xref:System.Xml.Xsl.XslTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#9](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#9)]
     [!code-vb[XML_Migration#9](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#9)]  
  
- <xref:System.Xml.Xsl.XslCompiledTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#10](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#10)]
     [!code-vb[XML_Migration#10](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#10)]  
  
### <a name="to-compile-a-style-sheet-and-use-a-resolver-with-default-credentials"></a>Bir stil sayfası derlemek ve varsayılan kimlik bilgileriyle çözümleyici kullanmak için  
  
- <xref:System.Xml.Xsl.XslTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#11)]
     [!code-vb[XML_Migration#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#11)]  
  
- <xref:System.Xml.Xsl.XslCompiledTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#12](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#12)]
     [!code-vb[XML_Migration#12](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#12)]  
  
### <a name="to-use-an-xslt-parameter"></a>XSLT parametresi kullanmak için  
  
- <xref:System.Xml.Xsl.XslTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#13](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#13)]
     [!code-vb[XML_Migration#13](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#13)]  
  
- <xref:System.Xml.Xsl.XslCompiledTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#14](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#14)]
     [!code-vb[XML_Migration#14](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#14)]  
  
### <a name="to-enable-xslt-scripting"></a>XSLT komut dosyalarını etkinleştirmek için  
  
- <xref:System.Xml.Xsl.XslTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#15](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#15)]
     [!code-vb[XML_Migration#15](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#15)]  
  
- <xref:System.Xml.Xsl.XslCompiledTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
     [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
### <a name="to-load-the-results-into-a-dom-object"></a>Sonuçları DOM nesnesine yüklemek için  
  
- <xref:System.Xml.Xsl.XslTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#19)]
     [!code-vb[XML_Migration#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#19)]  
  
- <xref:System.Xml.Xsl.XslCompiledTransform> Sınıfını kullanan kod.  
  
    > [!NOTE]
    > Sınıfın, XSLT dönüştürme sonuçlarını <xref:System.Xml.XmlReader> nesne olarak döndüren bir yöntemi yoktur. <xref:System.Xml.Xsl.XslCompiledTransform> Ancak, bir XML dosyasına çıktı verebilir ve XML dosyasını başka bir nesneye yükleyebilirsiniz.  
  
     [!code-csharp[XML_Migration#20](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#20)]
     [!code-vb[XML_Migration#20](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#20)]  
  
### <a name="to-stream-the-results-into-another-data-store"></a>Sonuçları başka bir veri deposuna akışa almak için  
  
- <xref:System.Xml.Xsl.XslTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#17](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#17)]
     [!code-vb[XML_Migration#17](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#17)]  
  
- <xref:System.Xml.Xsl.XslCompiledTransform> Sınıfını kullanan kod.  
  
     [!code-csharp[XML_Migration#18](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#18)]
     [!code-vb[XML_Migration#18](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#18)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [XslTransform Sınıfından Geçirme](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)
- [XslCompiledTransform Sınıfını Kullanma](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
