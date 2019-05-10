---
title: (Visual Basic) XML işlevsel dönüşümü
ms.date: 07/20/2015
ms.assetid: fdbe5b91-f457-4b4e-a11b-def4bdd77bab
ms.openlocfilehash: 147f36241fd2b8cec03adfac3273d2155af82922
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64618266"
---
# <a name="functional-transformation-of-xml-visual-basic"></a>(Visual Basic) XML işlevsel dönüşümü
Bu konu, XML belgelerinin sınırlandırması saf işlevsel dönüşüm yaklaşımını ele alır ve yordam yaklaşımından ile karşılaştırır.  
  
## <a name="modifying-an-xml-document"></a>Bir XML belgesi değiştirme  
 Bir XML programcı için en yaygın görevlerden biri XML bir şekilden diğerine dönüştürüyor. Bir XML belgesi şeklini aşağıdakileri içeren belge yapısı şöyledir:  
  
- Belgeye göre ifade hiyerarşisi.  
  
- Öğe ve öznitelik adları.  
  
- Öznitelikleri ve öğeleri veri türleri.  
  
 Genel olarak, XML bir şekle dönüştürme en etkili, saf işlev dönüşümün yaklaşımdır. Bu yaklaşımda, birincil Programcı görev tüm XML belgesi (veya bir veya daha fazla kesinlikle tanımlanmış düğümleri) uygulanan bir dönüştürme oluşturmaktır. İşlevsel dönüşümü gerçekleşir tartışmaya kolay (programcı yaklaşım ile ilgili bilgi sahibi olduktan sonra) kodu için en Bakımı yapılabilir kodu üretir ve genellikle daha alternatif yaklaşımlar compact olur.  
  
### <a name="xml-functional-transformational-technologies"></a>XML işlevsel Dönüşümsel teknolojiler  
 Microsoft XML belgeleri kullanmak için iki işlevsel dönüşüm teknolojileri sunar: XSLT ve LINQ to XML. XSLT içerisinde desteklendiği <xref:System.Xml.Xsl> ad alanı yönetilen ve yerel MSXML COM uygulama. XSLT XML belgeleri yönetmek için güçlü bir teknoloji olsa da, bir özel etki alanı, XSLT dili ve destekleyici API'lerini uzmanlığı gerektirir.  
  
 LINQ to XML, C# veya Visual Basic kodu içinde bir ifadesel ve güçlü şekilde kod saf işlevsel dönüşümlere için gerekli araçları sağlar. Örneğin, birçok LINQ örnek XML belgeleri için saf işlevsel bir yaklaşım kullanın. Ayrıca, [Öğreticisi: (Visual Basic) WordprocessingML belgesindeki içeriği düzenleme](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) öğreticide kullanıyoruz LINQ to XML işlevsel bir yaklaşım bir Microsoft Word belgesi bilgilerini işlemek için.  
  
 Bir daha kapsamlı bir karşılaştırması LINQ to XML için diğer Microsoft XML teknolojileriyle bkz [LINQ to XML ile. Diğer XML teknolojileri](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).  
  
 Kaynak belge düzensiz bir yapısı varsa XSLT belge odaklı dönüştürmeleri için önerilen araçtır. Ancak LINQ to XML belge odaklı dönüşümleri gerçekleştirebilirsiniz. Daha fazla bilgi için [nasıl yapılır: LINQ to XML ağaçlarını XSLT stilindeki (Visual Basic) dönüştürmek için ek açıklamalarını kullanma](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Saf işlevsel dönüşümlere (Visual Basic) giriş](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [LINQ to XML ile Diğer XML Teknolojileri Karşılaştırması](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)
