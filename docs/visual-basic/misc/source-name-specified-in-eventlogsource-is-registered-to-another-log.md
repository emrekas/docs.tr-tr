---
title: EventLogSource içinde belirtilen kaynak adı EventLogName içinde belirtilen dışında bir günlüğe kaydedilir
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 4de98bef87b871036c3c5730ff09cf94c1df2918
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584577"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>EventLogSource içinde belirtilen kaynak adı EventLogName içinde belirtilen dışında bir günlüğe kaydedilir
`EventLog` Farklı günlüğe kaydedilen kaynağına başvurmak çalışıyor. Girişler için olay günlüğünü yazıyorsanız, belirtmeniz gerekir <xref:System.Diagnostics.EventLog.Source%2A> özelliği. <xref:System.Diagnostics.EventLog.Source%2A> Özelliği ile olay günlüğü bileşeniniz girişler geçerli bir kaynak kaydeder. Tek bir kaynak ile ilişkili (ve bu nedenle girişlere yazma) aynı anda yalnızca bir olay günlüğü.  
  
 Kaynak ile olay günlüğüne kaydeder ilk bileşen, system gibi geçerli bir kaynak olarak otomatik olarak kayıtlı olmayan bir giriş yazmak çalışırsanız, varsayılan olarak, değerini kullanarak <xref:System.Diagnostics.EventLog.Source%2A> özelliği olarak kaynak dizesi.  
  
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Kaynak doğru günlüğe kayıtlı olduğundan emin olun. Bunu yapmak için <xref:System.Diagnostics.EventLog.CreateEventSource%2A> yöntemi veya olay günlüğüne bileşeniniz benzersiz olarak tanımlayan bir dize belirtmek için bunun aşırı yüklerinden biri.  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Olay günlüklerini yönetme](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)
- [Olay günlüğü başvuruları](https://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)
- [Nasıl yapılır: Olay günlüğü girişleri kaynağı olarak uygulamanıza ekleme](https://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)
- [Nasıl yapılır: Olay kaynağını Kaldır](https://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
