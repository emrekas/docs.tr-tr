---
title: While Serializing3 boşluk koruma
ms.date: 07/20/2015
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
ms.openlocfilehash: 1b2a7f3ab2dcad200d6985e6b7bd91637d27dde8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741369"
---
# <a name="preserving-white-space-while-serializing"></a>Serileştirirken boşlukları koruma
Bu konuda, bir XML ağacı serileştirilirken boşluk denetlemek nasıl açıklanmaktadır.  
  
 Sık karşılaşılan bir senaryodur girintili XML oku, herhangi bir boşluk metin düğümleri (diğer bir deyişle, beyaz boşluk olmayan koruma) olmadan bir bellek içi XML ağacı oluşturmak, bazı XML işlemleri ve XML girintilemeli kaydedin sağlamaktır. Biçimlendirme ile XML serileştirme, yalnızca önemli boşluk XML ağacındaki korunur. Varsayılan davranışı budur [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Başka bir yaygın bir senaryo, okuma ve değiştirme kasıtlı olarak girintili zaten XML sağlamaktır. Bu girinti herhangi bir şekilde değiştirmek istemeyebilirsiniz. Bunu yapmak için [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], yükleme veya XML Ayrıştırma ve XML serileştirme seçildiğinde biçimlendirmeyi devre dışı olduğunda bölünemez boşluğu koruyacak.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>XML ağaçlarını serileştirme yöntemleri boşluk davranışını  
 Aşağıdaki yöntemleri <xref:System.Xml.Linq.XElement> ve <xref:System.Xml.Linq.XDocument> sınıfların serileştirmek bir XML ağacı. Bir dosyaya bir XML ağacı serileştirebilen bir <xref:System.IO.TextReader>, veya bir <xref:System.Xml.XmlReader>. `ToString` Yöntemi bir dizeye serileştirir.  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 Yöntem değil izlerseniz <xref:System.Xml.Linq.SaveOptions> bağımsız değişken olarak, ardından yöntemi biçimlendirir (Girinti) serileştirilmiş XML. Bu durumda, XML ağacı Önemsiz tüm bölünemez boşluğu göz ardı edilir.  
  
 Yöntem alırsanız <xref:System.Xml.Linq.SaveOptions> bağımsız değişken olarak, ardından yöntemi olmayan biçimlendirme belirtebilirsiniz (Girinti) serileştirilmiş XML. Bu durumda, XML ağacındaki tüm boşluk korunur.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Serileştirmek XML ağaçları (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
