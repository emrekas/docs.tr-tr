---
title: XML Verilerine Nesne Hiyerarşisi Eşleme
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1808121049c6344b72b1c9d99e19c46422dfa0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650287"
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a><span data-ttu-id="4a8ac-102">XML Verilerine Nesne Hiyerarşisi Eşleme</span><span class="sxs-lookup"><span data-stu-id="4a8ac-102">Mapping the Object Hierarchy to XML Data</span></span>
<span data-ttu-id="4a8ac-103">Bir XML belgesi bellekte olduğunda, kavramsal bir ağaç gösterimidir.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-103">When an XML document is in memory, the conceptual representation is a tree.</span></span> <span data-ttu-id="4a8ac-104">Programlama için ağaç düğümleri erişmek için bir nesne hiyerarşisine sahip.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-104">For programming, you have an object hierarchy to access the nodes of the tree.</span></span> <span data-ttu-id="4a8ac-105">Aşağıdaki örnek nasıl düğümleri XML içeriği haline gelir gösterir.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-105">The following example shows you how the XML content becomes nodes.</span></span>  
  
 <span data-ttu-id="4a8ac-106">XML XML belge nesne modeli (DOM) içine okunduğu gibi parçaları düğümlere çevrilir ve bu düğümler, düğüm türü ve değerleri gibi kendileri hakkında ek meta veriler korur.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-106">As the XML is read into the XML Document Object Model (DOM), the pieces are translated into nodes, and these nodes retain additional metadata about themselves, such as their node type and values.</span></span> <span data-ttu-id="4a8ac-107">Düğüm türü, nesne ve hangi işlemler gerçekleştirilebilir belirler ve hangi özellikleri ayarlamak veya alınır.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-107">The node type is its object and is what determines what actions can be performed and what properties can be set or retrieved.</span></span>  
  
 <span data-ttu-id="4a8ac-108">Aşağıdaki basit XML varsa:</span><span class="sxs-lookup"><span data-stu-id="4a8ac-108">If you have the following simple XML:</span></span>  
  
 <span data-ttu-id="4a8ac-109">**Giriş**</span><span class="sxs-lookup"><span data-stu-id="4a8ac-109">**Input**</span></span>  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 <span data-ttu-id="4a8ac-110">Giriş bellekte aşağıdaki düğüm ağacı atanan düğüm türü özelliği ile gösterilir:</span><span class="sxs-lookup"><span data-stu-id="4a8ac-110">The input is represented in memory as the following node tree with the assigned node type property:</span></span>  
  
 <span data-ttu-id="4a8ac-111">![örnek düğüm ağacı](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span><span class="sxs-lookup"><span data-stu-id="4a8ac-111">![example node tree](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span></span>  
<span data-ttu-id="4a8ac-112">Kitap ve başlık düğüm ağacı gösterimi</span><span class="sxs-lookup"><span data-stu-id="4a8ac-112">Book and title node tree representation</span></span>  
  
 <span data-ttu-id="4a8ac-113">`book` Öğesi olur bir **XmlElement** nesnesi, sonraki öğeye `title`, ayrıca olur bir **XmlElement**, öğe içerik olurken bir **XmlText** nesne.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-113">The `book` element becomes an **XmlElement** object, the next element, `title`, also becomes an **XmlElement**, while the element content becomes an **XmlText** object.</span></span> <span data-ttu-id="4a8ac-114">Bakarak içinde **XmlElement** yöntemleri ve özellikleri, yöntemleri ve özellikleri yöntemleri ve özellikleri kullanılabilir daha farklı bir **XmlText** nesne.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-114">In looking at the **XmlElement** methods and properties, the methods and properties are different than the methods and properties available on an **XmlText** object.</span></span> <span data-ttu-id="4a8ac-115">Bu nedenle kendi düğüm türü gerçekleştirilecek işlemleri belirleyen XML işaretlemesini haline gelir hangi düğüm türü önemlidir bilerek.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-115">So knowing what node type the XML markup becomes is vital, as its node type determines the actions that can be performed.</span></span>  
  
 <span data-ttu-id="4a8ac-116">Aşağıdaki örnek, XML verileri okur ve düğüm türüne bağlı olarak farklı metin yazar.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-116">The following example reads in XML data and writes out different text, depending on the node type.</span></span> <span data-ttu-id="4a8ac-117">Giriş olarak aşağıdaki XML veri dosyasını kullanarak **items.xml**:</span><span class="sxs-lookup"><span data-stu-id="4a8ac-117">Using the following XML data file as input, **items.xml**:</span></span>  
  
 <span data-ttu-id="4a8ac-118">**Giriş**</span><span class="sxs-lookup"><span data-stu-id="4a8ac-118">**Input**</span></span>  
  
```xml  
<?xml version="1.0"?>  
<!-- This is a sample XML document -->  
<!DOCTYPE Items [<!ENTITY number "123">]>  
<Items>  
  <Item>Test with an entity: &number;</Item>  
  <Item>test with a child element <more/> stuff</Item>  
  <Item>test with a CDATA section <![CDATA[<456>]]> def</Item>  
  <Item>Test with a char entity: A</Item>  
  <!-- Fourteen chars in this element.-->  
  <Item>1234567890ABCD</Item>  
</Items>  
```  
  
 <span data-ttu-id="4a8ac-119">Aşağıdaki kod örneği okuma **items.xml** dosya ve her düğüm türü bilgilerini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-119">The following code example reads the **items.xml** file and displays information for each node type.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
    Private Const filename As String = "items.xml"  
  
    Public Shared Sub Main()  
  
        Dim reader As XmlTextReader = Nothing  
  
        Try  
            ' Load the reader with the data file and   
            'ignore all white space nodes.   
            reader = New XmlTextReader(filename)  
            reader.WhitespaceHandling = WhitespaceHandling.None  
  
            ' Parse the file and display each of the nodes.  
            While reader.Read()  
                Select Case reader.NodeType  
                    Case XmlNodeType.Element  
                        Console.Write("<{0}>", reader.Name)  
                    Case XmlNodeType.Text  
                        Console.Write(reader.Value)  
                    Case XmlNodeType.CDATA  
                        Console.Write("<![CDATA[{0}]]>", reader.Value)  
                    Case XmlNodeType.ProcessingInstruction  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value)  
                    Case XmlNodeType.Comment  
                        Console.Write("<!--{0}-->", reader.Value)  
                    Case XmlNodeType.XmlDeclaration  
                        Console.Write("<?xml version='1.0'?>")  
                    Case XmlNodeType.Document  
                    Case XmlNodeType.DocumentType  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value)  
                    Case XmlNodeType.EntityReference  
                        Console.Write(reader.Name)  
                    Case XmlNodeType.EndElement  
                        Console.Write("</{0}>", reader.Name)  
                End Select  
            End While  
  
        Finally  
            If Not (reader Is Nothing) Then  
                reader.Close()  
            End If  
        End Try  
    End Sub 'Main ' End class  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    private const String filename = "items.xml";  
  
    public static void Main()  
    {  
        XmlTextReader reader = null;  
  
        try  
        {  
            // Load the reader with the data file and ignore   
            // all white space nodes.  
            reader = new XmlTextReader(filename);  
            reader.WhitespaceHandling = WhitespaceHandling.None;  
  
            // Parse the file and display each of the nodes.  
            while (reader.Read())  
            {  
                switch (reader.NodeType)  
                {  
                    case XmlNodeType.Element:  
                        Console.Write("<{0}>", reader.Name);  
                        break;  
                    case XmlNodeType.Text:  
                        Console.Write(reader.Value);  
                        break;  
                    case XmlNodeType.CDATA:  
                        Console.Write("<![CDATA[{0}]]>", reader.Value);  
                        break;  
                    case XmlNodeType.ProcessingInstruction:  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.Comment:  
                        Console.Write("<!--{0}-->", reader.Value);  
                        break;  
                    case XmlNodeType.XmlDeclaration:  
                        Console.Write("<?xml version='1.0'?>");  
                        break;  
                    case XmlNodeType.Document:  
                        break;  
                    case XmlNodeType.DocumentType:  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.EntityReference:  
                        Console.Write(reader.Name);  
                        break;  
                    case XmlNodeType.EndElement:  
                        Console.Write("</{0}>", reader.Name);  
                        break;  
                }  
            }  
        }  
  
        finally  
        {  
            if (reader != null)  
                reader.Close();  
        }  
    }  
} // End class  
```  
  
 <span data-ttu-id="4a8ac-120">Örnekteki çıktının eşleme düğüm türleri verileri ortaya çıkarır.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-120">The output from the example reveals the mapping of the data to the node types.</span></span>  
  
 <span data-ttu-id="4a8ac-121">**Output**</span><span class="sxs-lookup"><span data-stu-id="4a8ac-121">**Output**</span></span>  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>  
```  
  
 <span data-ttu-id="4a8ac-122">Aynı anda tek giriş satırı alma ve koddan oluşturulan çıktı kullanarak, hangi düğüm sınaması çıktı satırları oluşturulan XML verileri ne tür bir düğüm türü hale geldi. böylece anlama analiz etmek için aşağıdaki tabloyu kullanın.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-122">Taking the input one line at a time and using the output generated from the code, you can use the following table to analyze what node test generated which lines of output, thereby understanding what XML data became what kind of node type.</span></span>  
  
|<span data-ttu-id="4a8ac-123">Giriş</span><span class="sxs-lookup"><span data-stu-id="4a8ac-123">Input</span></span>|<span data-ttu-id="4a8ac-124">Çıkış</span><span class="sxs-lookup"><span data-stu-id="4a8ac-124">Output</span></span>|<span data-ttu-id="4a8ac-125">Düğüm türü Test</span><span class="sxs-lookup"><span data-stu-id="4a8ac-125">Node Type Test</span></span>|  
|-----------|------------|--------------------|  
|<span data-ttu-id="4a8ac-126">\<? xml version = "1.0"? ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-126">\<?xml version="1.0"?></span></span>|<span data-ttu-id="4a8ac-127">\<? xml version ='1.0 '? ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-127">\<?xml version='1.0'?></span></span>|<span data-ttu-id="4a8ac-128">XmlNodeType.XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="4a8ac-128">XmlNodeType.XmlDeclaration</span></span>|  
|<span data-ttu-id="4a8ac-129">\<!--Bu örnek bir XML belgesi,--></span><span class="sxs-lookup"><span data-stu-id="4a8ac-129">\<!-- This is a sample XML document --></span></span>|<span data-ttu-id="4a8ac-130">\<!--Bu örnek bir XML belgesi,--></span><span class="sxs-lookup"><span data-stu-id="4a8ac-130">\<!--This is a sample XML document --></span></span>|<span data-ttu-id="4a8ac-131">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="4a8ac-131">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="4a8ac-132">\<! DOCTYPE öğeleri [\<! Varlık numarası "123" >] ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span></span>|<span data-ttu-id="4a8ac-133">\<! DOCTYPE öğeleri [\<! Varlık numarası "123" >]</span><span class="sxs-lookup"><span data-stu-id="4a8ac-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span></span>|<span data-ttu-id="4a8ac-134">XmlNodeType.DocumentType</span><span class="sxs-lookup"><span data-stu-id="4a8ac-134">XmlNodeType.DocumentType</span></span>|  
|<span data-ttu-id="4a8ac-135">\<Öğeler ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-135">\<Items></span></span>|<span data-ttu-id="4a8ac-136">\<Öğeler ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-136">\<Items></span></span>|<span data-ttu-id="4a8ac-137">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="4a8ac-137">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="4a8ac-138">\<Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-138">\<Item></span></span>|<span data-ttu-id="4a8ac-139">\<Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-139">\<Item></span></span>|<span data-ttu-id="4a8ac-140">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="4a8ac-140">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="4a8ac-141">Bir varlık ile test edin: &number;</span><span class="sxs-lookup"><span data-stu-id="4a8ac-141">Test with an entity: &number;</span></span>|<span data-ttu-id="4a8ac-142">Bir varlık ile test edin: 123</span><span class="sxs-lookup"><span data-stu-id="4a8ac-142">Test with an entity: 123</span></span>|<span data-ttu-id="4a8ac-143">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="4a8ac-143">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="4a8ac-144">\</ Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-144">\</Item></span></span>|<span data-ttu-id="4a8ac-145">\</ Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-145">\</Item></span></span>|<span data-ttu-id="4a8ac-146">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="4a8ac-146">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="4a8ac-147">\<Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-147">\<Item></span></span>|<span data-ttu-id="4a8ac-148">\<Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-148">\<Item></span></span>|<span data-ttu-id="4a8ac-149">XmNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="4a8ac-149">XmNodeType.Element</span></span>|  
|<span data-ttu-id="4a8ac-150">bir alt öğesi ile test</span><span class="sxs-lookup"><span data-stu-id="4a8ac-150">test with a child element</span></span>|<span data-ttu-id="4a8ac-151">bir alt öğesi ile test</span><span class="sxs-lookup"><span data-stu-id="4a8ac-151">test with a child element</span></span>|<span data-ttu-id="4a8ac-152">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="4a8ac-152">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="4a8ac-153">\<Daha fazla ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-153">\<more></span></span>|<span data-ttu-id="4a8ac-154">\<Daha fazla ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-154">\<more></span></span>|<span data-ttu-id="4a8ac-155">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="4a8ac-155">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="4a8ac-156">öğe</span><span class="sxs-lookup"><span data-stu-id="4a8ac-156">stuff</span></span>|<span data-ttu-id="4a8ac-157">öğe</span><span class="sxs-lookup"><span data-stu-id="4a8ac-157">stuff</span></span>|<span data-ttu-id="4a8ac-158">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="4a8ac-158">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="4a8ac-159">\</ Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-159">\</Item></span></span>|<span data-ttu-id="4a8ac-160">\</ Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-160">\</Item></span></span>|<span data-ttu-id="4a8ac-161">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="4a8ac-161">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="4a8ac-162">\<Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-162">\<Item></span></span>|<span data-ttu-id="4a8ac-163">\<Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-163">\<Item></span></span>|<span data-ttu-id="4a8ac-164">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="4a8ac-164">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="4a8ac-165">CDATA bölümü ile test</span><span class="sxs-lookup"><span data-stu-id="4a8ac-165">test with a CDATA section</span></span>|<span data-ttu-id="4a8ac-166">CDATA bölümü ile test</span><span class="sxs-lookup"><span data-stu-id="4a8ac-166">test with a CDATA section</span></span>|<span data-ttu-id="4a8ac-167">XmlTest.Text</span><span class="sxs-lookup"><span data-stu-id="4a8ac-167">XmlTest.Text</span></span>|  
|<span data-ttu-id="4a8ac-168">&LT;! [CDATA [\<456 &GT;]]\></span><span class="sxs-lookup"><span data-stu-id="4a8ac-168"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="4a8ac-169">&LT;! [CDATA [\<456 &GT;]]\></span><span class="sxs-lookup"><span data-stu-id="4a8ac-169"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="4a8ac-170">XmlTest.CDATA</span><span class="sxs-lookup"><span data-stu-id="4a8ac-170">XmlTest.CDATA</span></span>|  
|<span data-ttu-id="4a8ac-171">def</span><span class="sxs-lookup"><span data-stu-id="4a8ac-171">def</span></span>|<span data-ttu-id="4a8ac-172">def</span><span class="sxs-lookup"><span data-stu-id="4a8ac-172">def</span></span>|<span data-ttu-id="4a8ac-173">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="4a8ac-173">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="4a8ac-174">\</ Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-174">\</Item></span></span>|<span data-ttu-id="4a8ac-175">\</ Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-175">\</Item></span></span>|<span data-ttu-id="4a8ac-176">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="4a8ac-176">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="4a8ac-177">\<Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-177">\<Item></span></span>|<span data-ttu-id="4a8ac-178">\<Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-178">\<Item></span></span>|<span data-ttu-id="4a8ac-179">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="4a8ac-179">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="4a8ac-180">Char varlığı ile test: &\#65;</span><span class="sxs-lookup"><span data-stu-id="4a8ac-180">Test with a char entity: &\#65;</span></span>|<span data-ttu-id="4a8ac-181">Bir karakter varlık ile test edin: BİR</span><span class="sxs-lookup"><span data-stu-id="4a8ac-181">Test with a char entity: A</span></span>|<span data-ttu-id="4a8ac-182">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="4a8ac-182">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="4a8ac-183">\</ Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-183">\</Item></span></span>|<span data-ttu-id="4a8ac-184">\</ Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-184">\</Item></span></span>|<span data-ttu-id="4a8ac-185">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="4a8ac-185">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="4a8ac-186">\<!--Bu öğe. on dört karakter--></span><span class="sxs-lookup"><span data-stu-id="4a8ac-186">\<!-- Fourteen chars in this element.--></span></span>|<span data-ttu-id="4a8ac-187">\<--Bu öğe. on dört karakter--></span><span class="sxs-lookup"><span data-stu-id="4a8ac-187">\<--Fourteen chars in this element.--></span></span>|<span data-ttu-id="4a8ac-188">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="4a8ac-188">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="4a8ac-189">\<Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-189">\<Item></span></span>|<span data-ttu-id="4a8ac-190">\<Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-190">\<Item></span></span>|<span data-ttu-id="4a8ac-191">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="4a8ac-191">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="4a8ac-192">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="4a8ac-192">1234567890ABCD</span></span>|<span data-ttu-id="4a8ac-193">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="4a8ac-193">1234567890ABCD</span></span>|<span data-ttu-id="4a8ac-194">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="4a8ac-194">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="4a8ac-195">\</ Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-195">\</Item></span></span>|<span data-ttu-id="4a8ac-196">\</ Öğesi ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-196">\</Item></span></span>|<span data-ttu-id="4a8ac-197">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="4a8ac-197">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="4a8ac-198">\</ Öğeler ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-198">\</Items></span></span>|<span data-ttu-id="4a8ac-199">\</ Öğeler ></span><span class="sxs-lookup"><span data-stu-id="4a8ac-199">\</Items></span></span>|<span data-ttu-id="4a8ac-200">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="4a8ac-200">XmlNodeType.EndElement</span></span>|  
  
 <span data-ttu-id="4a8ac-201">Düğüm türüne atanan bilmeniz gerekir, düğüm olarak türü Eylemler ne tür geçerli olduğunu ve ne tür bir ayarlayın ve alma özellikleri denetler.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-201">You must know what node type is assigned, as the node type controls what kinds of actions are valid and what kind of properties you can set and retrieve.</span></span>  
  
 <span data-ttu-id="4a8ac-202">Boşluk düğüm oluşturma, verileri içine DOM tarafından yüklendiğinde denetlenir **PreserveWhitespace** bayrağı.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-202">Node creation for white space is controlled when the data is loaded into the DOM by the **PreserveWhitespace** flag.</span></span> <span data-ttu-id="4a8ac-203">Daha fazla bilgi için [boşluk ve önemli boşluk DOM yüklerken işleme](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="4a8ac-203">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>  
  
 <span data-ttu-id="4a8ac-204">DOM'da yeni düğümler eklemek için bkz [bir XML belgesine düğüm ekleme](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="4a8ac-204">To add new nodes to the DOM, see [Inserting Nodes into an XML Document](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span></span> <span data-ttu-id="4a8ac-205">DOM'dan düğümleri kaldırma için bkz: [düğümleri kaldırma, içerik ve değerleri XML belgesinden](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="4a8ac-205">To remove nodes from the DOM, see [Removing Nodes, Content, and Values from an XML Document](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span></span> <span data-ttu-id="4a8ac-206">DOM düğümleri içeriğini değiştirmek için bkz: [değiştirme düğümleri, içeriği ve değerleri bir XML belgesi](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="4a8ac-206">To modify the content of nodes in the DOM, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8ac-207">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4a8ac-207">See also</span></span>

- [<span data-ttu-id="4a8ac-208">XML Belge Nesne Modeli (DOM)</span><span class="sxs-lookup"><span data-stu-id="4a8ac-208">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
