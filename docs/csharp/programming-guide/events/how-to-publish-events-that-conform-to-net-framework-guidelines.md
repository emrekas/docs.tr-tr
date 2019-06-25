---
title: 'Nasıl yapılır: -.NET Framework yönergeleriyle uyumlu olayları yayımlama C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 8af6d7d91efef81569e6f783352ec89d260cdd13
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347595"
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a><span data-ttu-id="925ab-102">Nasıl yapılır: .NET Framework yönergeleriyle uyumlu olayları yayımlama (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="925ab-102">How to: Publish Events that Conform to .NET Framework Guidelines (C# Programming Guide)</span></span>
<span data-ttu-id="925ab-103">Aşağıdaki yordam, sınıflar ve yapılar için standart .NET Framework desenini izler olaylar ekleme göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="925ab-103">The following procedure demonstrates how to add events that follow the standard .NET Framework pattern to your classes and structs.</span></span> <span data-ttu-id="925ab-104">.NET Framework Sınıf Kitaplığı'nda tüm olayları dayalı <xref:System.EventHandler> temsilci, olduğu gibi tanımlanır:</span><span class="sxs-lookup"><span data-stu-id="925ab-104">All events in the .NET Framework class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>  
  
```csharp  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  <span data-ttu-id="925ab-105">Bu temsilcinin genel bir sürümü .NET Framework 2.0 tanıtır <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="925ab-105">The .NET Framework 2.0 introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="925ab-106">Aşağıdaki örnekler, iki sürümünü kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="925ab-106">The following examples show how to use both versions.</span></span>  
  
 <span data-ttu-id="925ab-107">Tüm geçerli temsilci türünde, bir değer döndürmesi bile temsilciler tanımladığınız sınıflarda olayları temel alabilir ancak genellikle kullanarak, .NET Framework desen olaylarınızı temel önerilir <xref:System.EventHandler>, aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="925ab-107">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the .NET Framework pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>  
  
### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="925ab-108">EventHandler deseni temel alınarak olayları yayımlamak için</span><span class="sxs-lookup"><span data-stu-id="925ab-108">To publish events based on the EventHandler pattern</span></span>  
  
1. <span data-ttu-id="925ab-109">(Adım 3a özel verilerle olayınızı göndermek yoksa gidin ve bu adımı atlayın.) Bir kapsamda yayımcısı ve abonesi sınıfların görebildiği özel verileriniz için sınıf bildirme.</span><span class="sxs-lookup"><span data-stu-id="925ab-109">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="925ab-110">Ardından, özel olay verisini tutmak için gerekli üyeleri ekleyin.</span><span class="sxs-lookup"><span data-stu-id="925ab-110">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="925ab-111">Bu örnekte, basit bir dize döndürülür.</span><span class="sxs-lookup"><span data-stu-id="925ab-111">In this example, a simple string is returned.</span></span>  
  
    ```csharp  
    public class CustomEventArgs : EventArgs  
    {  
        public CustomEventArgs(string s)  
        {  
            msg = s;  
        }  
        private string msg;  
        public string Message  
        {  
            get { return msg; }  
        }   
    }  
    ```  
  
2. <span data-ttu-id="925ab-112">(Genel sürümünü kullanıyorsanız bu adımı atlayın <xref:System.EventHandler%601> .) Yayımlama sınıfınızın bir Temsilcide bildirin.</span><span class="sxs-lookup"><span data-stu-id="925ab-112">(Skip this step if you are using the generic version of <xref:System.EventHandler%601> .) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="925ab-113">İle biten bir ad verin *EventHandler*.</span><span class="sxs-lookup"><span data-stu-id="925ab-113">Give it a name that ends with *EventHandler*.</span></span> <span data-ttu-id="925ab-114">İkinci parametresi, özel, EventArgs türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="925ab-114">The second parameter specifies your custom EventArgs type.</span></span>  
  
    ```csharp  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3. <span data-ttu-id="925ab-115">Olay yayımlama sınıfınızda, aşağıdaki adımlardan birini kullanarak bildirin.</span><span class="sxs-lookup"><span data-stu-id="925ab-115">Declare the event in your publishing class by using one of the following steps.</span></span>  
  
    1. <span data-ttu-id="925ab-116">Özel bir EventArgs sınıf varsa, genel olmayan EventHandler temsilci olay türünüz olacaktır.</span><span class="sxs-lookup"><span data-stu-id="925ab-116">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="925ab-117">Zaten içinde bildirildiği için temsilci bildirmenize gerek olmayan <xref:System> C# projesi oluşturduğunuzda, dahil edilen ad alanı.</span><span class="sxs-lookup"><span data-stu-id="925ab-117">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="925ab-118">Yayımcı sınıfa aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="925ab-118">Add the following code to your publisher class.</span></span>  
  
        ```csharp  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2. <span data-ttu-id="925ab-119">Genel olmayan sürümünü kullanıyorsanız <xref:System.EventHandler> ve türetilen özel bir sınıf sahip <xref:System.EventArgs>, yayımlama, sınıf içinde olay bildirmek ve 2. adımda, bir temsilci türü olarak kullanın.</span><span class="sxs-lookup"><span data-stu-id="925ab-119">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>  
  
        ```csharp  
        public event CustomEventHandler RaiseCustomEvent;  
        ```  
  
    3. <span data-ttu-id="925ab-120">Genel sürüm kullanıyorsanız, özel bir temsilci ihtiyacınız yoktur.</span><span class="sxs-lookup"><span data-stu-id="925ab-120">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="925ab-121">Bunun yerine, yayımlama sınıfınızda, olay türü olarak belirttiğiniz `EventHandler<CustomEventArgs>`, açılı ayraçlar arasında kendi sınıfının adı değiştirme.</span><span class="sxs-lookup"><span data-stu-id="925ab-121">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>  
  
        ```csharp  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## <a name="example"></a><span data-ttu-id="925ab-122">Örnek</span><span class="sxs-lookup"><span data-stu-id="925ab-122">Example</span></span>  
 <span data-ttu-id="925ab-123">Aşağıdaki örnek, özel bir EventArgs sınıfını kullanarak önceki adımları göstermektedir ve <xref:System.EventHandler%601> olay türü.</span><span class="sxs-lookup"><span data-stu-id="925ab-123">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>  
  
 [!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="925ab-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="925ab-124">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="925ab-125">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="925ab-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="925ab-126">Olaylar</span><span class="sxs-lookup"><span data-stu-id="925ab-126">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="925ab-127">Temsilciler</span><span class="sxs-lookup"><span data-stu-id="925ab-127">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
