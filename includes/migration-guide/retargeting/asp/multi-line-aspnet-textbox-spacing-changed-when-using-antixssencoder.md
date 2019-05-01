---
ms.openlocfilehash: e2bca42daebd25667ab2f312d5e59089b986503c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640082"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>AntiXSSEncoder kullanılırken çok satırlı ASP.Net TextBox boşluğu değiştirildi

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.0’da, <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name> kullanılırken geri göndermede çok satırlı metin kutularındaki satırların arasına ek satırlar ekleniyordu. .NET Framework 4.5’te, web uygulaması .NET Framework 4.5’i hedefliyorsa bu ek satır sonları eklenmez|
|Öneri|.NET Framework 4.5’e yeniden hedeflenen 4.0 web uygulamalarında, çok satırlı metin kutularının ek satır sonu eklenmeyecek şekilde geliştirilmiş olabileceğine dikkat edin. Bu istenmeyen bir durumsa, uygulama .NET Framework 4.5 üzerinde çalışırken .NET Framework 4.0 hedeflenerek eski davranışa dönülebilir.|
|Kapsam|İkincil|
|Sürüm|4,5|
|Tür|Yeniden Hedefleme|
