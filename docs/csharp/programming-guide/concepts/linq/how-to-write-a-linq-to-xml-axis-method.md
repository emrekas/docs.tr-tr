---
title: 'Nasıl yapılır: LINQ to XML eksen yöntemi yazma (C#)'
ms.date: 07/20/2015
ms.assetid: 50aef06b-1d22-4718-a18a-21237e26d7c1
ms.openlocfilehash: 6e777e615d21dd43317f0813461a3f1d8a506c90
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484668"
---
# <a name="how-to-write-a-linq-to-xml-axis-method-c"></a>Nasıl yapılır: LINQ to XML eksen yöntemi yazma (C#)
XML ağacından koleksiyonları almak için kendi eksen yöntemler yazabilirsiniz. Bunu yapmak için en iyi yollarından biri öğe ve özniteliklerin koleksiyonunu döndüren bir uzantı metodu yazma sağlamaktır. Öğeler veya öznitelikleri, uygulamanızın gereksinimlerine göre belirli alt kümelerine döndürülecek genişletme yönteminizin yazabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iki uzantı yöntemi kullanır. İlk genişletme yöntemi `GetXPath`, üzerinde çalıştığı <xref:System.Xml.Linq.XObject>ve değerlendirildiğinde döndüren bir XPath ifadesi bir düğüm veya öznitelik döndürür. İkinci bir genişletme yöntemi `Find`, üzerinde çalıştığı <xref:System.Xml.Linq.XElement>. Bir koleksiyonunu döndürür <xref:System.Xml.Linq.XAttribute> nesneleri ve <xref:System.Xml.Linq.XElement> bazı içeren nesneleri belirtilen metin.  
  
 Bu örnek aşağıdaki XML belgesi kullanır: [Örnek XML dosyası: Birden fazla satın alma siparişi (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```csharp  
public static class MyExtensions  
{  
    private static string GetQName(XElement xe)  
    {  
        string prefix = xe.GetPrefixOfNamespace(xe.Name.Namespace);  
        if (xe.Name.Namespace == XNamespace.None || prefix == null)  
            return xe.Name.LocalName.ToString();  
        else  
            return prefix + ":" + xe.Name.LocalName.ToString();  
    }  
  
    private static string GetQName(XAttribute xa)  
    {  
        string prefix =  
            xa.Parent.GetPrefixOfNamespace(xa.Name.Namespace);  
        if (xa.Name.Namespace == XNamespace.None || prefix == null)  
            return xa.Name.ToString();  
        else  
            return prefix + ":" + xa.Name.LocalName;  
    }  
  
    private static string NameWithPredicate(XElement el)  
    {  
        if (el.Parent != null && el.Parent.Elements(el.Name).Count() != 1)  
            return GetQName(el) + "[" +   
                (el.ElementsBeforeSelf(el.Name).Count() + 1) + "]";  
        else  
            return GetQName(el);  
    }  
  
    public static string StrCat<T>(this IEnumerable<T> source,  
        string separator)  
    {  
        return source.Aggregate(new StringBuilder(),  
                   (sb, i) => sb  
                       .Append(i.ToString())  
                       .Append(separator),  
                   s => s.ToString());  
    }  
  
    public static string GetXPath(this XObject xobj)  
    {  
        if (xobj.Parent == null)  
        {  
            XDocument doc = xobj as XDocument;  
            if (doc != null)  
                return ".";  
            XElement el = xobj as XElement;  
            if (el != null)  
                return "/" + NameWithPredicate(el);  
            // the XPath data model does not include white space text nodes  
            // that are children of a document, so this method returns null.  
            XText xt = xobj as XText;  
            if (xt != null)  
                return null;  
            XComment com = xobj as XComment;  
            if (com != null)  
                return  
                    "/" +  
                    (  
                        com  
                        .Document  
                        .Nodes()  
                        .OfType<XComment>()  
                        .Count() != 1 ?  
                        "comment()[" +  
                        (com  
                        .NodesBeforeSelf()  
                        .OfType<XComment>()  
                        .Count() + 1) +  
                        "]" :  
                        "comment()"  
                    );  
            XProcessingInstruction pi = xobj as XProcessingInstruction;  
            if (pi != null)  
                return  
                    "/" +  
                    (  
                        pi.Document.Nodes()  
                        .OfType<XProcessingInstruction>()  
                        .Count() != 1 ?  
                        "processing-instruction()[" +  
                        (pi  
                        .NodesBeforeSelf()  
                        .OfType<XProcessingInstruction>()  
                        .Count() + 1) +  
                        "]" :  
                        "processing-instruction()"  
                    );  
            return null;  
        }  
        else  
        {  
            XElement el = xobj as XElement;  
            if (el != null)  
            {  
                return  
                    "/" +  
                    el  
                    .Ancestors()  
                    .InDocumentOrder()  
                    .Select(e => NameWithPredicate(e))  
                    .StrCat("/") +  
                    NameWithPredicate(el);  
            }  
            XAttribute at = xobj as XAttribute;  
            if (at != null)  
                return  
                    "/" +  
                    at  
                    .Parent  
                    .AncestorsAndSelf()  
                    .InDocumentOrder()  
                    .Select(e => NameWithPredicate(e))  
                    .StrCat("/") +  
                    "@" + GetQName(at);  
            XComment com = xobj as XComment;  
            if (com != null)  
                return  
                    "/" +  
                    com  
                    .Parent  
                    .AncestorsAndSelf()  
                    .InDocumentOrder()  
                    .Select(e => NameWithPredicate(e))  
                    .StrCat("/") +  
                    (  
                        com  
                        .Parent  
                        .Nodes()  
                        .OfType<XComment>()  
                        .Count() != 1 ?  
                        "comment()[" +  
                        (com  
                        .NodesBeforeSelf()  
                        .OfType<XComment>()  
                        .Count() + 1) + "]" :  
                        "comment()"  
                    );  
            XCData cd = xobj as XCData;  
            if (cd != null)  
                return  
                    "/" +  
                    cd  
                    .Parent  
                    .AncestorsAndSelf()  
                    .InDocumentOrder()  
                    .Select(e => NameWithPredicate(e))  
                    .StrCat("/") +  
                    (  
                        cd  
                        .Parent  
                        .Nodes()  
                        .OfType<XText>()  
                        .Count() != 1 ?  
                        "text()[" +  
                        (cd  
                        .NodesBeforeSelf()  
                        .OfType<XText>()  
                        .Count() + 1) + "]" :  
                        "text()"  
                    );  
            XText tx = xobj as XText;  
            if (tx != null)  
                return  
                    "/" +  
                    tx  
                    .Parent  
                    .AncestorsAndSelf()  
                    .InDocumentOrder()  
                    .Select(e => NameWithPredicate(e))  
                    .StrCat("/") +  
                    (  
                        tx  
                        .Parent  
                        .Nodes()  
                        .OfType<XText>()  
                        .Count() != 1 ?  
                        "text()[" +  
                        (tx  
                        .NodesBeforeSelf()  
                        .OfType<XText>()  
                        .Count() + 1) + "]" :  
                        "text()"  
                    );  
            XProcessingInstruction pi = xobj as XProcessingInstruction;  
            if (pi != null)  
                return  
                    "/" +  
                    pi  
                    .Parent  
                    .AncestorsAndSelf()  
                    .InDocumentOrder()  
                    .Select(e => NameWithPredicate(e))  
                    .StrCat("/") +  
                    (  
                        pi  
                        .Parent  
                        .Nodes()  
                        .OfType<XProcessingInstruction>()  
                        .Count() != 1 ?  
                        "processing-instruction()[" +  
                        (pi  
                        .NodesBeforeSelf()  
                        .OfType<XProcessingInstruction>()  
                        .Count() + 1) + "]" :  
                        "processing-instruction()"  
                    );  
            return null;  
        }  
    }  
  
    public static IEnumerable<XObject> Find(this XElement source, string value)  
    {  
        if (source.Attributes().Any())  
        {  
            foreach (XAttribute att in source.Attributes())  
            {  
                string contents = (string)att;  
                if (contents.Contains(value))  
                    yield return att;  
            }  
        }  
        if (source.Elements().Any())  
        {  
            foreach (XElement child in source.Elements())  
                foreach (XObject s in child.Find(value))  
                    yield return s;  
        }  
        else  
        {  
            string contents = (string)source;  
            if (contents.Contains(value))  
                yield return source;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement purchaseOrders = XElement.Load("PurchaseOrders.xml");  
  
        IEnumerable<XObject> subset =  
            from xobj in purchaseOrders.Find("1999")  
            select xobj;  
  
        foreach (XObject obj in subset)  
        {  
            Console.WriteLine(obj.GetXPath());  
            if (obj.GetType() == typeof(XElement))  
                Console.WriteLine(((XElement)obj).Value);  
            else if (obj.GetType() == typeof(XAttribute))  
                Console.WriteLine(((XAttribute)obj).Value);  
        }  
    }  
}  
```  
  
 Bu kod aşağıdaki çıktıyı üretir:  
  
```  
/PurchaseOrders/PurchaseOrder[1]/@OrderDate  
1999-10-20  
/PurchaseOrders/PurchaseOrder[1]/Items/Item[2]/ShipDate  
1999-05-21  
/PurchaseOrders/PurchaseOrder[2]/@OrderDate  
1999-10-22  
/PurchaseOrders/PurchaseOrder[3]/@OrderDate  
1999-10-22  
```  
  