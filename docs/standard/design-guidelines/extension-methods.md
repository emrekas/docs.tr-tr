---
title: Genişletme Yöntemleri
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: KrzysztofCwalina
ms.openlocfilehash: bd5f67c3bd766625e7c22b3ca9986cfbca8854bf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026425"
---
# <a name="extension-methods"></a>Genişletme Yöntemleri
Genişletme yöntemleri örnek yöntem çağrısı sözdizimi kullanılarak çağrılabilir için statik yöntemler sağlayan bir dil özelliğidir. Bu yöntemler üzerinde çalışılacak yöntemidir örneği temsil eden en az bir parametre almalıdır.  
  
 Bu tür genişletme yöntemlerini sınıfı "sponsor" sınıf olarak adlandırılır ve statik olarak bildirilmelidir. Genişletme yöntemleri kullanmak için bir sponsor sınıfı tanımlayan ad alanı içe aktarmanız gerekir.  
  
 **X AVOID** frivolously genişletme yöntemleri, özellikle yok kendi türlerinde tanımlama.  
  
 Kaynak kodu türü sahipseniz, normal örneğinde yöntemleri kullanmayı düşünün. Size ait olmayan ve bir yöntem eklemek istediğiniz, çok dikkatli olun. Serbest ayraç kullanımı genişletme yöntemleri, bu yöntemlere sahip olacak şekilde tasarlanmamıştır türlerinin API'leri yığılmak olasılığına sahiptir.  
  
 **✓ CONSIDER** genişletme yöntemleri aşağıdaki senaryolardan birini kullanarak:  
  
- Yardımcısı sağlamak açısından temel arabirimi işlevselliği söyledi, ilgili arabirim, her bir uygulama için işlevselliği yazılabilir. Somut uygulamalarını aksi arabirimlerine atama yapılamaz olmasıdır. Örneğin, `LINQ to Objects` işleçlerini genişletme yöntemleri tüm uygulanır <xref:System.Collections.Generic.IEnumerable%601> türleri. Bu nedenle, tüm `IEnumerable<>` LINQ özellikli otomatik olarak uygulamasıdır.  
  
- Bazı tür bağımlı, ancak böyle bir bağımlılık bir örnek yöntemi zaman gösterebileceği bağımlılık Yönetimi kurallarını bölün. Örneğin, bir bağımlılık <xref:System.String> için <xref:System.Uri?displayProperty=nameWithType> olduğu gibi olmayabilir ve bu nedenle `String.ToUri()` döndüren örnek yöntem `System.Uri` bağımlılık yönetimi açısından yanlış bir tasarım olur. Bir statik genişletme yöntemi `Uri.ToUri(this string str)` döndüren `System.Uri` bir çok daha iyi bir tasarım olur.  
  
 **X AVOID** üzerinde genişletme yöntemleri tanımlama <xref:System.Object?displayProperty=nameWithType>.  
  
 VB kullanıcılar üzerinde genişletme yöntemi sözdizimi kullanarak nesne başvuruları gibi yöntemleri çağırmak mümkün olmayacaktır. VB nesne geç üzerindeki tüm yöntem çağrıları zorlar gibi bir başvuru bildirmek VB, bağlı olduğundan, bu yöntemleri çağırma desteklemez (gerçek üye adlı çalışma zamanında belirlenir), derleme zamanında (erken bağlamaları genişletme yöntemleri için belirlenen sırada bağlı).  
  
 Kılavuz aynı bağlama davranışı var olduğu ya da genişletme yöntemleri değil desteklendiği durumlarda diğer diller için geçerli olduğunu unutmayın.  
  
 **X DO NOT** veya bağımlılık yönetimi yöntemleri arabirimlerine ekleme için olmadığı sürece, genişletilmiş türü aynı ad alanına genişletme yöntemleri uygulamak.  
  
 **X AVOID** farklı ad alanlarında bulunuyorsa bile aynı imzayla iki veya daha fazla genişletme yöntemleri tanımlama.  
  
 **✓ CONSIDER** türü bir arabirim ise ve çoğu veya tamamı durumlarda kullanılacak genişletme yöntemleri istediyseniz genişletilmiş türü olarak aynı ad alanında genişletme yöntemleri tanımlama.  
  
 **X DO NOT** normalde diğer özelliklerle ilişkili ad alanlarında bir özellik uygulama uzantı yöntemleri tanımlar. Bunun yerine, bunları ait oldukları özellik ilişkili ad alanı tanımlayın.  
  
 **X AVOID** genel bir ad alanları adlandırma ayrılmış genişletme yöntemleri (örneğin, "uzantılarla"). Açıklayıcı bir ad kullanın (örneğin, "yönlendirme") bunun yerine.  
  
 *Kısımları © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*  
  
 *İzni Pearson eğitim, Inc. tarafından yeniden yazdırılmaları [çerçeve tasarım yönergeleri: Kuralları, deyimlerini ve yeniden kullanılabilir .NET kitaplıkları, sürüm 2 için desenler](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams, 22 Eki 2008 Addison Wesley Professional ile Microsoft Windows geliştirme serisi bir parçası olarak yayımlandı.*  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Üye Tasarımı Yönergeleri](../../../docs/standard/design-guidelines/member.md)
- [Çerçeve Tasarım Yönergeleri](../../../docs/standard/design-guidelines/index.md)
