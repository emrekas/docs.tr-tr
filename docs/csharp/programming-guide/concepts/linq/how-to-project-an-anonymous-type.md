---
title: 'Nasıl yapılır: Anonim bir tür (C#) proje'
ms.date: 07/20/2015
ms.assetid: 5cb9be13-5ac4-4373-a034-b3520a5b2dec
ms.openlocfilehash: 3ed14ae6e7bc4b84ae9dc416b76e37443b831c73
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253517"
---
# <a name="how-to-project-an-anonymous-type-c"></a>Nasıl yapılır: Anonim bir tür (C#) proje
Bazı durumlarda, bu türü yalnızca kısa bir süre kullanacağınızı bildiğiniz halde yeni bir türe bir sorgu için proje yapmak isteyebilirsiniz. Projeksiyon içinde kullanmak için yeni bir tür oluşturmaya yönelik çok fazla iş vardır. Bu örnekte daha verimli bir yaklaşım, bir anonim türe projem değildir. Anonim türler sınıfı tanımlamanızı sağlar, sonra sınıfa bir ad vermeden bu sınıfın bir nesnesini bildirip başlatabilir.  
  
 Anonim türler, bir C# *tanımlama*grubunun matematik kavramının uygulamasıdır. Matematiksel terim tanımlama grubu, tek, Çift, Üçlü, dörtlü, quintuple, n-Tuple dizisinden kaynakdır. Belirli bir türün her biri, sınırlı bir nesne dizisine başvurur. Bazen buna ad/değer çiftleri listesi denir. Örneğin, [örnek XML dosyasındaki bir adresin içeriği: Tipik satın alma siparişi (LINQ to XML](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) ) XML belgesi şu şekilde ifade edilebilir:  
  
```text  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 Anonim bir türün bir örneğini oluşturduğunuzda, bunu bir sıra n grubu oluşturarak düşünmek kullanışlıdır. `select` Yan tümcesinde bir tanımlama grubu oluşturan bir sorgu yazarsanız sorgu, kayıt düzeni `IEnumerable` döndürür.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `select` yan tümce, anonim bir tür. Örnek daha sonra `IEnumerable` nesneyi `var` oluşturmak için kullanır. `foreach` Döngü içinde, yineleme değişkeni sorgu ifadesinde oluşturulan anonim türün bir örneği olur.  
  
 Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Müşteriler ve siparişler (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
XElement custOrd = XElement.Load("CustomersOrders.xml");  
var custList =  
    from el in custOrd.Element("Customers").Elements("Customer")  
    select new {  
        CustomerID = (string)el.Attribute("CustomerID"),  
        CompanyName = (string)el.Element("CompanyName"),  
        ContactName = (string)el.Element("ContactName")  
    };  
foreach (var cust in custList)  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName);  
```  
  
 Bu kod aşağıdaki çıktıyı üretir:  
  
```output  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  