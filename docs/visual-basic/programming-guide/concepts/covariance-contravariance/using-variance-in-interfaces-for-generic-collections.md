---
title: (Visual Basic) genel koleksiyonlar için arabirimlerde varyans kullanma
ms.date: 07/20/2015
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
ms.openlocfilehash: 7265fc208b7538a2ab63822afbe63b09b0f34135
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735415"
---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a>(Visual Basic) genel koleksiyonlar için arabirimlerde varyans kullanma
Birlikte değişen bir arabirimin yöntemlerinin dönüş arabiriminde belirtilenlerden daha türetilmiş türleri sağlar. Bir değişken karşıtı arabirimi belirtilenlerden daha az türetilmiş türler arabiriminde parametrelerini kabul edecek şekilde yöntemlerini sağlar.  
  
 .NET Framework 4'te çeşitli mevcut arabirimlerin birlikte değişen hale geldi ve değişken karşıtı. Bunlar <xref:System.Collections.Generic.IEnumerable%601> ve <xref:System.IComparable%601>. Bu, türetilmiş türler için temel türleri genel koleksiyonlar ile çalışan yöntemlerini kullanmayı sağlar.  
  
 .NET Framework'teki değişken arabirimler listesi için bkz. [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).  
  
## <a name="converting-generic-collections"></a>Genel koleksiyonlar dönüştürme  
 Kovaryans destek avantajları aşağıdaki örnekte <xref:System.Collections.Generic.IEnumerable%601> arabirimi. `PrintFullName` Yöntemi koleksiyonunu kabul `IEnumerable(Of Person)` türü bir parametre olarak. Ancak, bir koleksiyonu için kullanabilirsiniz `IEnumerable(Of Person)` türü için `Employee` devralan `Person`.  
  
```vb  
' Simple hierarchy of classes.  
Public Class Person  
    Public Property FirstName As String  
    Public Property LastName As String  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
' The method has a parameter of the IEnumerable(Of Person) type.  
Public Sub PrintFullName(ByVal persons As IEnumerable(Of Person))  
    For Each person As Person In persons  
        Console.WriteLine(  
            "Name: " & person.FirstName & " " & person.LastName)  
    Next  
End Sub  
  
Sub Main()  
    Dim employees As IEnumerable(Of Employee) = New List(Of Employee)  
  
    ' You can pass IEnumerable(Of Employee),   
    ' although the method expects IEnumerable(Of Person).  
  
    PrintFullName(employees)  
  
End Sub  
```  
  
## <a name="comparing-generic-collections"></a>Genel koleksiyonları karşılaştırma  
 Aşağıdaki örnekte kontravaryans destek avantajlarını <xref:System.Collections.Generic.IComparer%601> arabirimi. `PersonComparer` Sınıfının Implements `IComparer(Of Person)` arabirimi. Ancak, bir dizi nesnelerini karşılaştırmak için bu sınıfı yeniden kullanabilirsiniz `Employee` türü için `Employee` devralan `Person`.  
  
```vb  
' Simple hierarhcy of classes.  
Public Class Person  
    Public Property FirstName As String  
    Public Property LastName As String  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
' The custom comparer for the Person type  
' with standard implementations of Equals()  
' and GetHashCode() methods.  
Class PersonComparer  
    Implements IEqualityComparer(Of Person)  
  
    Public Function Equals1(  
        ByVal x As Person,  
        ByVal y As Person) As Boolean _  
        Implements IEqualityComparer(Of Person).Equals  
  
        If x Is y Then Return True  
        If x Is Nothing OrElse y Is Nothing Then Return False  
        Return (x.FirstName = y.FirstName) AndAlso  
            (x.LastName = y.LastName)  
    End Function  
    Public Function GetHashCode1(  
        ByVal person As Person) As Integer _  
        Implements IEqualityComparer(Of Person).GetHashCode  
  
        If person Is Nothing Then Return 0  
        Dim hashFirstName =  
            If(person.FirstName Is Nothing,  
            0, person.FirstName.GetHashCode())  
        Dim hashLastName = person.LastName.GetHashCode()  
        Return hashFirstName Xor hashLastName  
    End Function  
End Class  
  
Sub Main()  
    Dim employees = New List(Of Employee) From {  
        New Employee With {.FirstName = "Michael", .LastName = "Alexander"},  
        New Employee With {.FirstName = "Jeff", .LastName = "Price"}  
    }  
  
    ' You can pass PersonComparer,   
    ' which implements IEqualityComparer(Of Person),  
    ' although the method expects IEqualityComparer(Of Employee)  
  
    Dim noduplicates As IEnumerable(Of Employee) = employees.Distinct(New PersonComparer())  
  
    For Each employee In noduplicates  
        Console.WriteLine(employee.FirstName & " " & employee.LastName)  
    Next  
End Sub  
```  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
