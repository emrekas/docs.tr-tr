---
title: XML belgesinde ad alanlarını yönetme
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 682643fc-b848-4e42-8c0d-50deeaeb5f2a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9375386360c94f959f638e1227cb847b783b994
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676178"
---
# <a name="managing-namespaces-in-an-xml-document"></a>XML belgesinde ad alanlarını yönetme
XML ad alanları XML belgesinde öğe ve öznitelik adları, özel ve önceden tanımlanmış bir URI'leri ile ilişkilendirin. Bu ilişkileri oluşturmak için URI ad alanı ön eklerini tanımlayın ve bu ön ekler öğe ve öznitelik adları XML verisindeki nitelemek için kullanın. Ad alanları, öğe ve öznitelik adı çakışmalarını önlemek ve öğeleri ve öznitelikleri aynı ada sahip işlenmesini ve farklı şekilde doğrulanmış etkinleştirin.  
  
<a name="declare"></a>   
## <a name="declaring-namespaces"></a>Ad alanlarını bildirme  
 Bir öğe üzerinde bir ad alanı bildirmek için kullanmanız `xmlns:` özniteliği:  
  
 `xmlns:<name>=<"uri">`  
  
 Burada `<name>` ad alanı öneki ve `<"uri">` ad alanını tanımlayan URI. Önek bildirdikten sonra öğeleri ve özniteliklerinin bir XML belgesi sınıflandırmak ve ad alanı URI ile ilişkilendirmek için kullanabilirsiniz. Ad alanı öneki belge kullanılmakta olduğundan uzunluğu kısa olmalıdır.  
  
 Bu örnek iki tanımlar `BOOK` öğeleri. Ön eke göre ilk öğeyi nitelenmiş `mybook`, ve ikinci öğe ön eke göre nitelenmiş `bb`. Her ön eki farklı ad alanı URI ile ilişkilendirilir:  
  
```xml  
<mybook:BOOK xmlns:mybook="http://www.contoso.com/books.dtd">  
<bb:BOOK xmlns:bb="urn:blueyonderairlines">  
```  
  
 Bir öğenin belirli bir ad alanının bir parçası olduğunu belirtmek için ad alanı öneki ekleyin. Örneğin, bir `Author` öğenin ait olduğu `mybook` ad alanı, bildirilen olarak `<mybook:Author>`.  
  
<a name="scope"></a>   
## <a name="declaration-scope"></a>Bildirim kapsamı  
 Bir ad alanı içinde bildirilen öğe sonuna kadar bildirim noktasında etkilidir. Bu örnekte ad alanı tanımlı `BOOK` öğesi öğeler için geçerli değildir `BOOK` öğesi gibi `Publisher` öğesi:  
  
```xml  
<Author>Joe Smith</Author>  
<BOOK xmlns:book="http://www.contoso.com">  
    <title>My Wonderful Day</title>  
      <price>$3.95</price>  
</BOOK>  
<Publisher>  
    <Name>MSPress</Name>  
</Publisher>  
```  
  
 Bir ad alanı, kullanılabilir, ancak XML belgenin üst kısmında görünmesini yok önce bildirilmelidir.  
  
 Bir XML belgesinde birden çok ad alanını kullandığınızda, bir ad alanı Temizleyicisi görünümlü bir belge oluşturmak için varsayılan ad alanı olarak tanımlayabilirsiniz. Varsayılan ad alanı, kök öğesi bildirilmiş ve belgedeki tüm nitelenmemiş öğeleri için geçerlidir. Varsayılan ad alanlarını öznitelikler için yalnızca öğeler için geçerlidir.  
  
 Varsayılan ad alanı kullanılacak önek ve virgül gelen öğede bildirimi atla:  
  
```xml  
<BOOK xmlns="http://www.contoso.com/books.dtd">  
```  
  
## <a name="managing-namespaces"></a>Ad alanlarını yönetme  
 <xref:System.Xml.XmlNamespaceManager> Sınıf ad alanı URI koleksiyonunu depolar ve bunların ön ekleri ve sağlar, konum ekleyin ve bu koleksiyondan ad alanları. Belirli bağlamlarda bu sınıfı daha iyi XML işlem performansı için gereklidir. Örneğin, <xref:System.Xml.Xsl.XsltContext> sınıfının kullandığı <xref:System.Xml.XmlNamespaceManager> XPath desteği.  
  
 Ad alanı Yöneticisi'ni ad alanlarında herhangi doğrulaması gerçekleştirmez, ancak önek ve ad alanları zaten doğrulandı ve uygun varsayar [W3C ad alanları](https://www.w3.org/TR/REC-xml-names/) belirtimi.  
  
> [!NOTE]
>  [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) kullanmayan <xref:System.Xml.XmlNamespaceManager> ad alanlarını yönetmek için. Bkz: [XML ad alanları ile çalışma](https://msdn.microsoft.com/library/e3003209-3234-45be-a832-47feb7927430) LINQ to XML kullanarak ad alanlarını yönetme hakkında bilgi için LINQ belgelerinde.  
  
 Bazı görevlerin ile gerçekleştirebileceğiniz yönetim ve arama <xref:System.Xml.XmlNamespaceManager> sınıfı. Daha fazla bilgi ve örnekler için her bir metot veya Özellik Başvurusu sayfasına bağlantıları izleyin.  
  
|Bitiş|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|--------|---------|  
|Bir ad alanı Ekle|<xref:System.Xml.XmlNamespaceManager.AddNamespace%2A> Yöntemi|  
|Bir ad alanını Kaldır|<xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A> Yöntemi|  
|Varsayılan ad alanı URI bulma|<xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A> Özelliği|  
|İçin bir ad alanı öneki URI bulma|<xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A> Yöntemi|  
|Ad alanı için URI öneki bulun|<xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A> Yöntemi|  
|Geçerli düğüm ad alanlarının listesini alın|<xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A> Yöntemi|  
|Bir ad alanı kapsamı|<xref:System.Xml.XmlNamespaceManager.PushScope%2A> ve <xref:System.Xml.XmlNamespaceManager.PopScope%2A> yöntemleri|  
|Bir önek geçerli kapsamda tanımlı olup olmadığını denetleyin|<xref:System.Xml.XmlNamespaceManager.HasNamespace%2A> Yöntemi|  
|Ön ekleri ve URI'leri ara için kullanılan ad tablosu Al|<xref:System.Xml.XmlNamespaceManager.NameTable%2A> Özelliği|  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Xml.XmlNamespaceManager>
- [XML Belgeleri ve Verileri](../../../../docs/standard/data/xml/index.md)
