---
title: Windows Forms'ta Olay İşleyicileri Oluşturma
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: e90e1d6643a30c1d2f4438e77317a2348b07fd71
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882419"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="435a7-102">Windows Forms'ta Olay İşleyicileri Oluşturma</span><span class="sxs-lookup"><span data-stu-id="435a7-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="435a7-103">Bir olay işleyicisi, hangi eylemlerin bir ileti kuyruğu bir ileti alır ya da kullanıcı bir düğmeyi tıkladığında gibi bir olay meydana gerçekleştirilen belirler, kodunuzda bir yordamdır.</span><span class="sxs-lookup"><span data-stu-id="435a7-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="435a7-104">Bir olay oluştuğunda, olay işleyicisi veya etkinliğin işleyicisi yürütülür.</span><span class="sxs-lookup"><span data-stu-id="435a7-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="435a7-105">Olaylar için birden fazla işleyici atanabilir ve belirli olayları işleyen yöntemleri dinamik olarak değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="435a7-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="435a7-106">Olay işleyicilerini oluşturma Visual Studio'da Windows Form Tasarımcısı ' de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="435a7-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="435a7-107">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="435a7-107">In This Section</span></span>

 <span data-ttu-id="435a7-108">[Olaylara genel bakış](events-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="435a7-108">[Events Overview](events-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="435a7-109">Olay modeli ve temsilciler rolünü açıklar.</span><span class="sxs-lookup"><span data-stu-id="435a7-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="435a7-110">[Olay işleyicilerine genel bakış](event-handlers-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="435a7-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="435a7-111">Olayların nasıl işleneceğini açıklar.</span><span class="sxs-lookup"><span data-stu-id="435a7-111">Describes how to handle events.</span></span>

 <span data-ttu-id="435a7-112">[Nasıl yapılır: Windows Forms için çalışma zamanında olay işleyicileri oluşturma](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="435a7-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span></span>
 <span data-ttu-id="435a7-113">Dinamik olarak sistem veya kullanıcı olaylarına yanıt için yönergeler sağlar.</span><span class="sxs-lookup"><span data-stu-id="435a7-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="435a7-114">[Nasıl yapılır: Windows Forms'ta tek olay işleyicisine birden fazla olay bağlama](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="435a7-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="435a7-115">Olaylar ile birden çok denetim aynı işlevselliği atamak için yönergeler sağlar.</span><span class="sxs-lookup"><span data-stu-id="435a7-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="435a7-116">[Windows Forms'ta olayların sırası](order-of-events-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="435a7-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="435a7-117">Windows Forms denetimlerinde olay oluşturulan sırasını anlatır.</span><span class="sxs-lookup"><span data-stu-id="435a7-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="435a7-118">[Nasıl yapılır: Tasarımcıyı kullanarak olay işleyicileri oluşturma](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) olay işleyicilerini oluşturma Windows Form Tasarımcısı'nı kullanmayı açıklar.</span><span class="sxs-lookup"><span data-stu-id="435a7-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="435a7-119">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="435a7-119">Related Sections</span></span>

 <span data-ttu-id="435a7-120">[Olayları](../../standard/events/index.md)\\</span><span class="sxs-lookup"><span data-stu-id="435a7-120">[Events](../../standard/events/index.md)\\</span></span>
 <span data-ttu-id="435a7-121">.NET Framework kullanarak olayları oluşturma ve işleme hakkında konulara bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="435a7-121">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="435a7-122">[Basic'de devralınmış olay işleyicileri Visual Basic sorunlarını giderme](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span><span class="sxs-lookup"><span data-stu-id="435a7-122">[Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span></span>
 <span data-ttu-id="435a7-123">Devralınan bileşenler olay işleyicileri ile oluşabilecek genel sorunları listeler.</span><span class="sxs-lookup"><span data-stu-id="435a7-123">Lists common issues that occur with event handlers in inherited components.</span></span>
