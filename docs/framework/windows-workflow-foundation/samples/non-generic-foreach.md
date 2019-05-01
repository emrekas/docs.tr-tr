---
title: Genel Olmayan ForEach
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: 353128d1c313be62222e091c084e5b5e37a92b58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004919"
---
# <a name="non-generic-foreach"></a><span data-ttu-id="67e77-102">Genel Olmayan ForEach</span><span class="sxs-lookup"><span data-stu-id="67e77-102">Non-Generic ForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="67e77-103">kendi araç kutusunda etkinlikler, akış denetimi dahil olmak üzere bir dizi birlikte gelen <xref:System.Activities.Statements.ForEach%601>, üzerinden yineleme olanak tanıyan <xref:System.Collections.Generic.IEnumerable%601> koleksiyonları.</span><span class="sxs-lookup"><span data-stu-id="67e77-103">ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ForEach%601>, which allows iterating through <xref:System.Collections.Generic.IEnumerable%601> collections.</span></span>  
  
 <span data-ttu-id="67e77-104"><xref:System.Activities.Statements.ForEach%601> gerektirir, <xref:System.Activities.Statements.ForEach%601.Values%2A> türü özelliğini <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="67e77-104"><xref:System.Activities.Statements.ForEach%601> requires its <xref:System.Activities.Statements.ForEach%601.Values%2A> property to be of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="67e77-105">Bu kullanıcılar, uygulama veri yapıları üzerinde yineleme gelen ışığının <xref:System.Collections.Generic.IEnumerable%601> arabirimi (örneğin, <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="67e77-105">This precludes users from iterating over data structures that implement <xref:System.Collections.Generic.IEnumerable%601> interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="67e77-106">Genel olmayan sürümü <xref:System.Activities.Statements.ForEach%601> koleksiyonundaki değerleri türlerinin uyumluluğu sağlamaya yönelik daha fazla çalışma zamanı karmaşıklığı çoğaltamaz bu gereksinimi ortadan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="67e77-106">The non-generic version of <xref:System.Activities.Statements.ForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="67e77-107">Bu örnek, genel olmayan bir uygulama gösterilmektedir <xref:System.Activities.Statements.ForEach%601> etkinlik ve iş Tasarımcısı.</span><span class="sxs-lookup"><span data-stu-id="67e77-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ForEach%601> activity and its designer.</span></span> <span data-ttu-id="67e77-108">Bu etkinlik yinelemek için kullanılabilir <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="67e77-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="foreach-activity"></a><span data-ttu-id="67e77-109">ForEach etkinliği</span><span class="sxs-lookup"><span data-stu-id="67e77-109">ForEach Activity</span></span>  
 <span data-ttu-id="67e77-110">C# /VB `foreach` deyimi koleksiyonundaki her öğe için bir katıştırılmış deyim yürütülürken, bir koleksiyonun öğeleri sıralar.</span><span class="sxs-lookup"><span data-stu-id="67e77-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="67e77-111">[!INCLUDE[wf1](../../../../includes/wf1-md.md)] Eşdeğer etkinliklerini `foreach` olan <xref:System.Activities.Statements.ForEach%601> ve <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="67e77-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities of `foreach` are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="67e77-112"><xref:System.Activities.Statements.ForEach%601> Etkinlik değerleri ve gövde listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="67e77-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="67e77-113">Çalışma zamanında, listenin yinelenir ve listedeki her değerin gövdesi yürütülür.</span><span class="sxs-lookup"><span data-stu-id="67e77-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="67e77-114">Çoğu durumda, kullanılabilir ve derleme zamanında tür sağlar senaryoları çoğunu kapsar için etkinliğin genel sürüm tercih edilen bir çözüm olmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="67e77-114">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it would be used, and provides type checking at compile time.</span></span> <span data-ttu-id="67e77-115">Genel olmayan sürümü, genel olmayan uygulayan türler yineleme için kullanılabilir <xref:System.Collections.IEnumerable> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="67e77-115">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="67e77-116">Sınıf tanımı</span><span class="sxs-lookup"><span data-stu-id="67e77-116">Class Definition</span></span>  
 <span data-ttu-id="67e77-117">Aşağıdaki kod örneği, genel olmayan bir tanımı gösterilmektedir `ForEach` etkinlik.</span><span class="sxs-lookup"><span data-stu-id="67e77-117">The following code example shows the definition of a non-generic `ForEach` activity.</span></span>  
  
```  
[ContentProperty("Body")]  
public class ForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 <span data-ttu-id="67e77-118">Gövde (isteğe bağlı)</span><span class="sxs-lookup"><span data-stu-id="67e77-118">Body (optional)</span></span>  
 <span data-ttu-id="67e77-119"><xref:System.Activities.ActivityAction> Türü <xref:System.Object>, koleksiyondaki her öğe için gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="67e77-119">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="67e77-120">Her bağımsız öğede gövdesine geçirilir, `Argument` özelliği.</span><span class="sxs-lookup"><span data-stu-id="67e77-120">Each individual element is passed into the Body through its `Argument` property.</span></span>  
  
 <span data-ttu-id="67e77-121">Değer (isteğe bağlı)</span><span class="sxs-lookup"><span data-stu-id="67e77-121">Values (optional)</span></span>  
 <span data-ttu-id="67e77-122">Üzerinden yinelenir öğeleri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="67e77-122">The collection of elements that are iterated over.</span></span> <span data-ttu-id="67e77-123">Tüm koleksiyon öğelerini uyumlu bir tür olduğundan emin olmak için çalışma zamanında gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="67e77-123">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
## <a name="example-of-using-foreach"></a><span data-ttu-id="67e77-124">ForEach kullanma örneği</span><span class="sxs-lookup"><span data-stu-id="67e77-124">Example of Using ForEach</span></span>  
 <span data-ttu-id="67e77-125">Aşağıdaki kod ForEach etkinliği bir uygulamada kullanma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="67e77-125">The following code demonstrates how to use the ForEach activity in an application.</span></span>  
  
```  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ForEach  
    {  
       Values = new InArgument<IEnumerable>(c=> names),  
       Body = new ActivityAction<object>   
       {                          
           Argument = iterationVariable,  
           Handler = new WriteLine  
           {  
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))  
           }  
       }  
   };  
```  
  
|<span data-ttu-id="67e77-126">Koşul</span><span class="sxs-lookup"><span data-stu-id="67e77-126">Condition</span></span>|<span data-ttu-id="67e77-127">İleti</span><span class="sxs-lookup"><span data-stu-id="67e77-127">Message</span></span>|<span data-ttu-id="67e77-128">Önem Derecesi</span><span class="sxs-lookup"><span data-stu-id="67e77-128">Severity</span></span>|<span data-ttu-id="67e77-129">Özel Durum Türü</span><span class="sxs-lookup"><span data-stu-id="67e77-129">Exception Type</span></span>|  
|---------------|-------------|--------------|--------------------|  
|<span data-ttu-id="67e77-130">Değeri. `null`</span><span class="sxs-lookup"><span data-stu-id="67e77-130">Values is `null`</span></span>|<span data-ttu-id="67e77-131">Povinný argument 'Değerleri' için değer sağlanmadı.</span><span class="sxs-lookup"><span data-stu-id="67e77-131">Value for a required activity argument 'Values' was not supplied.</span></span>|<span data-ttu-id="67e77-132">Hata</span><span class="sxs-lookup"><span data-stu-id="67e77-132">Error</span></span>|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a><span data-ttu-id="67e77-133">ForEach Tasarımcısı</span><span class="sxs-lookup"><span data-stu-id="67e77-133">ForEach Designer</span></span>  
 <span data-ttu-id="67e77-134">Örnek etkinlik Tasarımcısı için yerleşik sağlanan Tasarımcı görünümü benzer <xref:System.Activities.Statements.ForEach%601> etkinlik.</span><span class="sxs-lookup"><span data-stu-id="67e77-134">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ForEach%601> activity.</span></span> <span data-ttu-id="67e77-135">Tasarımcı araç kutusunda görünür **örnekleri**, **genel olmayan etkinlikler** kategorisi.</span><span class="sxs-lookup"><span data-stu-id="67e77-135">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="67e77-136">Tasarımcı adlı **ForEachWithBodyFactory** Araç Kutusu'nda, etkinlik kullanıma sunduğundan bir <xref:System.Activities.Presentation.IActivityTemplateFactory> araç kutusunda oluşturan etkinliğin bir düzgün bir şekilde yapılandırılmış <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="67e77-136">The designer is named **ForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox, which creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```  
public sealed class ForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ForEach()  
        {  
            Body = new ActivityAction<object>()  
            {  
                Argument = new DelegateInArgument<object>()  
                {  
                    Name = "item"  
                }  
            }  
        };  
    }  
}  
```  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="67e77-137">Bu örneği çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="67e77-137">To run this sample</span></span>  
  
1. <span data-ttu-id="67e77-138">Seçtiğiniz proje, çözümün başlangıç projesi ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="67e77-138">Set the project of your choice as the start-up project of the solution:</span></span>  
  
    1. <span data-ttu-id="67e77-139">**CodeTestClient** kod kullanarak etkinliğini kullanma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="67e77-139">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2. <span data-ttu-id="67e77-140">**DesignerTestClient** etkinlik Tasarımcısı içinde kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="67e77-140">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2. <span data-ttu-id="67e77-141">Derleme ve projeyi çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="67e77-141">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="67e77-142">Örnekler, makinenizde zaten yüklü.</span><span class="sxs-lookup"><span data-stu-id="67e77-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="67e77-143">Devam etmeden önce şu (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="67e77-143">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="67e77-144">Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="67e77-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="67e77-145">Bu örnek, şu dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="67e77-145">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
