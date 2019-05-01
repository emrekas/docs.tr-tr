---
title: 'Nasıl yapılır: SOAP Kodlu XML Akışı Olarak Nesneyi Serileştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
ms.openlocfilehash: bfbdda0861a6f2867a2e7003dd7054129fd343b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018027"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="37119-102">Nasıl yapılır: SOAP Kodlu XML Akışı Olarak Nesneyi Serileştirme</span><span class="sxs-lookup"><span data-stu-id="37119-102">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="37119-103">XML, kullanarak bir SOAP ileti inşa edildiğinden <xref:System.Xml.Serialization.XmlSerializer> sınıfı sınıfları seri hale getirmek ve kodlanmış SOAP iletilerini oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="37119-103">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="37119-104">Elde edilen XML uyan ["Basit Nesne Erişim Protokolü (SOAP) 1.1" World Wide Web Consortium belgesinin 5 bölümüne](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span><span class="sxs-lookup"><span data-stu-id="37119-104">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="37119-105">SOAP iletilerini iletişim kuran bir XML Web hizmeti oluştururken, sınıflar ve sınıf üyeleri için özel SOAP öznitelikleri kümesi uygulayarak XML akışı özelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="37119-105">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="37119-106">Öznitelikler listesi için bkz. [öznitelikleri emin denetim kodlanmış SOAP serileştirme](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="37119-106">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="37119-107">SOAP kodlu XML akışı olarak bir nesneyi serileştirmek için</span><span class="sxs-lookup"><span data-stu-id="37119-107">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1. <span data-ttu-id="37119-108">Sınıfını kullanarak oluşturmak [XML şema tanımı Aracı (XSD.exe'nin)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="37119-108">Create the class using the [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2. <span data-ttu-id="37119-109">Bir uygulama veya daha fazla özel öznitelik bulunan `System.Xml.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="37119-109">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="37119-110">"Öznitelikler bu denetim kodlanan SOAP serileştirme." listesinde bakın</span><span class="sxs-lookup"><span data-stu-id="37119-110">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3. <span data-ttu-id="37119-111">Oluşturma bir `XmlTypeMapping` yeni bir oluşturarak `SoapReflectionImporter`ve çağırma `ImportTypeMapping` sahip serileştirilmiş sınıf türü yöntemi.</span><span class="sxs-lookup"><span data-stu-id="37119-111">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="37119-112">Aşağıdaki kod örneği çağrıları `ImportTypeMapping` yöntemi `SoapReflectionImporter` sınıfı oluşturmak için bir `XmlTypeMapping`.</span><span class="sxs-lookup"><span data-stu-id="37119-112">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping =
        New SoapReflectionImporter().ImportTypeMapping(GetType(Group))  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping =
        new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
    ```  
  
4. <span data-ttu-id="37119-113">Bir örneğini oluşturmak `XmlSerializer` geçirerek sınıf `XmlTypeMapping` için <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="37119-113">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. <span data-ttu-id="37119-114">Arama `Serialize` veya `Deserialize` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="37119-114">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37119-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="37119-115">Example</span></span>  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping =
    New SoapReflectionImporter().ImportTypeMapping(GetType(Group))
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping =
    new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## <a name="see-also"></a><span data-ttu-id="37119-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="37119-116">See also</span></span>

- [<span data-ttu-id="37119-117">XML ve SOAP Serileştirme</span><span class="sxs-lookup"><span data-stu-id="37119-117">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- [<span data-ttu-id="37119-118">Kodlanmış SOAP Serileştirmesini Denetleyen Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="37119-118">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="37119-119">XML Web Hizmetleri ile XML Serileştirme</span><span class="sxs-lookup"><span data-stu-id="37119-119">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)
- [<span data-ttu-id="37119-120">Nasıl yapılır: Bir nesneyi serileştirmek</span><span class="sxs-lookup"><span data-stu-id="37119-120">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="37119-121">Nasıl yapılır: Bir nesneyi seri durumdan çıkarma</span><span class="sxs-lookup"><span data-stu-id="37119-121">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [<span data-ttu-id="37119-122">Nasıl yapılır: Kodlanmış SOAP XML serileştirmesini geçersiz kılma</span><span class="sxs-lookup"><span data-stu-id="37119-122">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)
