---
title: 'Örnek XML dosyası: Birden fazla satın alma siparişi (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 08e148ff-4070-4bb4-b089-306f4a9a7641
ms.openlocfilehash: 676592b0bd77a10fa8bb5fa01bf3b3a06af1ca46
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623488"
---
# <a name="sample-xml-file-multiple-purchase-orders-linq-to-xml"></a>Örnek XML dosyası: Birden fazla satın alma siparişi (LINQ to XML)
Aşağıdaki XML dosyasını çeşitli örneklerde kullanılan [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] belgeleri. Bu dosya, çeşitli satın alma siparişleri içerir.  
  
## <a name="purchaseordersxml"></a>PurchaseOrders.xml  
  
```xml  
<?xml version="1.0"?>  
<PurchaseOrders>  
  <PurchaseOrder PurchaseOrderNumber="99503" OrderDate="1999-10-20">  
    <Address Type="Shipping">  
      <Name>Ellen Adams</Name>  
      <Street>123 Maple Street</Street>  
      <City>Mill Valley</City>  
      <State>CA</State>  
      <Zip>10999</Zip>  
      <Country>USA</Country>  
    </Address>  
    <Address Type="Billing">  
      <Name>Tai Yee</Name>  
      <Street>8 Oak Avenue</Street>  
      <City>Old Town</City>  
      <State>PA</State>  
      <Zip>95819</Zip>  
      <Country>USA</Country>  
    </Address>  
    <DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
    <Items>  
      <Item PartNumber="872-AA">  
        <ProductName>Lawnmower</ProductName>  
        <Quantity>1</Quantity>  
        <USPrice>148.95</USPrice>  
        <Comment>Confirm this is electric</Comment>  
      </Item>  
      <Item PartNumber="926-AA">  
        <ProductName>Baby Monitor</ProductName>  
        <Quantity>2</Quantity>  
        <USPrice>39.98</USPrice>  
        <ShipDate>1999-05-21</ShipDate>  
      </Item>  
    </Items>  
  </PurchaseOrder>  
  <PurchaseOrder PurchaseOrderNumber="99505" OrderDate="1999-10-22">  
    <Address Type="Shipping">  
      <Name>Cristian Osorio</Name>  
      <Street>456 Main Street</Street>  
      <City>Buffalo</City>  
      <State>NY</State>  
      <Zip>98112</Zip>  
      <Country>USA</Country>  
    </Address>  
    <Address Type="Billing">  
      <Name>Cristian Osorio</Name>  
      <Street>456 Main Street</Street>  
      <City>Buffalo</City>  
      <State>NY</State>  
      <Zip>98112</Zip>  
      <Country>USA</Country>  
    </Address>  
    <DeliveryNotes>Please notify me before shipping.</DeliveryNotes>  
    <Items>  
      <Item PartNumber="456-NM">  
        <ProductName>Power Supply</ProductName>  
        <Quantity>1</Quantity>  
        <USPrice>45.99</USPrice>  
      </Item>  
    </Items>  
  </PurchaseOrder>  
  <PurchaseOrder PurchaseOrderNumber="99504" OrderDate="1999-10-22">  
    <Address Type="Shipping">  
      <Name>Jessica Arnold</Name>  
      <Street>4055 Madison Ave</Street>  
      <City>Seattle</City>  
      <State>WA</State>  
      <Zip>98112</Zip>  
      <Country>USA</Country>  
    </Address>  
    <Address Type="Billing">  
      <Name>Jessica Arnold</Name>  
      <Street>4055 Madison Ave</Street>  
      <City>Buffalo</City>  
      <State>NY</State>  
      <Zip>98112</Zip>  
      <Country>USA</Country>  
    </Address>  
    <Items>  
      <Item PartNumber="898-AZ">  
        <ProductName>Computer Keyboard</ProductName>  
        <Quantity>1</Quantity>  
        <USPrice>29.99</USPrice>  
      </Item>  
      <Item PartNumber="898-AM">  
        <ProductName>Wireless Mouse</ProductName>  
        <Quantity>1</Quantity>  
        <USPrice>14.99</USPrice>  
      </Item>  
    </Items>  
  </PurchaseOrder>  
</PurchaseOrders>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Örnek XML Belgeleri (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
