---
ms.openlocfilehash: 284a578a732096e3081321342e37c0a59b46f6cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234532"
---
### <a name="xmlwriter-throws-on-invalid-surrogate-pairs"></a>Geçersiz yedek çiftler hakkında XmlWriter oluşturur

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.5.2 veya önceki sürümlerini hedefleyen uygulamalar için özel durum geri dönüş işleme kullanarak her zaman bir özel durum oluşturmaz geçersiz yedek çifti yazma. .NET Framework 4.6 hedefleyen uygulamalar için geçersiz bir yedek çifti oluşturur yazma girişimi bir <xref:System.ArgumentException?displayProperty=name>.|
|Öneri|Gerekirse, bu kesme .NET Framework 4.5.2 hedefleyerek hükümsüz kılınan veya önceki bir sürümü olabilir. Alternatif olarak, geçersiz yedek çiftler halinde bunları yazmadan önce geçerli xml önceden işlenmiş olabilir.|
|Kapsam|Kenar|
|Sürüm|4.6|
|Tür|Yeniden Hedefleme|
|Etkilenen API’ler|<ul><li><xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteAttributeStringAsync(System.String,System.String,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteCData(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteCDataAsync(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteChars(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteCharsAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteComment(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteCommentAsync(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteEntityRef(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteEntityRefAsync(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteRaw(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteProcessingInstruction(System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteProcessingInstructionAsync(System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteRaw(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteRawAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteRawAsync(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteString(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteStringAsync(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteSurrogateCharEntity(System.Char,System.Char)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteSurrogateCharEntityAsync(System.Char,System.Char)?displayProperty=nameWithType></li><li><xref:System.Xml.XmlWriter.WriteValue(System.String)?displayProperty=nameWithType></li></ul>|
