---
title: 'Nasıl yapılır: Bir öğenin yüzeysel değerini alma (C#)'
ms.date: 07/20/2015
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
ms.openlocfilehash: 593fe1c22664f1e4e8322cb8816e58f4721c5bf8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672850"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a>Nasıl yapılır: Bir öğenin yüzeysel değerini alma (C#)
Bu konuda, bir öğenin yüzeysel değerini alma gösterilmektedir. Basit yalnızca belirli öğenin değeri tek bir dize olarak birleştirilmiş tüm alt öğe değerlerini içeren ayrıntılı değer aksine değerdir.  
  
 Ya da bir çevrim kullanarak bir öğe değeri aldığınızda veya <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> özelliği, derin değeri alın. Yüzeysel değerini almak için kullanabileceğiniz `ShallowValue` genişletme yöntemi, aşağıdaki örnekte gösterildiği gibi. Yüzeysel değerini alma içeriklerine göre öğeleri seçmek istediğinizde yararlıdır.  
  
 Aşağıdaki örnek, bir öğenin yüzeysel değerini alır. bir genişletme yöntemi bildirir. Ardından, hesaplanan değeri içeren tüm öğeleri listelemek için genişletme yöntemi bir sorguda kullanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki metin dosyası Report.xml, bu örnekte kaynağıdır.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ to XML eksenleri (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
