---
title: İşlev ve eylem genel temsilcileri (C#) için varyans kullanma
ms.date: 07/20/2015
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
ms.openlocfilehash: f517eea07588bb01ef903c8311126eab872bd735
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540604"
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a><span data-ttu-id="c8745-102">İşlev ve eylem genel temsilcileri (C#) için varyans kullanma</span><span class="sxs-lookup"><span data-stu-id="c8745-102">Using Variance for Func and Action Generic Delegates (C#)</span></span>
<span data-ttu-id="c8745-103">Bu örnekler Kovaryans ve kontravaryans nasıl kazandırabileceğinizi `Func` ve `Action` yöntemleri kullanılmasını etkinleştirin ve kodunuzu daha fazla esneklik sağlamak için genel temsilciler.</span><span class="sxs-lookup"><span data-stu-id="c8745-103">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="c8745-104">Kovaryans ve kontravaryans hakkında daha fazla bilgi için bkz: [Temsilcilerde varyans (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="c8745-104">For more information about covariance and contravariance, see [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="c8745-105">Birlikte değişken tür parametreleri ile kullanma</span><span class="sxs-lookup"><span data-stu-id="c8745-105">Using Delegates with Covariant Type Parameters</span></span>  
 <span data-ttu-id="c8745-106">Kovaryans genel destek avantajları aşağıdaki örnekte `Func` temsilciler.</span><span class="sxs-lookup"><span data-stu-id="c8745-106">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="c8745-107">`FindByTitle` Yöntemi, bir parametre alır `String` yazın ve bir nesne döndürür `Employee` türü.</span><span class="sxs-lookup"><span data-stu-id="c8745-107">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="c8745-108">Ancak, bu yönteme atayabilirsiniz `Func<String, Person>` çünkü temsilci `Employee` devralan `Person`.</span><span class="sxs-lookup"><span data-stu-id="c8745-108">However, you can assign this method to the `Func<String, Person>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static Employee FindByTitle(String title)  
    {  
        // This is a stub for a method that returns  
        // an employee that has the specified title.  
        return new Employee();  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Func<String, Employee> findEmployee = FindByTitle;  
  
        // The delegate expects a method to return Person,  
        // but you can assign it a method that returns Employee.  
        Func<String, Person> findPerson = FindByTitle;  
  
        // You can also assign a delegate   
        // that returns a more derived type   
        // to a delegate that returns a less derived type.  
        findPerson = findEmployee;  
  
    }  
}  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="c8745-109">Değişken karşıtı tür parametreleri ile kullanma</span><span class="sxs-lookup"><span data-stu-id="c8745-109">Using Delegates with Contravariant Type Parameters</span></span>  
 <span data-ttu-id="c8745-110">Aşağıdaki örnekte genel kontravaryans destek avantajlarını `Action` temsilciler.</span><span class="sxs-lookup"><span data-stu-id="c8745-110">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="c8745-111">`AddToContacts` Yöntemi, bir parametre alır `Person` türü.</span><span class="sxs-lookup"><span data-stu-id="c8745-111">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="c8745-112">Ancak, bu yönteme atayabilirsiniz `Action<Employee>` çünkü temsilci `Employee` devralan `Person`.</span><span class="sxs-lookup"><span data-stu-id="c8745-112">However, you can assign this method to the `Action<Employee>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static void AddToContacts(Person person)  
    {  
        // This method adds a Person object  
        // to a contact list.  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Action<Person> addPersonToContacts = AddToContacts;  
  
        // The Action delegate expects   
        // a method that has an Employee parameter,  
        // but you can assign it a method that has a Person parameter  
        // because Employee derives from Person.  
        Action<Employee> addEmployeeToContacts = AddToContacts;  
  
        // You can also assign a delegate   
        // that accepts a less derived parameter to a delegate   
        // that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8745-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c8745-113">See also</span></span>

- [<span data-ttu-id="c8745-114">Kovaryans ve kontravaryans (C#)</span><span class="sxs-lookup"><span data-stu-id="c8745-114">Covariance and Contravariance (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="c8745-115">Genel Türler</span><span class="sxs-lookup"><span data-stu-id="c8745-115">Generics</span></span>](~/docs/standard/generics/index.md)
