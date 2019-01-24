---
title: 'İzlenecek yol: İlk dokunmatik uygulamanızı oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
ms.openlocfilehash: 34a534653455449233c2908f4226cdb3a9bb9867
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724245"
---
# <a name="walkthrough-creating-your-first-touch-application"></a><span data-ttu-id="6d7f3-102">İzlenecek yol: İlk dokunmatik uygulamanızı oluşturma</span><span class="sxs-lookup"><span data-stu-id="6d7f3-102">Walkthrough: Creating Your First Touch Application</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="6d7f3-103">dokunmaya yanıt uygulamaları etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-103">enables applications to respond to touch.</span></span> <span data-ttu-id="6d7f3-104">Örneğin, birini kullanarak bir uygulama ile etkileşim kurabilir veya daha fazla parmağınızı bir dokunmaya duyarlı cihazda dokunmatik ekranı sunduğumuz taşımak kullanıcı sağlayan bir uygulama oluşturur. Örneğin, yeniden boyutlandırma veya touch'ı kullanarak tek bir nesne döndürme.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-104">For example, you can interact with an application by using one or more fingers on a touch-sensitive device, such as a touchscreen This walkthrough creates an application that enables the user to move, resize, or rotate a single object by using touch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6d7f3-105">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="6d7f3-105">Prerequisites</span></span>  
 <span data-ttu-id="6d7f3-106">Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:</span><span class="sxs-lookup"><span data-stu-id="6d7f3-106">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="6d7f3-107">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-107">Visual Studio.</span></span>  
  
-   <span data-ttu-id="6d7f3-108">Dokunma kabul eden bir cihaz Windows Dokunma destekleyen bir dokunmatik gibi girin.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-108">A device that accepts touch input, such as a touchscreen, that supports Windows Touch.</span></span>  
  
 <span data-ttu-id="6d7f3-109">Ayrıca, uygulamayı oluşturmak nasıl temel bir anlayışa sahip olmalıdır [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], özellikle abone olma ve bir olayı işlemek nasıl.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-109">Additionally, you should have a basic understanding of how to create an application in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especially how to subscribe to and handle an event.</span></span> <span data-ttu-id="6d7f3-110">Daha fazla bilgi için [izlenecek yol: İlk WPF Masaüstü Uygulamam](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="6d7f3-110">For more information, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="creating-the-application"></a><span data-ttu-id="6d7f3-111">Uygulama oluşturma</span><span class="sxs-lookup"><span data-stu-id="6d7f3-111">Creating the Application</span></span>  
  
#### <a name="to-create-the-application"></a><span data-ttu-id="6d7f3-112">Uygulama oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="6d7f3-112">To create the application</span></span>  
  
1.  <span data-ttu-id="6d7f3-113">Visual Basic veya Visual C# adlı yeni bir WPF uygulaması projesi oluşturma `BasicManipulation`.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-113">Create a new WPF Application project in Visual Basic or Visual C# named `BasicManipulation`.</span></span> <span data-ttu-id="6d7f3-114">Daha fazla bilgi için [nasıl yapılır: Yeni bir WPF uygulaması projesi oluşturma](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="6d7f3-114">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="6d7f3-115">MainWindow.xaml içeriğini aşağıdaki XAML ile değiştirin.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-115">Replace the contents of MainWindow.xaml with the following XAML.</span></span>  
  
     <span data-ttu-id="6d7f3-116">Bu işaretleme kırmızı içeren basit bir uygulama oluşturur <xref:System.Windows.Shapes.Rectangle> üzerinde bir <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-116">This markup creates a simple application that contains a red <xref:System.Windows.Shapes.Rectangle> on a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="6d7f3-117"><xref:System.Windows.UIElement.IsManipulationEnabled%2A> Özelliği <xref:System.Windows.Shapes.Rectangle> olayları düzenleme alabileceklerdir true olarak ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-117">The <xref:System.Windows.UIElement.IsManipulationEnabled%2A> property of the <xref:System.Windows.Shapes.Rectangle> is set to true so that it will receive manipulation events.</span></span> <span data-ttu-id="6d7f3-118">Uygulama abone <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, ve <xref:System.Windows.UIElement.ManipulationInertiaStarting> olayları.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-118">The application subscribes to the <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, and <xref:System.Windows.UIElement.ManipulationInertiaStarting> events.</span></span> <span data-ttu-id="6d7f3-119">Bu olaylar taşımak için mantığı içeren <xref:System.Windows.Shapes.Rectangle> zaman kullanıcı yönetir.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-119">These events contain the logic to move the <xref:System.Windows.Shapes.Rectangle> when the user manipulates it.</span></span>  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  <span data-ttu-id="6d7f3-120">Visual Basic kullanıyorsanız MainWindow.xaml öğesinin ilk satırı değiştirin `x:Class="BasicManipulation.MainWindow"` ile `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-120">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="BasicManipulation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
4.  <span data-ttu-id="6d7f3-121">İçinde `MainWindow` sınıfında, aşağıdaki <xref:System.Windows.UIElement.ManipulationStarting> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-121">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationStarting> event handler.</span></span>  
  
     <span data-ttu-id="6d7f3-122"><xref:System.Windows.UIElement.ManipulationStarting> Olaylarının zaman [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dokunma algılar nesneyi işlemek için giriş başlar.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-122">The <xref:System.Windows.UIElement.ManipulationStarting> event occurs when [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] detects that touch input begins to manipulate an object.</span></span> <span data-ttu-id="6d7f3-123">Kod düzenleme konumu göreli olması gerektiğini belirtir. <xref:System.Windows.Window> ayarlayarak <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-123">The code specifies that the position of the manipulation should be relative to the <xref:System.Windows.Window> by setting the <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> property.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]

5.  <span data-ttu-id="6d7f3-124">İçinde `MainWindow` sınıfında, aşağıdaki <xref:System.Windows.Input.ManipulationDelta> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-124">In the `MainWindow` class, add the following <xref:System.Windows.Input.ManipulationDelta> event handler.</span></span>

     <span data-ttu-id="6d7f3-125"><xref:System.Windows.Input.ManipulationDelta> Olaylarının dokunma girişi değişiklikleri konumu ve düzenleme sırasında birden çok kez gerçekleşebilir.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-125">The <xref:System.Windows.Input.ManipulationDelta> event occurs when the touch input changes position and can occur multiple times during a manipulation.</span></span> <span data-ttu-id="6d7f3-126">Olay, bir parmak kaldırıldıktan sonra da meydana gelebilir.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-126">The event can also occur after a finger is raised.</span></span> <span data-ttu-id="6d7f3-127">Örneğin, kullanıcı bir ekranda bir parmak sürüklediğinde <xref:System.Windows.Input.ManipulationDelta> olay parmağınızı hareket ettikçe birden çok kez gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-127">For example, if the user drags a finger across a screen, the <xref:System.Windows.Input.ManipulationDelta> event occurs multiple times as the finger moves.</span></span> <span data-ttu-id="6d7f3-128">Kullanıcı bir parmak ekranından çektiğinde <xref:System.Windows.Input.ManipulationDelta> tutan bir olayın gerçekleşmesi Eylemsizliği benzetimini yapmak için.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-128">When the user raises a finger from the screen, the <xref:System.Windows.Input.ManipulationDelta> event keeps occurring to simulate inertia.</span></span>

     <span data-ttu-id="6d7f3-129">Kod geçerli <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> için <xref:System.Windows.UIElement.RenderTransform%2A> , <xref:System.Windows.Shapes.Rectangle> taşımak için kullanıcı touch taşınırken giriş.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-129">The code applies the <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> to the <xref:System.Windows.UIElement.RenderTransform%2A> of the <xref:System.Windows.Shapes.Rectangle> to move it as the user moves the touch input.</span></span> <span data-ttu-id="6d7f3-130">Ayrıca denetler olmadığını <xref:System.Windows.Shapes.Rectangle> sınırları dışında <xref:System.Windows.Window> sırasında Eylemsizliği oluştuğunda olay.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-130">It also checks whether the <xref:System.Windows.Shapes.Rectangle> is outside the bounds of the <xref:System.Windows.Window> when the event occurs during inertia.</span></span> <span data-ttu-id="6d7f3-131">Bu nedenle, uygulama çağırırsa <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> düzenlemeyi sonlandırmak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-131">If so, the application calls the <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> method to end the manipulation.</span></span>

     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]

6.  <span data-ttu-id="6d7f3-132">İçinde `MainWindow` sınıfında, aşağıdaki <xref:System.Windows.UIElement.ManipulationInertiaStarting> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-132">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationInertiaStarting> event handler.</span></span>

     <span data-ttu-id="6d7f3-133"><xref:System.Windows.UIElement.ManipulationInertiaStarting> Olay kullanıcı ekrandan tüm parmağınızı çektiğinde gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-133">The <xref:System.Windows.UIElement.ManipulationInertiaStarting> event occurs when the user raises all fingers from the screen.</span></span> <span data-ttu-id="6d7f3-134">Bu kod, taşıma, genişletmeyi ve döndürme için yavaşlama ve başlangıç hızı ayarlar.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-134">The code sets the initial velocity and deceleration for the movement, expansion, and rotation of the rectangle.</span></span>

     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]

7.  <span data-ttu-id="6d7f3-135">Derleme ve projeyi çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-135">Build and run the project.</span></span>

     <span data-ttu-id="6d7f3-136">Penceresinde görünen bir kırmızı kare görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-136">You should see a red square appear in the window.</span></span>

## <a name="testing-the-application"></a><span data-ttu-id="6d7f3-137">Uygulamayı Test Etme</span><span class="sxs-lookup"><span data-stu-id="6d7f3-137">Testing the Application</span></span>
 <span data-ttu-id="6d7f3-138">Uygulamayı test etmek için aşağıdaki düzenlemeleri deneyin.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-138">To test the application, try the following manipulations.</span></span> <span data-ttu-id="6d7f3-139">Aşağıdaki aynı anda birden çok işlemi gerçekleştirebileceğinizi unutmayın.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-139">Note that you can do more than one of the following at the same time.</span></span>

-   <span data-ttu-id="6d7f3-140">Taşımak <xref:System.Windows.Shapes.Rectangle>, böylece parmağınızı yerleştirip <xref:System.Windows.Shapes.Rectangle> ve ekranda parmağınızı hareket ettirin.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-140">To move the <xref:System.Windows.Shapes.Rectangle>, put a finger on the <xref:System.Windows.Shapes.Rectangle> and move the finger across the screen.</span></span>

-   <span data-ttu-id="6d7f3-141">Yeniden boyutlandırmak için <xref:System.Windows.Shapes.Rectangle>, iki parmağınızı yerleştirip <xref:System.Windows.Shapes.Rectangle> parmağınızı yaklaşacak şekilde veya birbirlerinden küçüldükleri taşıyın.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-141">To resize the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and move the fingers closer together or farther apart from each other.</span></span>

-   <span data-ttu-id="6d7f3-142">Döndürülecek <xref:System.Windows.Shapes.Rectangle>, iki parmağınızı yerleştirip <xref:System.Windows.Shapes.Rectangle> ve parmağınızı birbirine etrafında döndürün.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-142">To rotate the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and rotate the fingers around each other.</span></span>

 <span data-ttu-id="6d7f3-143">Eylemsizlik neden olmak için önceki işlemeleri gerçekleştirme gibi parmaklarınızın ekranından hızlı bir şekilde yükseltin.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-143">To cause inertia, quickly raise your fingers from the screen as you perform the previous manipulations.</span></span> <span data-ttu-id="6d7f3-144"><xref:System.Windows.Shapes.Rectangle> Taşıma, yeniden boyutlandırmak veya durdurulmadan önce birkaç saniye boyunca devam eder.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-144">The <xref:System.Windows.Shapes.Rectangle> will continue to move, resize, or rotate for a few seconds before it stops.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d7f3-145">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6d7f3-145">See also</span></span>

- <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>