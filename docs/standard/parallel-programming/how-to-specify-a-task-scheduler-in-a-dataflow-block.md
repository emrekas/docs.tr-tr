---
title: 'Nasıl yapılır: Veri Akışı Bloğunda Görev Zamanlayıcı Belirtme'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, linking to task scheduler in TPL
- Task Parallel Library, dataflows
- task scheduler, linking from TPL
ms.assetid: 27ece374-ed5b-49ef-9cec-b20db34a65e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 681c0f1f918c8991ed2544189488d1ea25547834
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935401"
---
# <a name="how-to-specify-a-task-scheduler-in-a-dataflow-block"></a><span data-ttu-id="5a102-102">Nasıl yapılır: Veri Akışı Bloğunda Görev Zamanlayıcı Belirtme</span><span class="sxs-lookup"><span data-stu-id="5a102-102">How to: Specify a Task Scheduler in a Dataflow Block</span></span>
<span data-ttu-id="5a102-103">Bu belge, uygulamanızda veri akışı kullandığınızda belirli bir Görev Zamanlayıcı ilişkilendirilecek gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="5a102-103">This document demonstrates how to associate a specific task scheduler when you use dataflow in your application.</span></span> <span data-ttu-id="5a102-104">Örnekte <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair?displayProperty=nameWithType> görevleri okuyucu etkin olduğunda ve bir yazıcı görev etkin olduğunda gösterilecek bir Windows Forms uygulamasında sınıfı.</span><span class="sxs-lookup"><span data-stu-id="5a102-104">The example uses the <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair?displayProperty=nameWithType> class in a Windows Forms application to show when reader tasks are active and when a writer task is active.</span></span> <span data-ttu-id="5a102-105">Ayrıca kullanan <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> kullanıcı arabirimi iş parçacığı üzerinde çalıştırılacak bir veri akışı bloğu etkinleştirmek için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="5a102-105">It also uses the <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method to enable a dataflow block to run on the user-interface thread.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="5a102-106">Formları uygulaması Windows oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="5a102-106">To Create the Windows Forms Application</span></span>  
  
1. <span data-ttu-id="5a102-107">Bir Visual C# veya Visual Basic oluşturma **Windows Forms uygulaması** proje.</span><span class="sxs-lookup"><span data-stu-id="5a102-107">Create a Visual C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="5a102-108">Aşağıdaki adımlarda, proje adı `WriterReadersWinForms`.</span><span class="sxs-lookup"><span data-stu-id="5a102-108">In the following steps, the project is named `WriterReadersWinForms`.</span></span>  
  
2. <span data-ttu-id="5a102-109">Ana form için form tasarımcıda Form1.cs (Visual Basic için Form1.vb), ekleme dört <xref:System.Windows.Forms.CheckBox> kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="5a102-109">On the form designer for the main form, Form1.cs (Form1.vb for Visual Basic), add four <xref:System.Windows.Forms.CheckBox> controls.</span></span> <span data-ttu-id="5a102-110">Ayarlama <xref:System.Windows.Forms.Control.Text%2A> özelliğini **Okuyucu 1** için `checkBox1`, **okuyucu 2** için `checkBox2`, **okuyucu 3** için `checkBox3`, ve  **Yazıcı** için `checkBox4`.</span><span class="sxs-lookup"><span data-stu-id="5a102-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to **Reader 1** for `checkBox1`, **Reader 2** for `checkBox2`, **Reader 3** for `checkBox3`, and **Writer** for `checkBox4`.</span></span> <span data-ttu-id="5a102-111">Ayarlama <xref:System.Windows.Forms.Control.Enabled%2A> özelliği için her denetim için `False`.</span><span class="sxs-lookup"><span data-stu-id="5a102-111">Set the <xref:System.Windows.Forms.Control.Enabled%2A> property for each control to `False`.</span></span>  
  
3. <span data-ttu-id="5a102-112">Ekleme bir <xref:System.Windows.Forms.Timer> forma.</span><span class="sxs-lookup"><span data-stu-id="5a102-112">Add a <xref:System.Windows.Forms.Timer> control to the form.</span></span> <span data-ttu-id="5a102-113">Ayarlama <xref:System.Windows.Forms.Timer.Interval%2A> özelliğini `2500`.</span><span class="sxs-lookup"><span data-stu-id="5a102-113">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `2500`.</span></span>  
  
## <a name="adding-dataflow-functionality"></a><span data-ttu-id="5a102-114">Veri akışı işlevsellik ekleme</span><span class="sxs-lookup"><span data-stu-id="5a102-114">Adding Dataflow Functionality</span></span>  
 <span data-ttu-id="5a102-115">Bu bölümde, uygulama içinde katılan veri akışı blokları oluşturma ve her biri bir Görev Zamanlayıcısı ile ilişkilendirmek nasıl açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="5a102-115">This section describes how to create the dataflow blocks that participate in the application and how to associate each one with a task scheduler.</span></span>  
  
### <a name="to-add-dataflow-functionality-to-the-application"></a><span data-ttu-id="5a102-116">Uygulama veri akışı işlevselliği eklemek için</span><span class="sxs-lookup"><span data-stu-id="5a102-116">To Add Dataflow Functionality to the Application</span></span>  
  
1. <span data-ttu-id="5a102-117">Projenizde, System.Threading.Tasks.Dataflow.dll'ye birer başvuru ekleyin.</span><span class="sxs-lookup"><span data-stu-id="5a102-117">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2. <span data-ttu-id="5a102-118">Form1.cs (Visual Basic için Form1.vb) aşağıdaki içerdiğinden emin olun `using` deyimleri (`Imports` Visual Basic'te).</span><span class="sxs-lookup"><span data-stu-id="5a102-118">Ensure that Form1.cs (Form1.vb for Visual Basic) contains the following `using` statements (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#1)]  
  
3. <span data-ttu-id="5a102-119">Ekleme bir <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> veri üyesi `Form1` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="5a102-119">Add a <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> data member to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#2)]  
  
4. <span data-ttu-id="5a102-120">İçinde `Form1` çağrısından sonra bir oluşturucu `InitializeComponent`, oluşturun bir <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> durumunu değiştirir nesne <xref:System.Windows.Forms.CheckBox> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="5a102-120">In the `Form1` constructor, after the call to `InitializeComponent`, create an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object that toggles the state of <xref:System.Windows.Forms.CheckBox> objects.</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#3)]  
  
5. <span data-ttu-id="5a102-121">İçinde `Form1` oluşturucusu, oluşturun bir <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> nesne ve dört <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> nesneleri, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> her nesne <xref:System.Windows.Forms.CheckBox> nesne.</span><span class="sxs-lookup"><span data-stu-id="5a102-121">In the `Form1` constructor, create a <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> object and four <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> objects, one <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object for each <xref:System.Windows.Forms.CheckBox> object.</span></span> <span data-ttu-id="5a102-122">Her <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> nesne, belirtin bir <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> nesnesi <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> özelliğini <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ConcurrentScheduler%2A> okuyucular için özellik ve <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ExclusiveScheduler%2A> yazıcısı için özelliği.</span><span class="sxs-lookup"><span data-stu-id="5a102-122">For each <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object, specify a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to the <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ConcurrentScheduler%2A> property for the readers, and the <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ExclusiveScheduler%2A> property for the writer.</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#4)]  
  
6. <span data-ttu-id="5a102-123">İçinde `Form1` oluşturucusu, başlangıç <xref:System.Windows.Forms.Timer> nesne.</span><span class="sxs-lookup"><span data-stu-id="5a102-123">In the `Form1` constructor, start the <xref:System.Windows.Forms.Timer> object.</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#5)]  
  
7. <span data-ttu-id="5a102-124">Ana form için form tasarımcıda oluşturmak için bir olay işleyicisi <xref:System.Windows.Forms.Timer.Tick> süreölçer olayı.</span><span class="sxs-lookup"><span data-stu-id="5a102-124">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.Timer.Tick> event for the timer.</span></span>  
  
8. <span data-ttu-id="5a102-125">Uygulama <xref:System.Windows.Forms.Timer.Tick> süreölçer olayı.</span><span class="sxs-lookup"><span data-stu-id="5a102-125">Implement the <xref:System.Windows.Forms.Timer.Tick> event for the timer.</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#6)]  
  
 <span data-ttu-id="5a102-126">Çünkü `toggleCheckBox` veri akışı bloğu davranır kullanıcı arabiriminde önemlidir Bu eylem kullanıcı arabirimi iş parçacığı üzerinde oluşur.</span><span class="sxs-lookup"><span data-stu-id="5a102-126">Because the `toggleCheckBox` dataflow block acts on the user interface, it is important that this action occur on the user-interface thread.</span></span> <span data-ttu-id="5a102-127">Bu nesne sağlar yapım sırasında bunu gerçekleştirmek için bir <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> nesnesi <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> özelliğini <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5a102-127">To accomplish this, during construction this object provides a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5a102-128"><xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A> Yöntemi oluşturur bir <xref:System.Threading.Tasks.TaskScheduler> geçerli eşitleme kapsamının üzerinde işini gerçekleştiren nesne.</span><span class="sxs-lookup"><span data-stu-id="5a102-128">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="5a102-129">Çünkü `Form1` Oluşturucu eylem için kullanıcı arabirimi iş parçacığından çağrılır `toggleCheckBox` veri akışı bloğu kullanıcı arabirimi iş parçacığı üzerinde de çalışır.</span><span class="sxs-lookup"><span data-stu-id="5a102-129">Because the `Form1` constructor is called from the user-interface thread, the action for the `toggleCheckBox` dataflow block also runs on the user-interface thread.</span></span>  
  
 <span data-ttu-id="5a102-130">Bu örnekte ayrıca <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> eşzamanlı olarak görev yapacak bazı veri akışı bloklarının etkinleştirmek için sınıf ve başka bir veri akışı bloğunun aynı çalıştıran diğer tüm veri akışı bloklarının göre özel olarak davranacak şekilde <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> nesne.</span><span class="sxs-lookup"><span data-stu-id="5a102-130">This example also uses the <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> class to enable some dataflow blocks to act concurrently, and another dataflow block to act exclusive with respect to all other dataflow blocks that run on the same <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> object.</span></span> <span data-ttu-id="5a102-131">El ile bu kaynağa erişimi eşitleme gereksinimini ortadan kaldırdığından bu tekniği birden çok veri akışı bloklarının kaynağı paylaşmak ve bu kaynağa özel erişim gerektiren bazı yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="5a102-131">This technique is useful when multiple dataflow blocks share a resource and some require exclusive access to that resource, because it eliminates the requirement to manually synchronize access to that resource.</span></span> <span data-ttu-id="5a102-132">El ile eşitleme saydamlığından kod daha verimli olmasını sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="5a102-132">The elimination of manual synchronization can make code more efficient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a102-133">Örnek</span><span class="sxs-lookup"><span data-stu-id="5a102-133">Example</span></span>  
 <span data-ttu-id="5a102-134">Aşağıdaki örnek, Form1.cs (Visual Basic için Form1.vb) için tam kod gösterilir.</span><span class="sxs-lookup"><span data-stu-id="5a102-134">The following example shows the complete code for Form1.cs (Form1.vb for Visual Basic).</span></span>  
  
 [!code-csharp[TPLDataflow_WriterReadersWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_WriterReadersWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="5a102-135">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5a102-135">See also</span></span>

- [<span data-ttu-id="5a102-136">Veri akışı</span><span class="sxs-lookup"><span data-stu-id="5a102-136">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
