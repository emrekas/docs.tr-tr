---
title: Değişkenler ve Bağımsız Değişkenler
ms.date: 03/30/2017
ms.assetid: d03dbe34-5b2e-4f21-8b57-693ee49611b8
ms.openlocfilehash: 29ce5222435b68ed13cbc967e58e72a937625e8e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320749"
---
# <a name="variables-and-arguments"></a><span data-ttu-id="aaf5e-102">Değişkenler ve Bağımsız Değişkenler</span><span class="sxs-lookup"><span data-stu-id="aaf5e-102">Variables and Arguments</span></span>
<span data-ttu-id="aaf5e-103">Windows Workflow Foundation (WF) değişkenleri temsil eden veri depolama ve küme içi ve dışı bir etkinlik bağımsız değişkenleri veri akışını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-103">In Windows Workflow Foundation (WF), variables represent the storage of data and arguments represent the flow of data into and out of an activity.</span></span> <span data-ttu-id="aaf5e-104">Bağımsız değişken kümesinin bir etkinlik içerir ve bunlar etkinlik imzasını yapın.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-104">An activity has a set of arguments and they make up the signature of the activity.</span></span> <span data-ttu-id="aaf5e-105">Ayrıca, bir etkinlik bir geliştirici ekleyebilir veya değişkenleri bir iş akışı tasarım sırasında kaldırma değişkenler listesini sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-105">Additionally, an activity can maintain a list of variables to which a developer can add or remove variables during the design of a workflow.</span></span> <span data-ttu-id="aaf5e-106">Bağımsız değişken bir değer döndüren bir ifade kullanarak bağlanır.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-106">An argument is bound using an expression that returns a value.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="aaf5e-107">Değişkenler</span><span class="sxs-lookup"><span data-stu-id="aaf5e-107">Variables</span></span>  
 <span data-ttu-id="aaf5e-108">Veri depolama konumları değişkenlerdir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-108">Variables are storage locations for data.</span></span> <span data-ttu-id="aaf5e-109">Değişkenleri, bir iş akışının tanımını bir parçası olarak belirtilir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-109">Variables are declared as part of the definition of a workflow.</span></span> <span data-ttu-id="aaf5e-110">Değişken değerleri çalışma zamanında alır ve bu değerleri bir iş akışı örneği durumu bir parçası olarak depolanır.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-110">Variables take on values at runtime and these values are stored as part of the state of a workflow instance.</span></span> <span data-ttu-id="aaf5e-111">Değişken bir tanım değişkenini ve isteğe bağlı olarak ad türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-111">A variable definition specifies the type of the variable and optionally, the name.</span></span> <span data-ttu-id="aaf5e-112">Aşağıdaki kodu kullanarak bir değere bir değişken, Ata bildirmek gösterilmiştir bir <xref:System.Activities.Statements.Assign%601> etkinlik ve ardından Konsolu kullanarak değerinin görüntülendiğini bir <xref:System.Activities.Statements.WriteLine> etkinlik.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-112">The following code shows how to declare a variable, assign a value to it using an <xref:System.Activities.Statements.Assign%601> activity, and then display its value to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
```csharp  
// Define a variable named "str" of type string.  
Variable<string> var = new Variable<string>  
{  
    Name = "str"  
};  
  
// Declare the variable within a Sequence, assign  
// a value to it, and then display it.  
Activity wf = new Sequence()  
{  
    Variables = { var },  
    Activities =  
    {  
        new Assign<string>  
        {  
            To = var,  
            Value = "Hello World."  
        },  
        new WriteLine  
        {  
            Text = var  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 <span data-ttu-id="aaf5e-113">Varsayılan değer ifadesi bir değişken bildirimi bir parçası olarak isteğe bağlı olarak belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-113">A default value expression can optionally be specified as part of a variable declaration.</span></span> <span data-ttu-id="aaf5e-114">Değişkenleri de değiştiricilere sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-114">Variables also can have modifiers.</span></span> <span data-ttu-id="aaf5e-115">Örneğin, bir değişken salt okunur ise ardından salt okunur <xref:System.Activities.VariableModifiers> değiştiricisi uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-115">For example, if a variable is read-only then the read-only <xref:System.Activities.VariableModifiers> modifier can be applied.</span></span> <span data-ttu-id="aaf5e-116">Aşağıdaki örnekte, atanmış bir varsayılan değere sahip bir salt okunur değişken oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-116">In the following example, a read-only variable is created that has a default value assigned.</span></span>  
  
```csharp  
// Define a read-only variable with a default value.  
Variable<string> var = new Variable<string>  
{  
    Default = "Hello World.",  
    Modifiers = VariableModifiers.ReadOnly  
};  
```  
  
## <a name="variable-scoping"></a><span data-ttu-id="aaf5e-117">Değişken kapsamı</span><span class="sxs-lookup"><span data-stu-id="aaf5e-117">Variable Scoping</span></span>  
 <span data-ttu-id="aaf5e-118">Çalışma zamanında bir değişkenin ömrü, onu bildiren etkinlik ömrünü eşittir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-118">The lifetime of a variable at runtime is equal to the lifetime of the activity that declares it.</span></span> <span data-ttu-id="aaf5e-119">Bir etkinlik tamamlandığında değişkenlerini temizlenir ve artık başvurulabilir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-119">When an activity completes, its variables are cleaned up and can no longer be referenced.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="aaf5e-120">Arguments</span><span class="sxs-lookup"><span data-stu-id="aaf5e-120">Arguments</span></span>  
 <span data-ttu-id="aaf5e-121">Etkinlik yazarlar şekilde verileri tanımlamak için bağımsız değişkenler kullanın içine ve dışına Etkinlik Akışları.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-121">Activity authors use arguments to define the way data flows into and out of an activity.</span></span> <span data-ttu-id="aaf5e-122">Belirtilen yönde her bağımsız değişkenlere sahiptir: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out>, veya <xref:System.Activities.ArgumentDirection.InOut>.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-122">Each argument has a specified direction: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out>, or <xref:System.Activities.ArgumentDirection.InOut>.</span></span>  
  
 <span data-ttu-id="aaf5e-123">İş akışı çalışma zamanı veri taşıma içine ve dışına etkinlikleri zamanlaması hakkında aşağıdakileri garantiler:</span><span class="sxs-lookup"><span data-stu-id="aaf5e-123">The workflow runtime makes the following guarantees about the timing of data movement into and out of activities:</span></span>  
  
1. <span data-ttu-id="aaf5e-124">Bir etkinlik yürütme başlatıldığında, tüm giriş ve giriş/çıkış bağımsız değişkenlerinin değerlerini hesaplanır.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-124">When an activity starts executing, the values of all of its input and input/output arguments are calculated.</span></span> <span data-ttu-id="aaf5e-125">Örneğin, ne zaman bakılmaksızın <xref:System.Activities.Argument.Get%2A> olan adlı bir hesaplanır kendi çağrılmasına önce çalışma zamanı tarafından döndürülen değer `Execute`.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-125">For example, regardless of when <xref:System.Activities.Argument.Get%2A> is called, the value returned is the one calculated by the runtime prior to its invocation of `Execute`.</span></span>  
  
2. <span data-ttu-id="aaf5e-126">Zaman <xref:System.Activities.InOutArgument%601.Set%2A> olan çağrılır, hemen değeri çalışma zamanı ayarlar.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-126">When <xref:System.Activities.InOutArgument%601.Set%2A> is called, the runtime sets the value immediately.</span></span>  
  
3. <span data-ttu-id="aaf5e-127">Bağımsız değişken isteğe bağlı olarak olabilir, <xref:System.Activities.Argument.EvaluationOrder%2A> belirtilen.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-127">Arguments can optionally have their <xref:System.Activities.Argument.EvaluationOrder%2A> specified.</span></span> <xref:System.Activities.Argument.EvaluationOrder%2A> <span data-ttu-id="aaf5e-128">bağımsız değişken değerlendirilme sırasını belirleyen sıfır tabanlı bir değerdir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-128">is a zero-based value that specifies the order in which the argument is evaluated.</span></span> <span data-ttu-id="aaf5e-129">Varsayılan olarak, değerlendirme sırasında bağımsız değişken belirtilmezse ve eşittir <xref:System.Activities.Argument.UnspecifiedEvaluationOrder> değeri.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-129">By default, the evaluation order of the argument is unspecified and is equal to the <xref:System.Activities.Argument.UnspecifiedEvaluationOrder> value.</span></span> <span data-ttu-id="aaf5e-130">Ayarlama <xref:System.Activities.Argument.EvaluationOrder%2A> büyük veya bu bağımsız değişken için bir değerlendirme sırasını belirlemek için sıfıra eşit bir değer.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-130">Set <xref:System.Activities.Argument.EvaluationOrder%2A> to a value greater or equal to zero to specify an evaluation order for this argument.</span></span> <span data-ttu-id="aaf5e-131">Windows Workflow Foundation bir belirtilen değerlendirme sırası artan düzende bağımsız değişken değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-131">Windows Workflow Foundation evaluates arguments with a specified evaluation order in ascending order.</span></span> <span data-ttu-id="aaf5e-132">Bağımsız değişkenlerle bir belirtilmeyen Değerlendirme sırasını belirtilen değerlendirme sırası olanlardan önce değerlendirildiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-132">Note that arguments with an unspecified evaluation order are evaluated before those with a specified evaluation order.</span></span>  
  
 <span data-ttu-id="aaf5e-133">Bir etkinlik Yazar bağımsız değişkenlerinden açığa çıkarmak için kesin türü belirtilmiş bir mekanizma kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-133">An activity author can use a strongly-typed mechanism for exposing its arguments.</span></span> <span data-ttu-id="aaf5e-134">Bu türün özelliklerini bildirerek gerçekleştirilir <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, ve <xref:System.Activities.InOutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-134">This is accomplished by declaring properties of type <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, and <xref:System.Activities.InOutArgument%601>.</span></span> <span data-ttu-id="aaf5e-135">Bu, küme içi ve dışı bir etkinlik giden verileri hakkında belirli bir sözleşme'kurmak bir etkinlik Yazar sağlar.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-135">This allows an activity author to establish a specific contract about the data going into and out of an activity.</span></span>  
  
### <a name="defining-the-arguments-on-an-activity"></a><span data-ttu-id="aaf5e-136">Bir etkinlik bağımsız değişkenleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="aaf5e-136">Defining the Arguments on an Activity</span></span>  
 <span data-ttu-id="aaf5e-137">Bağımsız değişkenler tanımlanabilir bir etkinlik türünün özelliklerini belirterek <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, ve <xref:System.Activities.InOutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-137">Arguments can be defined on an activity by specifying properties of type <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, and <xref:System.Activities.InOutArgument%601>.</span></span> <span data-ttu-id="aaf5e-138">Aşağıdaki kod, bağımsız değişkenleri tanımlamak gösterilmiştir bir `Prompt` etkinliği kullanıcıya göstermek için bir dize alır ve kullanıcının yanıt içeren bir dize döndürür.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-138">The following code shows how to define the arguments for a `Prompt` activity that takes in a string to display to the user and returns a string that contains the user's response.</span></span>  
  
```csharp  
public class Prompt : Activity  
{  
    public InArgument<string> Text { get; set; }  
    public OutArgument<string> Response { get; set; }  
    // Rest of activity definition omitted.  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="aaf5e-139">Tek bir değer döndürmesi etkinlikleri türeyebilir <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601>, veya <xref:System.Activities.CodeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-139">Activities that return a single value can derive from <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601>, or <xref:System.Activities.CodeActivity%601>.</span></span> <span data-ttu-id="aaf5e-140">Bu etkinlikler, iyi tanımlanmış olması <xref:System.Activities.OutArgument%601> adlı <xref:System.Activities.Activity%601.Result%2A> , etkinliğin dönüş değerini içerir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-140">These activities have a well-defined <xref:System.Activities.OutArgument%601> named <xref:System.Activities.Activity%601.Result%2A> that contains the return value of the activity.</span></span>  
  
### <a name="using-variables-and-arguments-in-workflows"></a><span data-ttu-id="aaf5e-141">İş akışlarında değişkenler ve bağımsız değişkenleri kullanma</span><span class="sxs-lookup"><span data-stu-id="aaf5e-141">Using Variables and Arguments in Workflows</span></span>  
 <span data-ttu-id="aaf5e-142">Aşağıdaki örnek, değişkenler ve bağımsız değişkenleri bir iş akışında nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-142">The following example shows how variables and arguments are used in a workflow.</span></span> <span data-ttu-id="aaf5e-143">İş akışı üç değişkenler bildirilmektedir dizisidir: `var1`, `var2`, ve `var3`.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-143">The workflow is a sequence that declares three variables: `var1`, `var2`, and `var3`.</span></span> <span data-ttu-id="aaf5e-144">İlk etkinlik iş akışında bir `Assign` değişkeninin değeri atar etkinlik `var1` değişkenine `var2`.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-144">The first activity in the workflow is an `Assign` activity that assigns the value of variable `var1` to the variable `var2`.</span></span> <span data-ttu-id="aaf5e-145">Bu takip bir `WriteLine` değerini yazdırır etkinlik `var2` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-145">This is followed by a `WriteLine` activity that prints the value of the `var2` variable.</span></span> <span data-ttu-id="aaf5e-146">Başka bir sonraki olduğu `Assign` değişkeninin değeri atar etkinlik `var2` değişkenine `var3`.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-146">Next is another `Assign` activity that assigns the value of variable `var2` to the variable `var3`.</span></span> <span data-ttu-id="aaf5e-147">Son olarak yoktur başka `WriteLine` değerini yazdırır etkinlik `var3` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-147">Finally there is another `WriteLine` activity that prints the value of the `var3` variable.</span></span> <span data-ttu-id="aaf5e-148">İlk `Assign` etkinliği kullanan `InArgument<string>` ve `OutArgument<string>` bağlamaları etkinliğe ilişkin bağımsız değişkenler için açıkça temsil eden nesneleri.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-148">The first `Assign` activity uses `InArgument<string>` and `OutArgument<string>` objects that explicitly represent the bindings for the activity's arguments.</span></span> `InArgument<string>` <span data-ttu-id="aaf5e-149">için kullanılan <xref:System.Activities.Statements.Assign.Value%2A> değeri içine akar çünkü <xref:System.Activities.Statements.Assign%601> etkinlik aracılığıyla kendi <xref:System.Activities.Statements.Assign.Value%2A> bağımsız değişkeni, ve `OutArgument<string>` için kullanılan <xref:System.Activities.Statements.Assign.To%2A> değeri tanesi akan çünkü <xref:System.Activities.Statements.Assign.To%2A> bağımsız değişkeni olarak.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-149">is used for <xref:System.Activities.Statements.Assign.Value%2A> because the value is flowing into the <xref:System.Activities.Statements.Assign%601> activity through its <xref:System.Activities.Statements.Assign.Value%2A> argument, and `OutArgument<string>` is used for <xref:System.Activities.Statements.Assign.To%2A> because the value is flowing out of the <xref:System.Activities.Statements.Assign.To%2A> argument into the variable.</span></span> <span data-ttu-id="aaf5e-150">İkinci `Assign` etkinlik daha aynı şeyi gerçekleştirir örtük yayınları kullanır ancak eşdeğer sözdizimi sıkıştırın.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-150">The second `Assign` activity accomplishes the same thing with more compact but equivalent syntax that uses implicit casts.</span></span> <span data-ttu-id="aaf5e-151">`WriteLine` Etkinlikleri de kısa sözdizimini kullanın.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-151">The `WriteLine` activities also use the compact syntax.</span></span>  
  
```csharp  
// Declare three variables; the first one is given an initial value.  
Variable<string> var1 = new Variable<string>()  
{  
    Default = "one"  
};  
Variable<string> var2 = new Variable<string>();  
Variable<string> var3 = new Variable<string>();  
  
// Define the workflow  
Activity wf = new Sequence  
{  
    Variables = { var1, var2, var3 },  
    Activities =   
    {  
        new Assign<string>()  
        {  
            Value = new InArgument<string>(var1),  
            To = new OutArgument<string>(var2)  
        },  
        new WriteLine() { Text = var2 },  
        new Assign<string>()  
        {  
            Value = var2,  
            To = var3  
        },  
        new WriteLine() { Text = var3 }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
### <a name="using-variables-and-arguments-in-code-based-activities"></a><span data-ttu-id="aaf5e-152">Değişkenler ve bağımsız değişkenler, kod tabanlı etkinlikleri kullanma</span><span class="sxs-lookup"><span data-stu-id="aaf5e-152">Using Variables and Arguments in Code-Based Activities</span></span>  
 <span data-ttu-id="aaf5e-153">Önceki örneklerde, bağımsız değişkenleri ve iş akışları ve bildirim temelli etkinlikleri değişkenler nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-153">The previous examples show how to use arguments and variables in workflows and declarative activities.</span></span> <span data-ttu-id="aaf5e-154">Bağımsız değişkenler ve değişkenler, kod tabanlı etkinlikler de kullanılır.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-154">Arguments and variables are also used in code-based activities.</span></span> <span data-ttu-id="aaf5e-155">Kavramsal olarak kullanım çok benzer.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-155">Conceptually the usage is very similar.</span></span> <span data-ttu-id="aaf5e-156">Değişkenleri temsil eden etkinlik içinde veri depolama ve bağımsız değişkenler içine veya dışına etkinlik veri akışını temsil eden ve burada veya veri akışları temsil eden diğer değişkenleri veya iş akışı bağımsız değişkenler iş akışı yazar tarafından bağlı.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-156">Variables represent data storage within the activity, and arguments represent the flow of data into or out of the activity, and are bound by the workflow author to other variables or arguments in the workflow that represent where the data flows to or from.</span></span> <span data-ttu-id="aaf5e-157">GET veya değeri bir değişkene veya bağımsız bir etkinlik, bir etkinlik bağlamı içinde kullanılması gerekir kümesi, etkinliğin geçerli yürütme ortamını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-157">To get or set the value of a variable or argument in an activity, an activity context must be used that represents the current execution environment of the activity.</span></span> <span data-ttu-id="aaf5e-158">Yöntemlere geçirilen bu <xref:System.Activities.CodeActivity%601.Execute%2A> etkinlik iş akışı çalışma zamanı tarafından yöntemi.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-158">This is passed into the <xref:System.Activities.CodeActivity%601.Execute%2A> method of the activity by the workflow runtime.</span></span> <span data-ttu-id="aaf5e-159">Bu örnekte, özel bir `Add` etkinlik iki içeren tanımlanır <xref:System.Activities.ArgumentDirection.In> bağımsız değişkenler.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-159">In this example, a custom `Add` activity is defined that has two <xref:System.Activities.ArgumentDirection.In> arguments.</span></span> <span data-ttu-id="aaf5e-160">Bağımsız değişkenler değere erişmek için <xref:System.Activities.Argument.Get%2A> yöntemi kullanılır ve iş akışı çalışma zamanı tarafından geçirilen bağlamı kullanılır.</span><span class="sxs-lookup"><span data-stu-id="aaf5e-160">To access the value of the arguments, the <xref:System.Activities.Argument.Get%2A> method is used and the context that was passed in by the workflow runtime is used.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="aaf5e-161">Bağımsız değişkenler, değişkenler ve ifadeleri kod ile çalışma hakkında daha fazla bilgi için bkz. [yazma iş akışları, etkinlikler ve ifadeler kullanarak kesinliği kod](authoring-workflows-activities-and-expressions-using-imperative-code.md) ve [gerekli bağımsız değişkenler ve aşırı grupları](required-arguments-and-overload-groups.md).</span><span class="sxs-lookup"><span data-stu-id="aaf5e-161">For more information about working with arguments, variables, and expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md) and [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md).</span></span>
