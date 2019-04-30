---
title: Yansıma (C#) kullanarak özniteliklere erişme
ms.date: 07/20/2015
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
ms.openlocfilehash: f7c7b89be13022471f4e17bcb6ed9a90bcbc1c54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61668646"
---
# <a name="accessing-attributes-by-using-reflection-c"></a>Yansıma (C#) kullanarak özniteliklere erişme
Özel öznitelikler tanımlamak ve bunları kaynak kodunuzu getirin olgu üzerinde çalışan ve bu bilgileri alınırken bir şekilde olmadan küçük değer olacaktır. Yansıma kullanarak özel öznitelik tanımlandı bilgi alabilirsiniz. Anahtar yöntemi `GetCustomAttributes`, kaynak kod özniteliklerini çalışma zamanı eşdeğerleri olan nesneler dizisi döndürür. Bu yöntem, birden fazla aşırı yüklenmiş sürümleri vardır. Daha fazla bilgi için bkz. <xref:System.Attribute>.  
  
 Bir öznitelik belirtimi gibi:  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 Bunun için kavramsal olarak eşdeğerdir:  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 Ancak, kod kadar yürütülmez `SampleClass` öznitelikleri için sorgulanır. Çağırma `GetCustomAttributes` üzerinde `SampleClass` neden olan bir `Author` nesne oluşturulur ve yukarıdaki gibi başlatıldı. Sınıfın diğer öznitelikleri varsa, diğer öznitelik nesneleri benzer şekilde oluşturulur. `GetCustomAttributes` ardından döndürür `Author` ve diğer öznitelik nesneleri bir dizideki nesne. Bu dizi yineleme hangi özniteliklerin her dizi öğesi türüne bağlı olarak uygulanan belirlemek ve öznitelik nesnelerden bilgiler ayıklayın.  
  
## <a name="example"></a>Örnek  
 Tam bir örnek aşağıda verilmiştir. Özel bir öznitelik tanımlı, birden fazla varlıklarına uygulanan ve yansıma alınır.  
  
```csharp  
// Multiuse attribute.  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // Multiuse attribute.  
]  
public class Author : System.Attribute  
{  
    string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
  
        // Default value.  
        version = 1.0;  
    }  
  
    public string GetName()  
    {  
        return name;  
    }  
}  
  
// Class with the Author attribute.  
[Author("P. Ackerman")]  
public class FirstClass  
{  
    // ...  
}  
  
// Class without the Author attribute.  
public class SecondClass  
{  
    // ...  
}  
  
// Class with multiple Author attributes.  
[Author("P. Ackerman"), Author("R. Koch", version = 2.0)]  
public class ThirdClass  
{  
    // ...  
}  
  
class TestAuthorAttribute  
{  
    static void Test()  
    {  
        PrintAuthorInfo(typeof(FirstClass));  
        PrintAuthorInfo(typeof(SecondClass));  
        PrintAuthorInfo(typeof(ThirdClass));  
    }  
  
    private static void PrintAuthorInfo(System.Type t)  
    {  
        System.Console.WriteLine("Author information for {0}", t);  
  
        // Using reflection.  
        System.Attribute[] attrs = System.Attribute.GetCustomAttributes(t);  // Reflection.  
  
        // Displaying output.  
        foreach (System.Attribute attr in attrs)  
        {  
            if (attr is Author)  
            {  
                Author a = (Author)attr;  
                System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version);  
            }  
        }  
    }  
}  
/* Output:  
    Author information for FirstClass  
       P. Ackerman, version 1.00  
    Author information for SecondClass  
    Author information for ThirdClass  
       R. Koch, version 2.00  
       P. Ackerman, version 1.00  
*/  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Reflection>
- <xref:System.Attribute>
- [C# Programlama Kılavuzu](../../../../csharp/programming-guide/index.md)
- [Özniteliklerde Depolanan Bilgileri Alma](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- [Yansıma (C#)](../../../../csharp/programming-guide/concepts/reflection.md)
- [Öznitelikler (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md)
- [Özel öznitelikler (C#) oluşturma](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)
