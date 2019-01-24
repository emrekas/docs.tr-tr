---
title: 'Örnek XML dosyası: Tipik satın alma siparişi (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 65321b9c-1239-45e4-af40-eb86cedf7abd
ms.openlocfilehash: cd3478c6f8cf246d7c3f9df34c597d4d265881b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729320"
---
# <a name="sample-xml-file-typical-purchase-order-linq-to-xml"></a><span data-ttu-id="1576d-102">Örnek XML dosyası: Tipik satın alma siparişi (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1576d-102">Sample XML File: Typical Purchase Order (LINQ to XML)</span></span>
<span data-ttu-id="1576d-103">Aşağıdaki XML dosyasını çeşitli örneklerde kullanılan [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] belgeleri.</span><span class="sxs-lookup"><span data-stu-id="1576d-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="1576d-104">Tipik satın alma siparişi dosyasıdır.</span><span class="sxs-lookup"><span data-stu-id="1576d-104">This file is a typical purchase order.</span></span>  
  
## <a name="purchaseorderxml"></a><span data-ttu-id="1576d-105">PurchaseOrder.xml</span><span class="sxs-lookup"><span data-stu-id="1576d-105">PurchaseOrder.xml</span></span>  
  
```xml  
<?xml version="1.0"?>  
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
```  
  
## <a name="see-also"></a><span data-ttu-id="1576d-106">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1576d-106">See also</span></span>
- [<span data-ttu-id="1576d-107">Örnek XML Belgeleri (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1576d-107">Sample XML Documents (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
