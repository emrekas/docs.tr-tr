---
title: Model-Görünüm-Görünüm Model ile Taşınabilir Sınıf Kitaplığı Kullanma
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b53be90764c6537fb27cb1b5ed781a68e69effa0
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504667"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="5161e-102">Model-Görünüm-Görünüm Model ile Taşınabilir Sınıf Kitaplığı Kullanma</span><span class="sxs-lookup"><span data-stu-id="5161e-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="5161e-103">.NET Framework kullanabilirsiniz [taşınabilir sınıf kitaplığı](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) Model-görünüm-görünüm Model (MVVM) desenini uygular ve birden çok platformda derlemeleri paylaşmak için.</span><span class="sxs-lookup"><span data-stu-id="5161e-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="5161e-104">MVVM temel iş mantığını kullanıcı arabiriminden yalıtan bir uygulama modelidir.</span><span class="sxs-lookup"><span data-stu-id="5161e-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="5161e-105">Visual Studio 2012'de taşınabilir sınıf kitaplığı projesinde modeli ve görünüm modeli sınıfları uygulayın ve ardından farklı platformlar için özelleştirilmiş görünümler oluşturun.</span><span class="sxs-lookup"><span data-stu-id="5161e-105">You can implement the model and view model classes in a Portable Class Library project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="5161e-106">Veri yazmak bu yaklaşım sayesinde modeli ve yalnızca bir kez iş mantığı ve kodu .NET Framework, Silverlight, Windows Phone, kullanım ve [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aşağıdaki çizimde gösterildiği gibi uygulamalar.</span><span class="sxs-lookup"><span data-stu-id="5161e-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>

 ![Paylaşım derlemeleri MVVM ile taşınabilir sınıf kitaplığı platformlar arasında gösterir.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 <span data-ttu-id="5161e-108">Bu konuda MVVM düzenini hakkında genel bilgiler sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="5161e-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="5161e-109">Yalnızca taşınabilir sınıf kitaplığı MVVM uygulamak için kullanma hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="5161e-109">It only provides information about how to use Portable Class Library to implement MVVM.</span></span> <span data-ttu-id="5161e-110">MVVM hakkında daha fazla bilgi için bkz: [MVVM hızlı başlangıç adımlarını kullanarak Prism kitaplığı 5.0 WPF için](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span><span class="sxs-lookup"><span data-stu-id="5161e-110">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="5161e-111">MVVM destekleyen sınıfları</span><span class="sxs-lookup"><span data-stu-id="5161e-111">Classes That Support MVVM</span></span>
 <span data-ttu-id="5161e-112">.NET Framework 4. 5'i hedeflediğiniz zaman [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight veya Windows Phone 7.5 taşınabilir sınıf kitaplığı projeniz için aşağıdaki sınıflar MVVM düzenini uygulamak için kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="5161e-112">When you target the .NET Framework 4.5, [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your Portable Class Library project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="5161e-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> Sınıfı</span><span class="sxs-lookup"><span data-stu-id="5161e-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="5161e-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> Sınıfı</span><span class="sxs-lookup"><span data-stu-id="5161e-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="5161e-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> Sınıfı</span><span class="sxs-lookup"><span data-stu-id="5161e-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="5161e-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> Sınıfı</span><span class="sxs-lookup"><span data-stu-id="5161e-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="5161e-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> Sınıfı</span><span class="sxs-lookup"><span data-stu-id="5161e-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="5161e-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> Sınıfı</span><span class="sxs-lookup"><span data-stu-id="5161e-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="5161e-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> Sınıfı</span><span class="sxs-lookup"><span data-stu-id="5161e-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="5161e-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> Sınıfı</span><span class="sxs-lookup"><span data-stu-id="5161e-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="5161e-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> Sınıfı</span><span class="sxs-lookup"><span data-stu-id="5161e-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="5161e-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> Sınıfı</span><span class="sxs-lookup"><span data-stu-id="5161e-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="5161e-123">Tüm sınıflarda <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> ad alanı</span><span class="sxs-lookup"><span data-stu-id="5161e-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="5161e-124">MVVM uygulama</span><span class="sxs-lookup"><span data-stu-id="5161e-124">Implementing MVVM</span></span>
 <span data-ttu-id="5161e-125">Taşınabilir sınıf kitaplığı projesini bir taşınabilir olmayan proje başvuramadığından MVVM uygulamak için genellikle hem model ve görünüm modeli bir taşınabilir sınıf kitaplığı projesinde oluşturursunuz.</span><span class="sxs-lookup"><span data-stu-id="5161e-125">To implement MVVM, you typically create both the model and the view model in a Portable Class Library project, because a Portable Class Library project cannot reference a non-portable project.</span></span> <span data-ttu-id="5161e-126">Model ve görünüm modeli, aynı projede veya projelerde ayrı olabilir.</span><span class="sxs-lookup"><span data-stu-id="5161e-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="5161e-127">Ayrı projeler kullanabilir, bir başvuru görünüm modeli projeden modeli projeye ekleyin.</span><span class="sxs-lookup"><span data-stu-id="5161e-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="5161e-128">Model derleme ve model projelerini görüntülemek sonra bu derlemeleri görünümü içeren uygulama başvuru.</span><span class="sxs-lookup"><span data-stu-id="5161e-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="5161e-129">Görünüm yalnızca görünüm model ile etkileşime giren, yalnızca görünüm modeli içeren derlemeye başvuru gerekir.</span><span class="sxs-lookup"><span data-stu-id="5161e-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="5161e-130">Model</span><span class="sxs-lookup"><span data-stu-id="5161e-130">Model</span></span>
 <span data-ttu-id="5161e-131">Aşağıdaki örnek, bir taşınabilir sınıf kitaplığı projesinde bulunan bir basitleştirilmiş bir model sınıfı gösterir.</span><span class="sxs-lookup"><span data-stu-id="5161e-131">The following example shows a simplified model class that could reside in a Portable Class Library project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="5161e-132">Aşağıdaki örnek, doldurmak, almak ve taşınabilir sınıf kitaplığı proje verileri güncelleştirmek için basit bir yol gösterir.</span><span class="sxs-lookup"><span data-stu-id="5161e-132">The following example shows a simple way to populate, retrieve, and update the data in a Portable Class Library project.</span></span> <span data-ttu-id="5161e-133">Gerçek bir uygulamada, bir Windows Communication Foundation (WCF) hizmeti gibi bir kaynaktan gelen verileri almak.</span><span class="sxs-lookup"><span data-stu-id="5161e-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="5161e-134">Görünüm modeli</span><span class="sxs-lookup"><span data-stu-id="5161e-134">View Model</span></span>
 <span data-ttu-id="5161e-135">Görünüm modelleri için temel sınıf sık MVVM düzenini uygularken eklenir.</span><span class="sxs-lookup"><span data-stu-id="5161e-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="5161e-136">Aşağıdaki örnek, bir taban sınıfı gösterir.</span><span class="sxs-lookup"><span data-stu-id="5161e-136">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="5161e-137">Uygulanışı <xref:System.Windows.Input.ICommand> arabirimi MVVM desen ile sık kullanılır.</span><span class="sxs-lookup"><span data-stu-id="5161e-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="5161e-138">Aşağıdaki örnek bir uygulamasını gösterir <xref:System.Windows.Input.ICommand> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="5161e-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="5161e-139">Aşağıdaki örnek, bir basitleştirilmiş görünüm modeli gösterir.</span><span class="sxs-lookup"><span data-stu-id="5161e-139">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="5161e-140">Görüntüle</span><span class="sxs-lookup"><span data-stu-id="5161e-140">View</span></span>  
 <span data-ttu-id="5161e-141">Bir .NET Framework 4.5 uygulamasından [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulama, Silverlight tabanlı uygulamanın veya Windows Phone 7.5 uygulama, modeli ve görünüm model projelerini içeren derlemeye başvurabilir.</span><span class="sxs-lookup"><span data-stu-id="5161e-141">From a .NET Framework 4.5 app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="5161e-142">Ardından Görünüm model ile etkileşime giren bir görünüm oluşturun.</span><span class="sxs-lookup"><span data-stu-id="5161e-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="5161e-143">Aşağıdaki örnek, alır ve görünüm modeli verileri güncelleştiren basitleştirilmiş bir Windows Presentation Foundation (WPF) uygulaması gösterir.</span><span class="sxs-lookup"><span data-stu-id="5161e-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="5161e-144">Silverlight, Windows Phone benzer görünümler oluşturabilir veya [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulamalar.</span><span class="sxs-lookup"><span data-stu-id="5161e-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5161e-145">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5161e-145">See also</span></span>

- [<span data-ttu-id="5161e-146">Taşınabilir Sınıf Kitaplığı</span><span class="sxs-lookup"><span data-stu-id="5161e-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
