---
title: 'Nasıl yapılır: XmlSerializer kullanarak serileştirme (C#)'
ms.date: 07/20/2015
ms.assetid: 2e0a0bbc-c548-4fe2-8741-be5a9ccd0cbb
ms.openlocfilehash: 9d722735f9a83f0d65fbc10b6c868525e8393a7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567769"
---
# <a name="how-to-serialize-using-xmlserializer-c"></a><span data-ttu-id="3b559-102">Nasıl yapılır: XmlSerializer kullanarak serileştirme (C#)</span><span class="sxs-lookup"><span data-stu-id="3b559-102">How to: Serialize Using XmlSerializer (C#)</span></span>
<span data-ttu-id="3b559-103">Bu konuda serileştirir ve kullanarak çıkarır bir örnek gösterilmektedir <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3b559-103">This topic shows an example that serializes and deserializes using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b559-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="3b559-104">Example</span></span>  
 <span data-ttu-id="3b559-105">Aşağıdaki örnek, bir sayı içeren bir nesne oluşturur. <xref:System.Xml.Linq.XElement> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="3b559-105">The following example creates a number of objects that contain <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="3b559-106">Ardından bunları bir bellek akışa serileştirir ve bunları bellek akıştan serisini kaldırır.</span><span class="sxs-lookup"><span data-stu-id="3b559-106">It then serializes them to a memory stream, and then deserializes them from the memory stream.</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Linq;  
using System.Xml;  
using System.Xml.Serialization;  
using System.Xml.Linq;  
  
public class XElementContainer  
{  
    public XElement member;  
  
    public XElementContainer()  
    {  
        member = XLinqTest.CreateXElement();  
    }  
  
    public override string ToString()  
    {  
        return member.ToString();  
    }  
}  
  
public class XElementNullContainer  
{  
    public XElement member;  
  
    public XElementNullContainer()  
    {  
    }  
}  
  
class XLinqTest  
{  
    static void Main(string[] args)  
    {  
        Test<XElementNullContainer>(new XElementNullContainer());  
        Test<XElement>(CreateXElement());  
        Test<XElementContainer>(new XElementContainer());  
    }  
  
    public static XElement CreateXElement()  
    {  
        XNamespace ns = "http://www.adventure-works.com";  
        return new XElement(ns + "aw");  
    }  
  
    static void Test<T>(T obj)  
    {  
        using (MemoryStream stream = new MemoryStream())  
        {  
            XmlSerializer s = new XmlSerializer(typeof(T));  
            Console.WriteLine("Testing for type: {0}", typeof(T));  
            s.Serialize(XmlWriter.Create(stream), obj);  
            stream.Flush();  
            stream.Seek(0, SeekOrigin.Begin);  
            object o = s.Deserialize(XmlReader.Create(stream));  
            Console.WriteLine("  Deserialized type: {0}", o.GetType());  
        }  
    }  
}  
```  
  
 <span data-ttu-id="3b559-107">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="3b559-107">This example produces the following output:</span></span>  
  
```  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b559-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3b559-108">See also</span></span>

- [<span data-ttu-id="3b559-109">XElement nesneleri (C#) içeren nesne grafiklerini serileştirme</span><span class="sxs-lookup"><span data-stu-id="3b559-109">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-object-graphs-that-contain-xelement-objects.md)
