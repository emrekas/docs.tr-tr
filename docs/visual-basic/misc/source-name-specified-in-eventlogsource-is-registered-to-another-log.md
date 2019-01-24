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
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a><span data-ttu-id="734fa-102">EventLogSource içinde belirtilen kaynak adı EventLogName içinde belirtilen dışında bir günlüğe kaydedilir</span><span class="sxs-lookup"><span data-stu-id="734fa-102">Source name specified in EventLogSource is registered to a log other than that specified in EventLogName</span></span>
<span data-ttu-id="734fa-103">`EventLog` Farklı günlüğe kaydedilen kaynağına başvurmak çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="734fa-103">The `EventLog` is attempting to refer to a source that is registered to a different log.</span></span> <span data-ttu-id="734fa-104">Girişler için olay günlüğünü yazıyorsanız, belirtmeniz gerekir <xref:System.Diagnostics.EventLog.Source%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="734fa-104">If you are writing entries to an event log, you must specify the <xref:System.Diagnostics.EventLog.Source%2A> property.</span></span> <span data-ttu-id="734fa-105"><xref:System.Diagnostics.EventLog.Source%2A> Özelliği ile olay günlüğü bileşeniniz girişler geçerli bir kaynak kaydeder.</span><span class="sxs-lookup"><span data-stu-id="734fa-105">The <xref:System.Diagnostics.EventLog.Source%2A> property registers your component with the event log as a valid source of entries.</span></span> <span data-ttu-id="734fa-106">Tek bir kaynak ile ilişkili (ve bu nedenle girişlere yazma) aynı anda yalnızca bir olay günlüğü.</span><span class="sxs-lookup"><span data-stu-id="734fa-106">A single source can be associated with (and therefore write entries to) only one event log at a time.</span></span>  
  
 <span data-ttu-id="734fa-107">Kaynak ile olay günlüğüne kaydeder ilk bileşen, system gibi geçerli bir kaynak olarak otomatik olarak kayıtlı olmayan bir giriş yazmak çalışırsanız, varsayılan olarak, değerini kullanarak <xref:System.Diagnostics.EventLog.Source%2A> özelliği olarak kaynak dizesi.</span><span class="sxs-lookup"><span data-stu-id="734fa-107">By default, if you try to write an entry without first having registered your component as a valid source, the system automatically registers the source with the event log, using the value of the <xref:System.Diagnostics.EventLog.Source%2A> property as the source string.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="734fa-108">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="734fa-108">To correct this error</span></span>  
  
-   <span data-ttu-id="734fa-109">Kaynak doğru günlüğe kayıtlı olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="734fa-109">Make sure the source is registered to the correct log.</span></span> <span data-ttu-id="734fa-110">Bunu yapmak için <xref:System.Diagnostics.EventLog.CreateEventSource%2A> yöntemi veya olay günlüğüne bileşeniniz benzersiz olarak tanımlayan bir dize belirtmek için bunun aşırı yüklerinden biri.</span><span class="sxs-lookup"><span data-stu-id="734fa-110">To do this, use the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method or one of its overloads to specify a string that uniquely identifies your component to the event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="734fa-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="734fa-111">See also</span></span>
- [<span data-ttu-id="734fa-112">Olay günlüklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="734fa-112">Administering Event Logs</span></span>](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)
- [<span data-ttu-id="734fa-113">Olay günlüğü başvuruları</span><span class="sxs-lookup"><span data-stu-id="734fa-113">Event Log References</span></span>](https://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)
- [<span data-ttu-id="734fa-114">Nasıl yapılır: Olay günlüğü girişleri kaynağı olarak uygulamanıza ekleme</span><span class="sxs-lookup"><span data-stu-id="734fa-114">How to: Add Your Application as a Source of Event Log Entries</span></span>](https://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)
- [<span data-ttu-id="734fa-115">Nasıl yapılır: Olay kaynağını Kaldır</span><span class="sxs-lookup"><span data-stu-id="734fa-115">How to: Remove an Event Source</span></span>](https://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
