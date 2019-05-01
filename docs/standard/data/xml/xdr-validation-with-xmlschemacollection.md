---
title: XmlSchemaCollection ile XDR Doğrulaması
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 00833027-1428-4586-83c1-42f5de3323d1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca806f0f9c7e1ad859affe05d5db8ec0d3b36b03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959074"
---
# <a name="xdr-validation-with-xmlschemacollection"></a><span data-ttu-id="6b6e9-102">XmlSchemaCollection ile XDR Doğrulaması</span><span class="sxs-lookup"><span data-stu-id="6b6e9-102">XDR Validation with XmlSchemaCollection</span></span>

<span data-ttu-id="6b6e9-103">Karşı doğrulama XML verileri azaltılmış (XDR) şema içinde depolanıyorsa **XmlSchemaCollection**, ad alanı URI belirtilen şema koleksiyonuna zaman eklendi ile ilişkilidir.</span><span class="sxs-lookup"><span data-stu-id="6b6e9-103">If the XML-Data Reduced (XDR) schema you are validating against is stored in the **XmlSchemaCollection**, it is associated with the namespace URI specified when the schema was added to the collection.</span></span> <span data-ttu-id="6b6e9-104">**XmlValidatingReader** koleksiyondaki bu URI'ye karşılık gelen şema XML belgesindeki ad alanı URI eşler.</span><span class="sxs-lookup"><span data-stu-id="6b6e9-104">**XmlValidatingReader** maps the namespace URI in the XML document to the schema that corresponds to that URI in the collection.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b6e9-105"><xref:System.Xml.Schema.XmlSchemaCollection> Sınıf artık kullanımdan kalkmıştır ve ile değiştirilmiştir <xref:System.Xml.Schema.XmlSchemaSet> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="6b6e9-105">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="6b6e9-106">Hakkında daha fazla bilgi için <xref:System.Xml.Schema.XmlSchemaSet> sınıfı bakın [şema derleme için XmlSchemaSet](xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="6b6e9-106">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](xmlschemaset-for-schema-compilation.md).</span></span>

<span data-ttu-id="6b6e9-107">Örneğin, XML belgesi kök öğesi ise `<bookstore xmlns="urn:newbooks-schema">`, şema eklendiğinde **XmlSchemaCollection** gibi aynı ad alanına başvuruyor:</span><span class="sxs-lookup"><span data-stu-id="6b6e9-107">For example, if the root element of the XML document is `<bookstore xmlns="urn:newbooks-schema">`, when the schema is added to the **XmlSchemaCollection** it references the same namespace, as follows:</span></span>

```
xsc.Add("urn:newbooks-schema", "newbooks.xdr")
```

<span data-ttu-id="6b6e9-108">Aşağıdaki kod örneği oluşturur bir **XmlValidatingReader** almayan bir **XmlTextReader** ve HeadCount.xdr, bir XDR şeması için ekler **XmlSchemaCollection**.</span><span class="sxs-lookup"><span data-stu-id="6b6e9-108">The following code example creates an **XmlValidatingReader** that takes an **XmlTextReader** and adds an XDR schema, HeadCount.xdr, to the **XmlSchemaCollection**.</span></span>

```vb
Imports System
Imports System.IO
Imports System.Xml
Imports System.Xml.Schema

Namespace ValidationSample

   Class Sample

      Public Shared Sub Main()
         Dim tr As New XmlTextReader("HeadCount.xml")
         Dim vr As New XmlValidatingReader(tr)

         vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr")
         vr.ValidationType = ValidationType.XDR
         AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler

         While vr.Read()
            PrintTypeInfo(vr)
            If vr.NodeType = XmlNodeType.Element Then
               While vr.MoveToNextAttribute()
                  PrintTypeInfo(vr)
               End While
            End If
         End While
         Console.WriteLine("Validation finished")
      End Sub
      ' Main

      Public Shared Sub PrintTypeInfo(vr As XmlValidatingReader)
         If Not (vr.SchemaType Is Nothing) Then
            If TypeOf vr.SchemaType Is XmlSchemaDatatype Or TypeOf vr.SchemaType Is XmlSchemaSimpleType Then
               Dim value As Object = vr.ReadTypedValue()
               Console.WriteLine("{0}({1},{2}):{3}", vr.NodeType, vr.Name, value.GetType().Name, value)
            End If
         End If
      End Sub
      ' PrintTypeInfo

      Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)
         Console.WriteLine("***Validation error")
         Console.WriteLine("Severity:{0}", args.Severity)
         Console.WriteLine("Message:{0}", args.Message)
      End Sub
      ' ValidationHandler
   End Class
   ' Sample
End Namespace
' ValidationSample
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Schema;

namespace ValidationSample
{
   class Sample
   {
      public static void Main()
      {
         XmlTextReader tr = new XmlTextReader("HeadCount.xml");
         XmlValidatingReader vr = new XmlValidatingReader(tr);

         vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr");
         vr.ValidationType = ValidationType.XDR;
         vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);

         while(vr.Read())
         {
            PrintTypeInfo(vr);
            if(vr.NodeType == XmlNodeType.Element)
            {
               while(vr.MoveToNextAttribute())
                  PrintTypeInfo(vr);
            }
         }
         Console.WriteLine("Validation finished");
      }

      public static void PrintTypeInfo(XmlValidatingReader vr)
      {
         if(vr.SchemaType != null)
         {
            if(vr.SchemaType is XmlSchemaDatatype || vr.SchemaType is XmlSchemaSimpleType)
            {
               object value = vr.ReadTypedValue();
               Console.WriteLine("{0}({1},{2}):{3}", vr.NodeType, vr.Name, value.GetType().Name, value);
            }
         }
      }

      public static void ValidationHandler(object sender, ValidationEventArgs args)
      {
         Console.WriteLine("***Validation error");
         Console.WriteLine("\tSeverity:{0}", args.Severity);
         Console.WriteLine("\tMessage:{0}", args.Message);
      }
   }
}
```

<span data-ttu-id="6b6e9-109">Giriş dosyasının içeriğini aşağıdaki özetler *HeadCount.xml*doğrulanması için:</span><span class="sxs-lookup"><span data-stu-id="6b6e9-109">The following outlines the contents of the input file, *HeadCount.xml*, to be validated:</span></span>

```xml
<!--Load HeadCount.xdr in SchemaCollection for Validation-->
<HeadCount xmlns='xdrHeadCount'>
   <Name>Waldo Pepper</Name>
   <Name>Red Pepper</Name>
</HeadCount>
```

<span data-ttu-id="6b6e9-110">XDR şema dosyasının içeriğini aşağıdaki özetler *HeadCount.xdr*karşı doğrulanması için:</span><span class="sxs-lookup"><span data-stu-id="6b6e9-110">The following outlines the contents of the XDR schema file, *HeadCount.xdr*, to be validated against:</span></span>

```xml
<Schema xmlns="urn:schemas-microsoft-com:xml-data" xmlns:dt="urn:schemas-microsoft-com:datatypes">
   <ElementType name="Name" content="textOnly"/>
   <AttributeType name="Bldg" default="2"/>
   <ElementType name="HeadCount" content="eltOnly">
      <element type="Name"/>
      <attribute type="Bldg"/>
   </ElementType>
</Schema>
```

## <a name="see-also"></a><span data-ttu-id="6b6e9-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6b6e9-111">See also</span></span>

- <xref:System.Xml.XmlValidatingReader.ValidationType%2A>
- [<span data-ttu-id="6b6e9-112">XmlSchemaCollection Şema Derlemesi</span><span class="sxs-lookup"><span data-stu-id="6b6e9-112">XmlSchemaCollection Schema Compilation</span></span>](xmlschemacollection-schema-compilation.md)
