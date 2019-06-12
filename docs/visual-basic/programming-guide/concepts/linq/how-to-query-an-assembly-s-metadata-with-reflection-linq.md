---
title: 'Nasıl yapılır: Bir derlemenin meta verilerini (LINQ) (Visual Basic) yansıma ile sorgulama'
ms.date: 07/20/2015
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
ms.openlocfilehash: fd9fa5fcbd1f02cec4e96511fa8c4e60d77ce965
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67026062"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-visual-basic"></a>Nasıl yapılır: Bir derlemenin meta verilerini (LINQ) (Visual Basic) yansıma ile sorgulama
Aşağıdaki örnek nasıl LINQ yansıma ile belirtilen arama ölçütüyle eşleşen yöntemleri ile ilgili özel meta verilerini almak için kullanılabileceğini gösterir. Bu durumda, sorgu, diziler gibi numaralandırılabilir türleri döndüren derlemedeki tüm yöntemlerin adlarını bulabilirsiniz.  
  
## <a name="example"></a>Örnek  
  
```vb
Imports System.Linq
Imports System.Reflection  

Module Module1  
    Sub Main()  
        Dim asmbly As Assembly =
            Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089")  
  
        Dim pubTypesQuery = From type In asmbly.GetTypes()
                            Where type.IsPublic
                            From method In type.GetMethods()
                            Where method.ReturnType.IsArray = True
                            Let name = method.ToString()
                            Let typeName = type.ToString()
                            Group name By typeName Into methodNames = Group  
  
        Console.WriteLine("Getting ready to iterate")  
        For Each item In pubTypesQuery  
            Console.WriteLine(item.methodNames)  
  
            For Each type In item.methodNames  
                Console.WriteLine(" " & type)  
            Next  
        Next  
        Console.WriteLine("Press any key to exit... ")  
        Console.ReadKey()  
    End Sub  
End Module  
```  
  
Örnekte <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> yöntemi Belirtilen derlemedeki türleri dizisi döndürür. [Where yan tümcesi](../../../../visual-basic/language-reference/queries/where-clause.md) filtre, böylece yalnızca genel türleri döndürülen uygulanır. Her bir genel türü için sorgu kullanılarak oluşturulan <xref:System.Reflection.MethodInfo> öğesinden döndürülen dizi <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> çağırın. Dönüş türü olan bir dizi; Aksi takdirde uygulayan bir tür yöntemleri döndürmek için bu sonuçları filtrelenir <xref:System.Collections.Generic.IEnumerable%601>. Son olarak, bu sonuç tür adı bir anahtar kullanarak gruplanır.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ to Objects'in (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
