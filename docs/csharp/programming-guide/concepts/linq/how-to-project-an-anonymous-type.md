---
title: 'Nasıl yapılır: Anonim bir tür (C#) proje'
ms.date: 07/20/2015
ms.assetid: 5cb9be13-5ac4-4373-a034-b3520a5b2dec
ms.openlocfilehash: cd05c0ad7ab5a683b95e110cb0b1bb75b8a1dd2a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593024"
---
# <a name="how-to-project-an-anonymous-type-c"></a><span data-ttu-id="7060c-102">Nasıl yapılır: Anonim bir tür (C#) proje</span><span class="sxs-lookup"><span data-stu-id="7060c-102">How to: Project an Anonymous Type (C#)</span></span>
<span data-ttu-id="7060c-103">Bazı durumlarda, bu türü yalnızca kısa bir süre kullanacağınızı bildiğiniz halde yeni bir türe bir sorgu için proje yapmak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7060c-103">In some cases you might want to project a query to a new type, even though you know you will only use this type for a short while.</span></span> <span data-ttu-id="7060c-104">Projeksiyon içinde kullanmak için yeni bir tür oluşturmaya yönelik çok fazla iş vardır.</span><span class="sxs-lookup"><span data-stu-id="7060c-104">It is a lot of extra work to create a new type just to use in the projection.</span></span> <span data-ttu-id="7060c-105">Bu örnekte daha verimli bir yaklaşım, bir anonim türe projem değildir.</span><span class="sxs-lookup"><span data-stu-id="7060c-105">A more efficient approach in this case is to project to an anonymous type.</span></span> <span data-ttu-id="7060c-106">Anonim türler sınıfı tanımlamanızı sağlar, sonra sınıfa bir ad vermeden bu sınıfın bir nesnesini bildirip başlatabilir.</span><span class="sxs-lookup"><span data-stu-id="7060c-106">Anonymous types allow you to define a class, then declare and initialize an object of that class, without giving the class a name.</span></span>  
  
 <span data-ttu-id="7060c-107">Anonim türler, bir C# *tanımlama*grubunun matematik kavramının uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="7060c-107">Anonymous types are the C# implementation of the mathematical concept of a *tuple*.</span></span> <span data-ttu-id="7060c-108">Matematiksel terim tanımlama grubu, tek, Çift, Üçlü, dörtlü, quintuple, n-Tuple dizisinden kaynakdır.</span><span class="sxs-lookup"><span data-stu-id="7060c-108">The mathematical term tuple originated from the sequence single, double, triple, quadruple, quintuple, n-tuple.</span></span> <span data-ttu-id="7060c-109">Belirli bir türün her biri, sınırlı bir nesne dizisine başvurur.</span><span class="sxs-lookup"><span data-stu-id="7060c-109">It refers to a finite sequence of objects, each of a specific type.</span></span> <span data-ttu-id="7060c-110">Bazen buna ad/değer çiftleri listesi denir.</span><span class="sxs-lookup"><span data-stu-id="7060c-110">Sometimes this is called a list of name/value pairs.</span></span> <span data-ttu-id="7060c-111">Örneğin, [örnek XML dosyasındaki bir adresin içeriği: Tipik satın alma siparişi (LINQ to XML](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) ) XML belgesi şu şekilde ifade edilebilir:</span><span class="sxs-lookup"><span data-stu-id="7060c-111">For example, the contents of an address in the [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) XML document could be expressed as follows:</span></span>  
  
```  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 <span data-ttu-id="7060c-112">Anonim bir türün bir örneğini oluşturduğunuzda, bunu bir sıra n grubu oluşturarak düşünmek kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="7060c-112">When you create an instance of an anonymous type, it is convenient to think of it as creating a tuple of order n.</span></span> <span data-ttu-id="7060c-113">`select` Yan tümcesinde bir tanımlama grubu oluşturan bir sorgu yazarsanız sorgu, kayıt düzeni `IEnumerable` döndürür.</span><span class="sxs-lookup"><span data-stu-id="7060c-113">If you write a query that creates a tuple in the `select` clause, the query returns an `IEnumerable` of the tuple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7060c-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="7060c-114">Example</span></span>  
 <span data-ttu-id="7060c-115">Bu örnekte `select` yan tümce, anonim bir tür.</span><span class="sxs-lookup"><span data-stu-id="7060c-115">In this example, the `select` clause projects an anonymous type.</span></span> <span data-ttu-id="7060c-116">Örnek daha sonra `IEnumerable` nesneyi `var` oluşturmak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="7060c-116">The example then uses `var` to create the `IEnumerable` object.</span></span> <span data-ttu-id="7060c-117">`foreach` Döngü içinde, yineleme değişkeni sorgu ifadesinde oluşturulan anonim türün bir örneği olur.</span><span class="sxs-lookup"><span data-stu-id="7060c-117">Within the `foreach` loop, the iteration variable becomes an instance of the anonymous type created in the query expression.</span></span>  
  
 <span data-ttu-id="7060c-118">Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Müşteriler ve siparişler (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="7060c-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
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
  
 <span data-ttu-id="7060c-119">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="7060c-119">This code produces the following output:</span></span>  
  
```  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  