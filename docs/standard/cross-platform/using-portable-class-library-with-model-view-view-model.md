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
ms.openlocfilehash: 8b48dc67e18411d82f03d29ab244d57575d6d720
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835791"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Model-Görünüm-Görünüm Model ile Taşınabilir Sınıf Kitaplığı Kullanma
.NET Framework kullanabilirsiniz [taşınabilir sınıf kitaplığı](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) Model-görünüm-görünüm Model (MVVM) desenini uygular ve birden çok platformda derlemeleri paylaşmak için.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 MVVM temel iş mantığını kullanıcı arabiriminden yalıtan bir uygulama modelidir. Model ve görünüm modeli sınıflarda uygulayabilirsiniz bir [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proje Visual Studio 2012'de ve ardından farklı platformlar için özelleştirilmiş görünümler oluşturun. Veri yazmak bu yaklaşım sayesinde modeli ve yalnızca bir kez iş mantığı ve kodu .NET Framework, Silverlight, Windows Phone, kullanım ve [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aşağıdaki çizimde gösterildiği gibi uygulamalar.

 ![Diyagram MVVM ile taşınabilir](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")

 Bu konuda MVVM düzenini hakkında genel bilgiler sağlamaz. Yalnızca nasıl kullanılacağı hakkında bilgi sağlar [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] MVVM uygulamak için. MVVM hakkında daha fazla bilgi için bkz: [MVVM hızlı başlangıç adımlarını kullanarak Prism kitaplığı 5.0 WPF için](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).

## <a name="classes-that-support-mvvm"></a>MVVM destekleyen sınıfları
 Hedeflediğinizde [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight veya Windows Phone 7.5, [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proje, aşağıdaki sınıflar MVVM düzenini uygulamak için kullanılabilir:

-   <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> Sınıfı

-   <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> Sınıfı

-   <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> Sınıfı

-   <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> Sınıfı

-   <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> Sınıfı

-   <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> Sınıfı

-   <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> Sınıfı

-   <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> Sınıfı

-   <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> Sınıfı

-   <xref:System.Windows.Input.ICommand?displayProperty=nameWithType> Sınıfı

-   Tüm sınıflarda <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> ad alanı

## <a name="implementing-mvvm"></a>MVVM uygulama
 MVVM uygulamak için genellikle hem model ve görünüm modeli içinde oluşturduğunuz bir [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] çünkü proje bir [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proje, taşınabilir olmayan proje başvuramaz. Model ve görünüm modeli, aynı projede veya projelerde ayrı olabilir. Ayrı projeler kullanabilir, bir başvuru görünüm modeli projeden modeli projeye ekleyin.

 Model derleme ve model projelerini görüntülemek sonra bu derlemeleri görünümü içeren uygulama başvuru. Görünüm yalnızca görünüm model ile etkileşime giren, yalnızca görünüm modeli içeren derlemeye başvuru gerekir.

### <a name="model"></a>Model
 Aşağıdaki örnek, içinde yer alan bir basitleştirilmiş bir model sınıfı gösterir. bir [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proje.

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 Aşağıdaki örnek, doldurmak, almak ve verileri güncelleştirmek için basit bir yol gösterir. bir [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proje. Gerçek bir uygulamada, bir Windows Communication Foundation (WCF) hizmeti gibi bir kaynaktan gelen verileri almak.

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a>Görünüm modeli
 Görünüm modelleri için temel sınıf sık MVVM düzenini uygularken eklenir. Aşağıdaki örnek, bir taban sınıfı gösterir.

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 Uygulanışı <xref:System.Windows.Input.ICommand> arabirimi MVVM desen ile sık kullanılır. Aşağıdaki örnek bir uygulamasını gösterir <xref:System.Windows.Input.ICommand> arabirimi.

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 Aşağıdaki örnek, bir basitleştirilmiş görünüm modeli gösterir.

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Görüntüle  
 Gelen bir [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] uygulamayı [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulama, Silverlight tabanlı uygulamanın veya Windows Phone 7.5 uygulama, modeli ve görünüm model projelerini içeren derlemeye başvurabilir.  Ardından Görünüm model ile etkileşime giren bir görünüm oluşturun. Aşağıdaki örnek, alır ve görünüm modeli verileri güncelleştiren basitleştirilmiş bir Windows Presentation Foundation (WPF) uygulaması gösterir. Silverlight, Windows Phone benzer görünümler oluşturabilir veya [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulamalar.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Taşınabilir Sınıf Kitaplığı](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
