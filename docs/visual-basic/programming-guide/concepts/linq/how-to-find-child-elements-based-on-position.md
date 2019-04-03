---
title: 'Nasıl yapılır: Konum (XPath-LINQ to XML) göre alt öğeleri bulma (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 6831e1db-5e97-444f-a7a1-d0a87104b005
ms.openlocfilehash: 57b9f3d7986bd85a65716c833165e7b073414ef0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831611"
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-visual-basic"></a>Nasıl yapılır: Konum (XPath-LINQ to XML) göre alt öğeleri bulma (Visual Basic)
Bazen kendi konumlarına göre öğeleri bulmak istediğiniz. İkinci öğe bulmak isteyebilirsiniz veya beşinci öğeyi aracılığıyla üçüncü bulmak isteyebilirsiniz.  
  
 XPath ifadesidir:  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 Bu yazma için iki yaklaşım vardır [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] yavaş bir şekilde sorgu. Kullanabileceğiniz <xref:System.Linq.Enumerable.Skip%2A> ve <xref:System.Linq.Enumerable.Take%2A> işleçleri veya kullanabileceğiniz <xref:System.Linq.Enumerable.Where%2A> dizin alan aşırı yüklemesini. Kullanırken <xref:System.Linq.Enumerable.Where%2A> aşırı yüklemesi, iki bağımsız değişken alan bir lambda ifadesi kullanın. Aşağıdaki örnek, iki yöntem de konumlarına göre seçme gösterir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte ikinci dördüncü aracılığıyla bulur `Test` öğesi. Öğelerinin bir koleksiyonunu sonucudur.  
  
 Bu örnek aşağıdaki XML belgesi kullanır: [Örnek XML dosyası: Test yapılandırması (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).  
  
```vb  
Dim testCfg As XElement = XElement.Load("TestConfig.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test").Skip(1).Take(3)  
  
'LINQ to XML query  
Dim list2 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test"). _  
    Where(Function(ByVal el, ByVal idx) idx >= 1 And idx <= 3)  
  
' XPath expression  
Dim list3 As IEnumerable(Of XElement) = _  
    testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]")  
  
If list1.Count() = list2.Count() And _  
       list1.Count() = list3.Count() And _  
       list1.Intersect(list2).Count() = list1.Count() And _  
       list1.Intersect(list3).Count() = list1.Count() Then  
  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```  
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
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ to XML için XPath kullanıcıları (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
