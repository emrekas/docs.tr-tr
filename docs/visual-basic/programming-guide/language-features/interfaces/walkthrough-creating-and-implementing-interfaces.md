---
title: Oluşturma ve uygulama arabirimler (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: faed4d3c9498938e022daf821dd0aefbcbcf2e8d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053775"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="af01f-102">İzlenecek yol: Oluşturma ve uygulama arabirimler (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af01f-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="af01f-103">Arabirimler, özellikleri, yöntemleri ve olayları özelliklerini açıklayan, ancak yapıların veya sınıfların kadar uygulama ayrıntılarını bırakın.</span><span class="sxs-lookup"><span data-stu-id="af01f-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="af01f-104">Bu izlenecek yol, bildirme ve bir arabirim gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="af01f-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af01f-105">Bu izlenecek yol, bir kullanıcı arabirimi oluşturma hakkında bilgi sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="af01f-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="af01f-106">Arabirim tanımlamak için</span><span class="sxs-lookup"><span data-stu-id="af01f-106">To define an interface</span></span>
  
1. <span data-ttu-id="af01f-107">Yeni bir Visual Basic Windows uygulaması projesi açın.</span><span class="sxs-lookup"><span data-stu-id="af01f-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="af01f-108">Yeni modül tıklayarak projeye ekleyin. **Modül Ekle** üzerinde **proje** menüsü.</span><span class="sxs-lookup"><span data-stu-id="af01f-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="af01f-109">Yeni modül adı `Module1.vb` tıklatıp **Ekle**.</span><span class="sxs-lookup"><span data-stu-id="af01f-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="af01f-110">Yeni modül kodu görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="af01f-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="af01f-111">Adlı bir arabirim tanımla `TestInterface` içinde `Module1` yazarak `Interface TestInterface` arasında `Module` ve `End Module` deyimleri ve sonra ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="af01f-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="af01f-112">**Kod Düzenleyicisi** girintileri `Interface` anahtar sözcüğü ve ekler bir `End Interface` deyimini bir kod bloğu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="af01f-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="af01f-113">Bir özellik, yöntemi ve olay arabirimi için arasına aşağıdaki kodu yerleştirerek tanımlamak `Interface` ve `End Interface` ifadeleri:</span><span class="sxs-lookup"><span data-stu-id="af01f-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="af01f-114">Uygulama</span><span class="sxs-lookup"><span data-stu-id="af01f-114">Implementation</span></span>

 <span data-ttu-id="af01f-115">Arabirim üyeleri bildirmek için kullanılan sözdizimi sınıf üyeleri bildirmek için kullanılan söz dizimi farklı olduğunu fark edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af01f-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="af01f-116">Bu fark, arabirimler uygulama kodu içeremez olgu yansıtır.</span><span class="sxs-lookup"><span data-stu-id="af01f-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="af01f-117">Arabirim uygulamak için</span><span class="sxs-lookup"><span data-stu-id="af01f-117">To implement the interface</span></span>
  
1. <span data-ttu-id="af01f-118">Adlı bir sınıf ekleyin `ImplementationClass` şu deyimi ekleyerek `Module1`, sonra `End Interface` deyimi önce `End Module` deyimi ve sonra ENTER tuşuna basın:</span><span class="sxs-lookup"><span data-stu-id="af01f-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="af01f-119">Tümleşik geliştirme ortamında çalışıyorsanız **Kod Düzenleyicisi** eşleşen sağlayan `End Class` deyimi ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="af01f-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="af01f-120">Aşağıdaki `Implements` ifadesine `ImplementationClass`, sınıf, arabirim adları uygular:</span><span class="sxs-lookup"><span data-stu-id="af01f-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="af01f-121">Bir sınıf veya yapı, üst kısmındaki diğer öğelerden ayrı olarak listelenen `Implements` deyimi, sınıfın veya yapının bir arabirim uyguladığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="af01f-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="af01f-122">Tümleşik geliştirme ortamında çalışıyorsanız **Kod Düzenleyicisi** uygulayan sınıf üyelerini gerektirdiği `TestInterface` olduğunda ENTER tuşuna basın ve sonraki adıma atlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af01f-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="af01f-123">Tümleşik geliştirme ortamında çalışmıyorsanız, arabirimin tüm üyelerini uygulamalıdır `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="af01f-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="af01f-124">Aşağıdaki kodu ekleyin `ImplementationClass` uygulamak için `Event1`, `Method1`, ve `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="af01f-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="af01f-125">`Implements` Arabirimi ve uygulanan arabirim üyesi bildirimi adları.</span><span class="sxs-lookup"><span data-stu-id="af01f-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="af01f-126">Tanımını tamamlamak `Prop1` özellik değeri depolanan sınıfı için özel bir alan ekleyerek:</span><span class="sxs-lookup"><span data-stu-id="af01f-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="af01f-127">Dönüş değeri `pval` erişimci özelliğin alın.</span><span class="sxs-lookup"><span data-stu-id="af01f-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="af01f-128">Değerini `pval` erişimci özelliğini ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="af01f-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="af01f-129">Tanımını tamamlamak `Method1` aşağıdaki kodu ekleyerek.</span><span class="sxs-lookup"><span data-stu-id="af01f-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="af01f-130">Arabirim uygulamasını test etmek için</span><span class="sxs-lookup"><span data-stu-id="af01f-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="af01f-131">Başlangıç formu için projenizde sağ **Çözüm Gezgini**, tıklatıp **kodu görüntüle**.</span><span class="sxs-lookup"><span data-stu-id="af01f-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="af01f-132">Düzenleyici, başlangıç formu için sınıf görüntüler.</span><span class="sxs-lookup"><span data-stu-id="af01f-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="af01f-133">Varsayılan olarak, başlangıç formu çağrılır `Form1`.</span><span class="sxs-lookup"><span data-stu-id="af01f-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="af01f-134">Aşağıdaki `testInstance` alanı `Form1` sınıfı:</span><span class="sxs-lookup"><span data-stu-id="af01f-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="af01f-135">Bildirmek `testInstance` olarak `WithEvents`, `Form1` sınıf olayları işleyebilir.</span><span class="sxs-lookup"><span data-stu-id="af01f-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="af01f-136">Eklemek için aşağıdaki olay işleyicisini `Form1` tarafından başlatılan olayları işlemek için sınıfın `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="af01f-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="af01f-137">Adlı bir alt yordam Ekle `Test` için `Form1` uygulama sınıfımızın test edilecek sınıf:</span><span class="sxs-lookup"><span data-stu-id="af01f-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="af01f-138">`Test` Yordamı uygulayan sınıfın bir örneğini oluşturur `MyInterface`, bu örneğe atar `testInstance` alan, bir özelliğini ayarlar ve bir yöntem arabirimi aracılığıyla çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="af01f-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="af01f-139">Çağırmak için kod ekleyin `Test` yordamdan `Form1 Load` başlangıç formunuzun yordam:</span><span class="sxs-lookup"><span data-stu-id="af01f-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="af01f-140">Çalıştırma `Test` F5 tuşuna basarak yordamı.</span><span class="sxs-lookup"><span data-stu-id="af01f-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="af01f-141">İleti "Prop1 9'a ayarlanmış" görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="af01f-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="af01f-142">Tamam, "X parametresi Method1 için 5'tir" iletisi tıkladıktan sonra görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="af01f-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="af01f-143">Tamam'ı tıklatın ve "olay işleyicisi, olay yakalandı" iletisi görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="af01f-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af01f-144">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="af01f-144">See also</span></span>

- [<span data-ttu-id="af01f-145">Implements Deyimi</span><span class="sxs-lookup"><span data-stu-id="af01f-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="af01f-146">Arabirimler</span><span class="sxs-lookup"><span data-stu-id="af01f-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="af01f-147">Interface Deyimi</span><span class="sxs-lookup"><span data-stu-id="af01f-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="af01f-148">Event Deyimi</span><span class="sxs-lookup"><span data-stu-id="af01f-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
