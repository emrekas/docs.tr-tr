---
title: Kesin kod temelli doğrulama
ms.date: 03/30/2017
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
ms.openlocfilehash: 333e1e200825dd1fc8ed750abbecbb309da66663
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707839"
---
# <a name="imperative-code-based-validation"></a><span data-ttu-id="c17f6-102">Kesin kod temelli doğrulama</span><span class="sxs-lookup"><span data-stu-id="c17f6-102">Imperative Code-Based Validation</span></span>

<span data-ttu-id="c17f6-103">Kesin kod temelli doğrulama doğrulama kendisi hakkında sağlamaya bir etkinlik için basit bir yol sağlar ve türetilen etkinlikler için kullanılabilir <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, ve <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="c17f6-103">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="c17f6-104">Herhangi bir doğrulama hataları veya uyarıları belirleyen bir doğrulama kodu etkinliğe eklenir.</span><span class="sxs-lookup"><span data-stu-id="c17f6-104">Validation code that determines any validation errors or warnings is added to the activity.</span></span>  
  
## <a name="using-code-based-validation"></a><span data-ttu-id="c17f6-105">Kod temelli doğrulama kullanma</span><span class="sxs-lookup"><span data-stu-id="c17f6-105">Using Code-Based Validation</span></span>

<span data-ttu-id="c17f6-106">Öğesinden türetilen etkinlikleri tarafından desteklenen kod temelli doğrulama <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, ve <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="c17f6-106">Code-based validation is supported by activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="c17f6-107">Doğrulama kodu yerleştirilebileceğini <xref:System.Activities.CodeActivity.CacheMetadata%2A> geçersiz kıl ve doğrulama hataları veya uyarılar, meta veri bağımsız değişkeni eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="c17f6-107">Validation code can be placed in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override, and validation errors or warnings can be added to the metadata argument.</span></span> <span data-ttu-id="c17f6-108">Aşağıdaki örnekte, `Cost` büyüktür `Price`, meta veriler için bir doğrulama hatası eklenir.</span><span class="sxs-lookup"><span data-stu-id="c17f6-108">In the following example, if the `Cost` is greater than the `Price`, a validation error is added to the metadata.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c17f6-109">Unutmayın `Cost` ve `Price` etkinlik bağımsız değişkenleri değildir, ancak tasarım zamanında ayarlanır özelliklerdir.</span><span class="sxs-lookup"><span data-stu-id="c17f6-109">Note that `Cost` and `Price` are not arguments to the activity, but are properties that are set at design time.</span></span> <span data-ttu-id="c17f6-110">Diğer bir deyişle neden değerleri olarak doğrulanabilmesi <xref:System.Activities.CodeActivity.CacheMetadata%2A> geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="c17f6-110">That is why their values can be validated in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="c17f6-111">Veri çalışma zamanına kadar akışı değil, ancak etkinlik bağımsız değişkenleri doğrulanmış bunlar kullanarak bağlı olmadığından emin olmak için tasarım zamanında bir bağımsız değişken akan veri değeri doğrulanamıyor `RequiredArgument` özniteliği ve grupları aşırı yükleme.</span><span class="sxs-lookup"><span data-stu-id="c17f6-111">The value of the data flowing through an argument cannot be validated at design time because the data does not flow until run time, but activity arguments can be validated to ensure that they are bound by using the `RequiredArgument` attribute and overload groups.</span></span> <span data-ttu-id="c17f6-112">Bu kod örneği görür `RequiredArgument` özniteliğini `Description` bağımsız değişken, bağlı değil sonra bir doğrulama hatası oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c17f6-112">This example code sees the `RequiredArgument` attribute for the `Description` argument, and if it is not bound then a validation error is generated.</span></span> <span data-ttu-id="c17f6-113">Gerekli bağımsız değişken içinde ele alınmıştır [gerekli bağımsız değişkenler ve aşırı grupları](required-arguments-and-overload-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c17f6-113">Required arguments are covered in [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md).</span></span>  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error   
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 <span data-ttu-id="c17f6-114">Varsayılan olarak, meta veriler için bir doğrulama hatası eklenir, <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> çağrılır.</span><span class="sxs-lookup"><span data-stu-id="c17f6-114">By default, a validation error is added to the metadata when <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> is called.</span></span> <span data-ttu-id="c17f6-115">Doğrulama uyarısı eklemek için <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> alan aşırı yüklemesini bir <xref:System.Activities.Validation.ValidationError>, belirleyen <xref:System.Activities.Validation.ValidationError> ayarlayarak bir uyarı temsil <xref:System.Activities.Validation.ValidationError.IsWarning%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="c17f6-115">To add a validation warning, use the <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> overload that takes a <xref:System.Activities.Validation.ValidationError>, and specify that the <xref:System.Activities.Validation.ValidationError> represents a warning by setting the <xref:System.Activities.Validation.ValidationError.IsWarning%2A> property.</span></span>  
  
 <span data-ttu-id="c17f6-116">Bir iş akışı iş akışı Tasarımcısı'nda değiştirilir ve herhangi bir doğrulama hataları veya uyarıları iş akışı Tasarımcısı'nda görüntülenen doğrulama gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="c17f6-116">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="c17f6-117">Doğrulama iş akışı çağrıldığında ve herhangi bir doğrulama hatası meydana gelirse, çalışma zamanında da oluşur bir <xref:System.Activities.InvalidWorkflowException> varsayılan Doğrulama mantığı tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c17f6-117">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> <span data-ttu-id="c17f6-118">Doğrulama uyarıları veya hataları erişmek ve doğrulamayı çağırma hakkında daha fazla bilgi için bkz. [etkinlik doğrulamayı çağırma](invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="c17f6-118">For more information about invoking validation and accessing any validation warnings or errors, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>  
  
 <span data-ttu-id="c17f6-119">Şuradan oluşturulduğu özel durumları <xref:System.Activities.CodeActivity.CacheMetadata%2A> doğrulama hataları değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="c17f6-119">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="c17f6-120">Bu özel durumlar çağrısından kaçış <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> ve çağıran tarafından ele alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="c17f6-120">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
 <span data-ttu-id="c17f6-121">Kod temelli doğrulama kodu içeren etkinlik doğrulamak için yararlıdır, ancak diğer etkinliklere görünürlük iş akışı içinde yok.</span><span class="sxs-lookup"><span data-stu-id="c17f6-121">Code-based validation is useful for validating the activity that contains the code, but it does not have visibility into the other activities in the workflow.</span></span> <span data-ttu-id="c17f6-122">Bildirim temelli kısıtlamalar doğrulama etkinlik diğer etkinlikler iş akışı ile arasındaki ilişkileri validate olanağı sağlar ve ele alınmıştır [bildirim temelli kısıtlamalar](declarative-constraints.md) konu.</span><span class="sxs-lookup"><span data-stu-id="c17f6-122">Declarative constraints validation provides the ability to validate the relationships between an activity and other activities in the workflow, and is covered in the [Declarative Constraints](declarative-constraints.md) topic.</span></span>
