---
title: Bir XML Belgesindeki Ad Alanı Bildirimlerini Değiştirme
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a6b80a885f43facf4b3d4dd1dcb56d937d4f8de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669166"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Bir XML Belgesindeki Ad Alanı Bildirimlerini Değiştirme
**XmlDocument** ad alanı bildirimi gösterir ve **xmlns** belge nesne modeli bir parçası olarak öznitelikleri. Bunlar depolanır **XmlDocument**, belgeyi kaydettiğinizde, bu öznitelikleri konumunu koruyabilirsiniz. Bu öznitelikler değiştirme sahip herhangi bir etkisi **adı**, **namespaceURI**, ve **önek** diğer düğümlere ağacında özellikleri. Örneğin aşağıdaki belge yüklemek, sonra `test` öğesinin **namespaceURI** `123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 Kaldırırsanız `xmlns` özniteliğini aşağıdaki gibi ardından `test` hala öğesinin **namespaceURI** , `123`.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Benzer şekilde, farklı bir eklerseniz `xmlns` özniteliğini `doc` öğesi gösterildiği gibi ardından `test` hala öğesinin **namespaceURI** `123`.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Bu nedenle, değiştirme `xmlns` öznitelikleri, herhangi bir etkisi olacaktır, kaydedebilir ve yeniden kadar **XmlDocument** nesne.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [XML Belge Nesne Modeli (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
