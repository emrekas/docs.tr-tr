---
title: 'Nasıl yapılır: Konuma göre alt öğeleri bul (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: e35bb269-ec86-4c96-8321-12491a0eb2c3
ms.openlocfilehash: 1adbbb6dd074ffcb39269a800024e444cf8791d1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253754"
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-c"></a>Nasıl yapılır: Konuma göre alt öğeleri bul (XPath-LINQ to XML) (C#)
Bazen, konumlarına göre öğeleri bulmak isteyebilirsiniz. İkinci öğeyi bulmak isteyebilirsiniz veya beşinci öğe aracılığıyla üçüncü öğeyi bulmak isteyebilirsiniz.  
  
 XPath ifadesi:  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 Bu [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sorguyu geç bir şekilde yazmak için iki yaklaşım vardır. <xref:System.Linq.Enumerable.Skip%2A> Ve<xref:System.Linq.Enumerable.Take%2A> işleçlerini kullanabilir<xref:System.Linq.Enumerable.Where%2A> veya bir dizini alan aşırı yüklemeyi kullanabilirsiniz. <xref:System.Linq.Enumerable.Where%2A> Aşırı yüklemeyi kullandığınızda, iki bağımsız değişken alan bir lambda ifadesi kullanırsınız. Aşağıdaki örnek, konum temelinde seçim yapmak için her iki yöntemi gösterir.  
  
## <a name="example"></a>Örnek  
 Bu örnek, dördüncü `Test` öğe aracılığıyla ikincisini bulur. Sonuç, öğelerin bir koleksiyonudur.  
  
 Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Test yapılandırması (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).  
  
```csharp  
XElement testCfg = XElement.Load("TestConfig.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    testCfg  
    .Elements("Test")  
    .Skip(1)  
    .Take(3);  
  
// LINQ to XML query  
IEnumerable<XElement> list2 =  
    testCfg  
    .Elements("Test")  
    .Where((el, idx) => idx >= 1 && idx <= 3);  
  
// XPath expression  
IEnumerable<XElement> list3 =  
  testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]");  
  
if (list1.Count() == list2.Count() &&  
    list1.Count() == list3.Count() &&  
    list1.Intersect(list2).Count() == list1.Count() &&  
    list1.Intersect(list3).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```output  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
