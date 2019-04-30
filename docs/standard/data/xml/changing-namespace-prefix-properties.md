---
title: Ad Alanı Ön Ek Özelliklerini Değiştirme
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a6597a3a57cd68c4dd17c4fbae882590f373709
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669153"
---
# <a name="changing-namespace-prefix-properties"></a><span data-ttu-id="9bb20-102">Ad Alanı Ön Ek Özelliklerini Değiştirme</span><span class="sxs-lookup"><span data-stu-id="9bb20-102">Changing Namespace Prefix Properties</span></span>
<span data-ttu-id="9bb20-103">**XmlNode** sınıfı belirli bir düğümle ilişkili ad alanı öneki değiştirmenize izin verir.</span><span class="sxs-lookup"><span data-stu-id="9bb20-103">The **XmlNode** class allows you to change the namespace prefix associated with a given node.</span></span> <span data-ttu-id="9bb20-104">Örneğin, aşağıdaki kod, değişmekte olan bir öğenin ön ek gösterir.</span><span class="sxs-lookup"><span data-stu-id="9bb20-104">For example, the following code shows the prefix of an element being changed.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="9bb20-105">**Output**</span><span class="sxs-lookup"><span data-stu-id="9bb20-105">**Output**</span></span>  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 <span data-ttu-id="9bb20-106">Bir düğümün önek değiştirme, ad alanı değiştirmez.</span><span class="sxs-lookup"><span data-stu-id="9bb20-106">Changing the prefix of a node does not change its namespace.</span></span> <span data-ttu-id="9bb20-107">Ad alanı, yalnızca düğüm oluşturulduğunda ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="9bb20-107">The namespace can only be set when the node is created.</span></span> <span data-ttu-id="9bb20-108">Ağaç kalıcı, yeni ad alanı öznitelikleri kullanıma ayarladığınız ön ekini karşılamak için kalıcı.</span><span class="sxs-lookup"><span data-stu-id="9bb20-108">When you persist the tree, new namespace attributes may be persisted out to satisfy the prefix you set.</span></span> <span data-ttu-id="9bb20-109">Yeni ad alanı oluşturulamazsa önek yerel adı ve ad alanı düğümü korur şekilde değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="9bb20-109">If the new namespace cannot be created, then the prefix is changed so the node preserves its local name and namespace.</span></span> <span data-ttu-id="9bb20-110">Aşağıdaki örnek, eklenen bir ad alanı özniteliği gösterir.</span><span class="sxs-lookup"><span data-stu-id="9bb20-110">The following example shows a namespace attribute being added.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="9bb20-111">**Output**</span><span class="sxs-lookup"><span data-stu-id="9bb20-111">**Output**</span></span>  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 <span data-ttu-id="9bb20-112">Ne zaman ağaç kalıcı bir dizeye çağrısının sonucunda **belge. Sınıfının InnerXml**, `xmlns:a='123'` öznitelik ad alanı korumak için eklenen `test` öğesi.</span><span class="sxs-lookup"><span data-stu-id="9bb20-112">When the tree was persisted to a string as a result of the call to **doc.InnerXml**, the `xmlns:a='123'` attribute was added to preserve the namespace of the `test` element.</span></span> <span data-ttu-id="9bb20-113">Bu `'123'`, ve onu kaldığını `'123'`.</span><span class="sxs-lookup"><span data-stu-id="9bb20-113">It was `'123'`, and it remained `'123'`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bb20-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9bb20-114">See also</span></span>

- [<span data-ttu-id="9bb20-115">XML Belge Nesne Modeli (DOM)</span><span class="sxs-lookup"><span data-stu-id="9bb20-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
