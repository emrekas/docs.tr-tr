---
title: LINQ to XML güvenliği (C#)
ms.date: 07/20/2015
ms.assetid: ef2c0dc9-ecf9-4c17-b24e-144184ab725f
ms.openlocfilehash: c9045025b5af11fb84d4b6bb1598e8cf6ff229a0
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591747"
---
# <a name="linq-to-xml-security-c"></a>LINQ to XML güvenliği (C#)
Bu konuda LINQ to XML ilişkili güvenlik sorunları açıklanmaktadır. Ayrıca, güvenlik açısından etkilenme riskini azaltmak için bazı kılavuzluk sağlar.  
  
## <a name="linq-to-xml-security-overview"></a>LINQ to XML güvenliğe genel bakış  
 LINQ to XML, katı güvenlik gereksinimlerine sahip sunucu tarafı uygulamalardan daha fazla programlama kolaylığı için tasarlanmıştır. Çoğu XML senaryosu, bir sunucuya yüklenen güvenilmeyen XML belgelerini işlemek yerine, güvenilen XML belgelerinin işlenmesini içerir. LINQ to XML, bu senaryolar için iyileştirilmiştir.  
  
 Bilinmeyen kaynaklardan güvenilmeyen verileri işlemek istiyorsanız, Microsoft, bilinen XML hizmet reddi (DOS) saldırılarını filtrelemek için <xref:System.Xml.XmlReader> yapılandırılmış bir sınıfının örneğini kullanmanızı önerir.  
  
 Hizmet reddi saldırılarını azaltmak için <xref:System.Xml.XmlReader> bir yapılandırdıysanız, bu okuyucuyu bir LINQ to XML ağacı doldurmak ve LINQ to XML programcı üretkenlik geliştirmelerinden faydalanmaya devam etmek için kullanabilirsiniz. Birçok azaltma tekniği, güvenlik sorununu hafifletmek üzere yapılandırılmış okuyucular oluşturmayı ve sonra yapılandırılmış okuyucu aracılığıyla bir XML ağacını örneklamayı içerir.  
  
 Belgeler boyut, derinlik, öğe adı boyutu ve daha fazlası için sınırsız olduğundan, XML, hizmet reddi saldırılarına karşı doğası gereği açıktır. XML işlemek için kullandığınız bileşenden bağımsız olarak, aşırı kaynak kullanıyorsa uygulama etki alanını geri dönüştürmeye her zaman hazırlıklı olmalısınız.  
  
## <a name="mitigation-of-xml-xsd-xpath-and-xslt-attacks"></a>XML, XSD, XPath ve XSLT saldırıları üzerinde risk azaltma  
 LINQ to XML, ve <xref:System.Xml.XmlWriter>üzerine <xref:System.Xml.XmlReader> kurulmuştur. LINQ to XML, <xref:System.Xml.Schema?displayProperty=nameWithType> ve <xref:System.Xml.XPath?displayProperty=nameWithType> ad alanlarındaki genişletme yöntemleri aracılığıyla XSD ve XPath 'i destekler. <xref:System.Xml.XmlReader>, Vesınıflarını<xref:System.Xml.XmlWriter> LINQ to XML ile birlikte kullanarak, XML ağaçlarını dönüştürmek için XSLT 'yi çağırabilirsiniz. <xref:System.Xml.XPath.XPathNavigator>  
  
 Daha az güvenli bir ortamda çalışıyorsanız, XML ile ilişkili birçok güvenlik sorunu ve, <xref:System.Xml?displayProperty=nameWithType>, ve <xref:System.Xml.Xsl?displayProperty=nameWithType>içinde <xref:System.Xml.Schema?displayProperty=nameWithType> <xref:System.Xml.XPath?displayProperty=nameWithType>sınıfların kullanımı vardır. Bu sorunlar şunları içerir, ancak bunlarla sınırlı değildir:  
  
- XSD, XPath ve XSLT, çok fazla zamanı veya belleği kullanan işlemleri belirtebileceğiniz dize tabanlı dillerdir. Dizelerin kötü amaçlı olmayan kaynaklardan XSD, XPath veya XSLT dizeleri alan ve bu dizeleri değerlendirme olasılığını izlemek ve azaltmak için, aşırı sisteme yol açacağından kaynak tüketimi.  
  
- XSD şemaları (satır içi şemalar dahil), doğal olarak hizmet reddi saldırılarına karşı savunmasız kalır; Güvenilmeyen kaynaklardan şemaları kabul etmemelisiniz.  
  
- XSD ve XSLT diğer dosyalara başvurular içerebilir ve bu tür başvurular, bölgeler arası ve etki alanları arası saldırılara yol açabilir.  
  
- DTD 'lerde dış varlıklar, bölgeler arası ve etki alanları arası saldırılara yol açabilir.  
  
- DTD 'Ler hizmet reddi saldırılarına karşı savunmasızdır.  
  
- Daha fazla derin XML belgesi, hizmet reddi sorunları oluşturabilir; XML belgelerinin derinliğini kısıtlamak isteyebilirsiniz.  
  
- Güvenilmeyen derlemelerden,, ve <xref:System.Xml.NameTable> <xref:System.Xml.XmlResolver> nesneleri gibi destekleyici bileşenleri <xref:System.Xml.XmlNamespaceManager>kabul etmez.  
  
- Büyük belge saldırılarını azaltmak için öbeklerdeki verileri okuyun.  
  
- XSLT stil sayfalarındaki betik blokları çok sayıda saldırı sunabilir.  
  
- Dinamik XPath ifadelerini oluşturmadan önce dikkatle doğrulayın.  
  
## <a name="linq-to-xml-security-issues"></a>LINQ to XML güvenlik sorunları  
 Bu konudaki güvenlik sorunları belirli bir sırada sunulmaz. Tüm sorunlar önemlidir ve uygun şekilde ele alınmalıdır.  
  
 Başarılı bir ayrıcalık yükselmesi saldırısı, kendi ortamı üzerinde kötü amaçlı bir derlemeye daha fazla denetim sağlar. Başarılı bir ayrıcalık yükseltme saldırısı, verilerin açığa çıkmasına, hizmet reddine ve daha fazlasına neden olabilir.  
  
 Uygulamalar, verileri görme yetkisine sahip olmayan kullanıcılara verileri açıklamamalıdır.  
  
 Hizmet reddi saldırıları, XML ayrıştırıcısının veya LINQ to XML aşırı miktarda belleği veya CPU süresini kullanmasına neden olur. Hizmet reddi saldırıları, ayrıcalık saldırılarının yükseltilmesinin veya veri saldırılarının açıklanmasının daha az önemli olduğu kabul edilir. Ancak, bir sunucunun güvenilmeyen kaynaklardan XML belgelerini işlemesi gereken bir senaryoda bu durumlar önemlidir.  
  
### <a name="exceptions-and-error-messages-might-reveal-data"></a>Özel durumlar ve hata Iletileri verileri açığa çıkarmayabilir  
 Bir hatanın açıklaması, dönüştürülen veriler, dosya adları veya uygulama ayrıntıları gibi verileri açığa çıkarmayabilir. Hata iletileri güvenilmeyen çağıranlara gösterilmemelidir. Kendi özel hata mesajlarınız ile tüm hataları ve rapor hatalarını yakalamalı.  
  
### <a name="do-not-call-codeaccesspermissionsassert-in-an-event-handler"></a>CodeAccessPermissions. bir olay Işleyicisinde onay çağrısı yapın  
 Bir derlemenin daha az veya daha fazla izni olabilir. Daha fazla izne sahip bir derleme, bilgisayar ve ortamları üzerinde daha fazla denetime sahiptir.  
  
 Daha fazla izinlere sahip bir derlemedeki kod bir olay <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=nameWithType> işleyicide çağrılamışsa ve sonra XML ağacı kısıtlanmış izinlere sahip kötü amaçlı bir derlemeye geçirilirse, kötü amaçlı derleme bir olayın oluşturulmasına neden olabilir. Olay derlemede daha fazla izinle kod çalıştırdığı için kötü amaçlı derleme yükseltilmiş ayrıcalıklarla çalışır.  
  
 Microsoft bir olay işleyicisinde hiçbir şekilde <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=nameWithType> çağrı yapmanızı önerir.  
  
### <a name="dtds-are-not-secure"></a>DTD 'Ler güvenli değil  
 DTD 'lerde varlıklar, doğal olarak güvenli değildir. Bir DTD içeren kötü amaçlı bir XML belgesi, ayrıştırıcısının tüm belleği ve CPU süresini kullanmasına neden olur ve bu da hizmet reddi saldırısına neden olur. Bu nedenle, LINQ to XML öğesinde DTD işleme varsayılan olarak kapalıdır. Güvenilmeyen kaynaklardan DTD 'Leri kabul etmemelisiniz.  
  
 Güvenilmeyen kaynaklardan DTD 'Leri kabul etmenin bir örneği, Web kullanıcılarının bir DTD 'ye ve DTD dosyasına başvuran bir XML dosyasını karşıya yüklemesine izin veren bir Web uygulamasıdır. Dosyanın doğrulanması sırasında, kötü amaçlı bir DTD sunucunuz üzerinde bir hizmet reddi saldırısı yürütebilir. Güvenilmeyen kaynaklardan DTD 'Lerin kabul edilmesi için başka bir örnek de, anonim FTP erişimine izin veren bir ağ paylaşımındaki bir DTD 'ye başvurulmalıdır.  
  
### <a name="avoid-excessive-buffer-allocation"></a>Aşırı arabellek ayırmayı önleyin  
 Uygulama geliştiricileri, son derece büyük veri kaynaklarının kaynak tükenmesi ve hizmet reddi saldırılarına yol açabileceğini bilmelidir.  
  
 Kötü amaçlı bir Kullanıcı çok büyük bir XML belgesi gönderdiğinde veya karşıya yüklediğinde, LINQ to XML aşırı sistem kaynağı kullanmasına neden olabilir. Bu, bir hizmet reddi saldırısı oluşturabilir. Bunu engellemek için <xref:System.Xml.XmlReaderSettings.MaxCharactersInDocument%2A?displayProperty=nameWithType> özelliği ayarlayabilir ve daha sonra yükleyebilen belgenin boyutuyla sınırlı bir okuyucu oluşturabilirsiniz. Ardından, XML ağacı oluşturmak için okuyucuyu kullanın.  
  
 Örneğin, güvenilir olmayan bir kaynaktan gelen XML belgelerinin beklenen en büyük boyutunun 50K bayttan daha az olacağını biliyorsanız, 100.000 olarak ayarlayın <xref:System.Xml.XmlReaderSettings.MaxCharactersInDocument%2A?displayProperty=nameWithType> . Bu, XML belgelerinin işlenmesini içermez ve aynı zamanda, belgelerin karşıya yüklenmesi, büyük miktarlarda bellek tüketebileceği hizmet reddi tehditleri ortadan kaldırılır.  
  
### <a name="avoid-excess-entity-expansion"></a>Aşırı varlık genişletmesinin önleyin  
 DTD kullanırken bilinen hizmet reddi saldırılarına bir, aşırı varlık genişlemesine neden olan bir belgedir. Bunu engellemek için <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities%2A?displayProperty=nameWithType> özelliğini ayarlayabilir ve daha sonra varlık genişletmesinden kaynaklanan karakter sayısında sınırlı bir okuyucu oluşturabilirsiniz. Ardından, XML ağacı oluşturmak için okuyucuyu kullanın.  
  
### <a name="limit-the-depth-of-the-xml-hierarchy"></a>XML hiyerarşisinin derinliğini sınırlayın  
 Olası bir hizmet reddi saldırısı, çok sayıda hiyerarşi içeren bir belge gönderildiğinde gönderilir. Bunu engellemek için, öğelerin derinliğini sayan <xref:System.Xml.XmlReader> kendi sınıfınıza bir sardırabilirsiniz. Derinlik önceden belirlenmiş makul bir düzeyi aşarsa, kötü amaçlı belgeyi işlemeyi sonlandırabilirsiniz.  
  
### <a name="protect-against-untrusted-xmlreader-or-xmlwriter-implementations"></a>Güvenilmeyen XmlReader veya XmlWriter uygulamalarına karşı koruma  
 Yöneticiler dışarıdan sağlanan <xref:System.Xml.XmlReader> veya <xref:System.Xml.XmlWriter> uygulamaların, güçlü adlara sahip olduğunu ve makine yapılandırmasında kayıtlı olduğunu doğrulamalıdır. Bu, kötü amaçlı kodun bir okuyucu veya yazıcının yüklenmesini önler.  
  
### <a name="periodically-free-objects-that-reference-xname"></a>XName 'e başvuran düzenli olarak ücretsiz nesneler  
 Uygulama programcılarının belirli türlerde saldırılara karşı korunması için, uygulama etki alanındaki bir <xref:System.Xml.Linq.XName> nesneye düzenli olarak başvuran tüm nesneleri boşaltmalıdır.  
  
### <a name="protect-against-random-xml-names"></a>Rastgele XML adlarına karşı koruma  
 Güvenilmeyen kaynaklardan veri alan uygulamalar, rastgele XML adları ve ad <xref:System.Xml.XmlReader> alanları olasılığını incelemek için özel koda Sarmalanan bir kullanmayı düşünmelidir. Bu tür rastgele XML adları ve ad alanları algılanırsa, uygulama kötü amaçlı belgenin işlenmesini sonlandırabilir.  
  
 Belirli bir ad alanındaki (ad alanı olmayan adlar dahil) ad sayısını makul bir sınıra sınırlamak isteyebilirsiniz.  
  
### <a name="annotations-are-accessible-by-software-components-that-share-a-linq-to-xml-tree"></a>Ek açıklamalar LINQ to XML ağacı paylaşan yazılım bileşenleri tarafından erişilebilir  
 LINQ to XML, farklı uygulama bileşenlerinin XML ağaçları olarak bileşenler arasında geçirilen XML verilerini yükleme, doğrulama, sorgulama, dönüştürme, güncelleştirme ve kaydetme işlem hatlarını oluşturmak için kullanılabilir. Bu, XML metnine nesne yükleme ve serileştirilmesinin yükü yalnızca işlem hattının sonunda yapıldığından performansı iyileştirmenize yardımcı olabilir. Ancak geliştiriciler, bir bileşen tarafından oluşturulan tüm ek açıklamaların ve olay işleyicilerinin diğer bileşenler tarafından erişilebilir olduğunu bilmelidir. Bu, bileşenlerin farklı düzeylerde güven düzeyine sahip olması halinde bir dizi güvenlik açığı oluşturabilir. Daha az güvenilir bileşenlere güvenli işlem hatları oluşturmak için, verileri güvenilmeyen bir bileşene geçirmeden önce LINQ to XML nesneleri XML metnine serileştirmelidir.  
  
 Bazı güvenlik, ortak dil çalışma zamanı (CLR) tarafından sağlanır. Örneğin, özel bir sınıf içermeyen bir bileşen, bu sınıf tarafından anahtarlanan ek açıklamaların erişimine erişemez. Ancak, ek açıklamalar bunları okuyadesteklemeyen bileşenler tarafından silinebilir. Bu, bir izinsiz saldırı olarak kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Programlama Kılavuzu (LINQ to XML) (C#)](./programming-guide-linq-to-xml.md)
