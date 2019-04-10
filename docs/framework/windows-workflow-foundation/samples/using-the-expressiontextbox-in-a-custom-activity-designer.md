---
title: Özel Etkinlik Tasarımcısında ExpressionTextBox Kullanma
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: c85254f1ae7ba8a269568cf1a14acf367b595e33
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344981"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a><span data-ttu-id="0421c-102">Özel Etkinlik Tasarımcısında ExpressionTextBox Kullanma</span><span class="sxs-lookup"><span data-stu-id="0421c-102">Using the ExpressionTextBox in a Custom Activity Designer</span></span>
<span data-ttu-id="0421c-103">Bu örnek nasıl kullanılacağını gösterir <xref:System.Activities.Presentation.View.ExpressionTextBox> özel etkinlik Tasarımcısı'nda.</span><span class="sxs-lookup"><span data-stu-id="0421c-103">This sample shows how to use the <xref:System.Activities.Presentation.View.ExpressionTextBox> in a custom activity designer.</span></span> <span data-ttu-id="0421c-104">Özel Etkinlik `MultiAssign`, iki dize değişkenlerine iki dize değerleri atar.</span><span class="sxs-lookup"><span data-stu-id="0421c-104">The custom activity, `MultiAssign`, assigns two string values to two string variables.</span></span> <span data-ttu-id="0421c-105">Bazı <xref:System.Activities.Presentation.View.ExpressionTextBox> denetimlerini bağlamak için <xref:System.Activities.InArgument>s ve bazı bağlanma <xref:System.Activities.OutArgument>s.</span><span class="sxs-lookup"><span data-stu-id="0421c-105">Some <xref:System.Activities.Presentation.View.ExpressionTextBox> controls bind to <xref:System.Activities.InArgument>s and some bind to <xref:System.Activities.OutArgument>s.</span></span>

## <a name="sample-details"></a><span data-ttu-id="0421c-106">Örnek Ayrıntıları</span><span class="sxs-lookup"><span data-stu-id="0421c-106">Sample details</span></span>
 <span data-ttu-id="0421c-107">`ArgumentToExpressionConverter` Bağımsız değişken ifadeleri bağlanırken kullanılan türü dönüştürücü.</span><span class="sxs-lookup"><span data-stu-id="0421c-107">The `ArgumentToExpressionConverter` is the type converter used when binding expressions to arguments.</span></span> <span data-ttu-id="0421c-108">`ConverterParameter` Ayarlanmalıdır `In` veya `Out` uygun şekilde.</span><span class="sxs-lookup"><span data-stu-id="0421c-108">The `ConverterParameter` must be set to `In` or `Out` as appropriate.</span></span> `InOut` <span data-ttu-id="0421c-109">desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="0421c-109">is not supported.</span></span>

 <span data-ttu-id="0421c-110">`UseLocationExpression` Özniteliği kullanılır `OutArgument`s ifade bir L-değeri ("sol value" veya "konum değeri") ifadesi olması gerektiğini belirtin.</span><span class="sxs-lookup"><span data-stu-id="0421c-110">The `UseLocationExpression` attribute is used on `OutArgument`s to specify that the expression should be an L-value ("left value" or "location value") expression.</span></span> <span data-ttu-id="0421c-111">Çoğu durumda, bir L-değeri ifade göstermek için kullanılan geçerli bir Visual Basic tanımlayıcısı olan `OutArgument` iade edilmekte olan bir değişken veya değişken adı.</span><span class="sxs-lookup"><span data-stu-id="0421c-111">In most cases, an L-value expression is a valid Visual Basic identifier used to indicate that the `OutArgument` being returned is a variable or argument name.</span></span>

 <span data-ttu-id="0421c-112">`MaxLines` Özniteliği, bu örnekte birine ayarlanır ve `MinLines` ayarlı değil.</span><span class="sxs-lookup"><span data-stu-id="0421c-112">The `MaxLines` attribute is set to one in this example and `MinLines` is not set.</span></span> <span data-ttu-id="0421c-113">Gösterir <xref:System.Activities.Presentation.View.ExpressionTextBox> tek satır metin kullanıcı tarafından yazılan bakılmaksızın sabit bir boyutu.</span><span class="sxs-lookup"><span data-stu-id="0421c-113">This indicates that the <xref:System.Activities.Presentation.View.ExpressionTextBox> is a fixed size of one line regardless of the amount of text typed by the user.</span></span> <span data-ttu-id="0421c-114">İzin vermek için <xref:System.Activities.Presentation.View.ExpressionTextBox> kullanıcı girişi uyacak şekilde büyümesine olanak ayarlamak `MaxLines` büyüktür `MinLines`.</span><span class="sxs-lookup"><span data-stu-id="0421c-114">To allow the <xref:System.Activities.Presentation.View.ExpressionTextBox> to grow to fit user input, set `MaxLines` greater than `MinLines`.</span></span>

 <span data-ttu-id="0421c-115">Bir ExpressionTextBox bağımsız değişkenleri yalnızca bağlanabilir ve CLR özelliklerini bağlanamaz.</span><span class="sxs-lookup"><span data-stu-id="0421c-115">An ExpressionTextBox can only be bound to arguments, and cannot be bound to CLR properties.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="0421c-116">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="0421c-116">To use this sample</span></span>

1. <span data-ttu-id="0421c-117">Visual Studio 2010'u kullanarak, ExpressionTextBoxSample.sln dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="0421c-117">Using Visual Studio 2010, open the ExpressionTextBoxSample.sln file.</span></span>

2. <span data-ttu-id="0421c-118">Çözümü derlemek için CTRL + SHIFT + B tuşlarına basın.</span><span class="sxs-lookup"><span data-stu-id="0421c-118">To build the solution, press CTRL+SHIFT+B.</span></span>

#### <a name="to-run-this-sample"></a><span data-ttu-id="0421c-119">Bu örneği çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="0421c-119">To run this sample</span></span>

1. <span data-ttu-id="0421c-120">Çözüme yeni bir iş akışı konsol uygulaması ekleyin.</span><span class="sxs-lookup"><span data-stu-id="0421c-120">Add a new Workflow Console Application to the solution.</span></span>

2. <span data-ttu-id="0421c-121">Bir başvuru ekleyin **ExpressionTextBoxSample** proje yeni iş akışı konsol uygulaması projesi.</span><span class="sxs-lookup"><span data-stu-id="0421c-121">Add a reference to the **ExpressionTextBoxSample** project from the new Workflow Console Application project.</span></span>

3. <span data-ttu-id="0421c-122">Çözümü oluşturun.</span><span class="sxs-lookup"><span data-stu-id="0421c-122">Build the solution.</span></span>

4. <span data-ttu-id="0421c-123">Sürükleme **MultiAssign** araç kutusundan ve iş akışına bırakın.</span><span class="sxs-lookup"><span data-stu-id="0421c-123">Drag the **MultiAssign** activity from the toolbox and drop it into the workflow.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="0421c-124">Örnekler, makinenizde zaten yüklü.</span><span class="sxs-lookup"><span data-stu-id="0421c-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0421c-125">Devam etmeden önce şu (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="0421c-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0421c-126">Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="0421c-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0421c-127">Bu örnek, şu dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="0421c-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a><span data-ttu-id="0421c-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0421c-128">See also</span></span>

- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [<span data-ttu-id="0421c-129">İş Akışı Tasarımcısı ile uygulama geliştirme</span><span class="sxs-lookup"><span data-stu-id="0421c-129">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
