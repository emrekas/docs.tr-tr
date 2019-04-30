---
title: LINQ to XML olayları (C#)
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: f7ce6ed99f7279d1dc774314cdc2dde345b6a84d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701693"
---
# <a name="linq-to-xml-events-c"></a>LINQ to XML olayları (C#)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] olayları bir XML ağacı değiştirildiğinde bildirim almak etkinleştirin.  
  
 Herhangi bir örneği için olayları ekleyebilirsiniz <xref:System.Xml.Linq.XObject>. Olay işleyicisi, ardından, değişiklikler için olayları alacaksınız <xref:System.Xml.Linq.XObject> ve tüm alt öğeleri. Örneğin, ağacının kökü için bir olay işleyicisi ekleme ve ağaç yapılan tüm değişiklikler bu olay işleyicisinden tanıtıcı.  
  
 Örnekler için [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] olayları görmek <xref:System.Xml.Linq.XObject.Changing> ve <xref:System.Xml.Linq.XObject.Changed>.  
  
## <a name="types-and-events"></a>Türleri ve olaylar  
 Olaylar ile çalışırken aşağıdaki türlerini kullanır:  
  
|Tür|Açıklama|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|Olay türü için bir olay oluştuğunda belirtir bir <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|İçin veri sağlayan <xref:System.Xml.Linq.XObject.Changing> ve <xref:System.Xml.Linq.XObject.Changed> olayları.|  
  
 Bir XML ağacı değiştirdiğinizde, aşağıdaki olaylar oluşturulur:  
  
|Olay|Açıklama|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|Hemen önce gerçekleşir <xref:System.Xml.Linq.XObject> veya alt öğelerinden birini gittiğini değiştirin.|  
|<xref:System.Xml.Linq.XObject.Changed>|Gerçekleşir, bir <xref:System.Xml.Linq.XObject> değiştirildi veya alt öğelerinden birini değiştirilmiştir.|  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Olayları toplama bazı bilgiler XML ağacındaki bulundurmak istediğinizde yararlıdır. Örneğin, toplam fatura satır öğelerini bir fatura toplamı korumak isteyebilirsiniz. Bu örnekte, toplam karmaşık öğesinin altındaki tüm alt öğeleri tutmak için olayları kullanır. `Items`.  
  
### <a name="code"></a>Kod  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Total", "0"),  
    new XElement("Items")  
);  
XElement total = root.Element("Total");  
XElement items = root.Element("Items");  
items.Changed += (object sender, XObjectChangeEventArgs cea) =>  
{  
    switch (cea.ObjectChange)  
    {  
        case XObjectChange.Add:  
            if (sender is XElement)  
                total.Value = ((int)total + (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total + (int)((XText)sender).Parent).ToString();  
            break;  
        case XObjectChange.Remove:  
            if (sender is XElement)  
                total.Value = ((int)total - (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total - Int32.Parse(((XText)sender).Value)).ToString();  
            break;  
    }  
    Console.WriteLine("Changed {0} {1}",  
      sender.GetType().ToString(), cea.ObjectChange.ToString());  
};  
items.SetElementValue("Item1", 25);  
items.SetElementValue("Item2", 50);  
items.SetElementValue("Item2", 75);  
items.SetElementValue("Item3", 133);  
items.SetElementValue("Item1", null);  
items.SetElementValue("Item4", 100);  
Console.WriteLine("Total:{0}", (int)total);  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a>Açıklamalar  
 Bu kod aşağıdaki çıktıyı üretir:  
  
```  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Gelişmiş LINQ to XML programlama (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
