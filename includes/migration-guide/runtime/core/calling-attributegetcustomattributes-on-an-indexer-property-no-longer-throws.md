---
ms.openlocfilehash: a3f54bec98f220af48e932e6485d06732a4c6ddd
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858838"
---
### <a name="calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>Dizinin türüyle belirsizlik çözümlenebiliyorsa AmbiguousMatchException Attribute.GetCustomAttributes bir dizin oluşturucu özelliği artık çağırma oluşturur

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.6, çağırma önce <code>GetCustomAttribute(s)</code> başka bir özelliği yalnızca dizin türüne göre farklıydı özelliği bir dizin oluşturucusunda neden olacağından bir <xref:System.Reflection.AmbiguousMatchException?displayProperty=name>. .NET Framework 4. 6 ' başlayarak, özelliğin özniteliklerini doğru bir şekilde döndürülür.|
|Öneri|GetCustomAttribute(s) daha sık artık çalışacağını unutmayın. Uygulama daha önce bağlı, <xref:System.Reflection.AmbiguousMatchException?displayProperty=name>, yansıma artık birden çok dizin oluşturucular için bunun yerine açıkça aramak için kullanılmalıdır.|
|`Scope`|Kenar|
|Version|4.6|
|Type|Çalışma zamanı|
|Etkilenen API’ler|<ul><li><xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li></ul>|

