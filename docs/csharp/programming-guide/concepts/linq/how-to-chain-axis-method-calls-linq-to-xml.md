---
title: 'Nasıl yapılır: Zincir ekseni Yöntem çağrıları (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
ms.openlocfilehash: 573efb50dd889d1e10fc3a74bb5c7d9a8ac30eab
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594086"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-c"></a>Nasıl yapılır: Zincir ekseni Yöntem çağrıları (LINQ to XML) (C#)
Kodunuzda kullanacağınız ortak bir model, bir eksen yöntemi çağırmak ve sonra uzantı yöntemi eksenlerinden birini çağırmalıdır.  
  
 Adında `Elements` bir öğe koleksiyonu döndüren iki eksen vardır <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> : yöntemi ve <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> yöntemi. Ağaçta verilen bir derinlikte belirtilen bir adın tüm öğelerini bulmak için bu iki ekseni birleştirebilirsiniz.  
  
## <a name="example"></a>Örnek  
 Bu örnek, <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> tüm <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> öğelerinde tüm öğelerdeki `Name` tüm öğeleri `Address` `PurchaseOrder` bulmak için ve kullanır.  
  
 Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Birden çok satın alma siparişi (](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md)LINQ to XML).  
  
```csharp  
XElement purchaseOrders = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements("PurchaseOrder")  
        .Elements("Address")  
        .Elements("Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 Bu, `Elements` eksenin uygulamalarından biri <xref:System.Xml.Linq.XContainer>üzerinde <xref:System.Collections.Generic.IEnumerable%601> bir genişletme yöntemi olduğu için geçerlidir. <xref:System.Xml.Linq.XElement>' dan <xref:System.Xml.Linq.XContainer>türetilir, bu sayede yöntemine yapılan <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> çağrının <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> sonuçlarında yöntemi çağırabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Bazı durumlarda, üst öğelerinden oluşan veya aradaki bir işlem olduğunda, belirli bir öğe derinliğinde tüm öğeleri almak istersiniz. Örneğin, aşağıdaki belgede, öğesinin alt öğesi olan `ConfigParameter` tüm öğeleri `Customer` almak isteyebilirsiniz, ancak `ConfigParameter` `Root` öğesinin bir alt öğesidir.  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 Bunu yapmak için, aşağıdaki gibi, <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> eksenini kullanabilirsiniz:  
  
```csharp  
XElement root = XElement.Load("Irregular.xml");  
IEnumerable<XElement> configParameters =   
    root.Elements("Customer").Elements("Config").  
    Elements("ConfigParameter");  
foreach (XElement cp in configParameters)  
    Console.WriteLine(cp);  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir ad alanında bulunan XML için aynı tekniği gösterir. Daha fazla bilgi için bkz. [ad alanlarına genel bakış (C#LINQ to XML) ()](namespaces-overview-linq-to-xml.md).  
  
 Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Bir ad alanında](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md)birden fazla satın alma siparişi.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement purchaseOrders = XElement.Load("PurchaseOrdersInNamespace.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements(aw + "PurchaseOrder")  
        .Elements(aw + "Address")  
        .Elements(aw + "Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ to XML eksenleri (C#)](./linq-to-xml-axes.md)
