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
# <a name="using-portable-class-library-with-model-view-view-model"></a>Model-Görünüm-Görünüm Model ile Taşınabilir Sınıf Kitaplığı Kullanma
.NET Framework kullanabilirsiniz [taşınabilir sınıf kitaplığı](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) Model-görünüm-görünüm Model (MVVM) desenini uygular ve birden çok platformda derlemeleri paylaşmak için.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 MVVM temel iş mantığını kullanıcı arabiriminden yalıtan bir uygulama modelidir. Visual Studio 2012'de taşınabilir sınıf kitaplığı projesinde modeli ve görünüm modeli sınıfları uygulayın ve ardından farklı platformlar için özelleştirilmiş görünümler oluşturun. Veri yazmak bu yaklaşım sayesinde modeli ve yalnızca bir kez iş mantığı ve kodu .NET Framework, Silverlight, Windows Phone, kullanım ve [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aşağıdaki çizimde gösterildiği gibi uygulamalar.

 ![Paylaşım derlemeleri MVVM ile taşınabilir sınıf kitaplığı platformlar arasında gösterir.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 Bu konuda MVVM düzenini hakkında genel bilgiler sağlamaz. Yalnızca taşınabilir sınıf kitaplığı MVVM uygulamak için kullanma hakkında bilgi sağlar. MVVM hakkında daha fazla bilgi için bkz: [MVVM hızlı başlangıç adımlarını kullanarak Prism kitaplığı 5.0 WPF için](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).

## <a name="classes-that-support-mvvm"></a>MVVM destekleyen sınıfları
 .NET Framework 4. 5'i hedeflediğiniz zaman [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight veya Windows Phone 7.5 taşınabilir sınıf kitaplığı projeniz için aşağıdaki sınıflar MVVM düzenini uygulamak için kullanılabilir:

- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> Sınıfı

- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> Sınıfı

- <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> Sınıfı

- <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> Sınıfı

- <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> Sınıfı

- <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> Sınıfı

- <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> Sınıfı

- <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> Sınıfı

- <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> Sınıfı

- <xref:System.Windows.Input.ICommand?displayProperty=nameWithType> Sınıfı

- Tüm sınıflarda <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> ad alanı

## <a name="implementing-mvvm"></a>MVVM uygulama
 Taşınabilir sınıf kitaplığı projesini bir taşınabilir olmayan proje başvuramadığından MVVM uygulamak için genellikle hem model ve görünüm modeli bir taşınabilir sınıf kitaplığı projesinde oluşturursunuz. Model ve görünüm modeli, aynı projede veya projelerde ayrı olabilir. Ayrı projeler kullanabilir, bir başvuru görünüm modeli projeden modeli projeye ekleyin.

 Model derleme ve model projelerini görüntülemek sonra bu derlemeleri görünümü içeren uygulama başvuru. Görünüm yalnızca görünüm model ile etkileşime giren, yalnızca görünüm modeli içeren derlemeye başvuru gerekir.

### <a name="model"></a>Model
 Aşağıdaki örnek, bir taşınabilir sınıf kitaplığı projesinde bulunan bir basitleştirilmiş bir model sınıfı gösterir.

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 Aşağıdaki örnek, doldurmak, almak ve taşınabilir sınıf kitaplığı proje verileri güncelleştirmek için basit bir yol gösterir. Gerçek bir uygulamada, bir Windows Communication Foundation (WCF) hizmeti gibi bir kaynaktan gelen verileri almak.

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
 Bir .NET Framework 4.5 uygulamasından [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulama, Silverlight tabanlı uygulamanın veya Windows Phone 7.5 uygulama, modeli ve görünüm model projelerini içeren derlemeye başvurabilir.  Ardından Görünüm model ile etkileşime giren bir görünüm oluşturun. Aşağıdaki örnek, alır ve görünüm modeli verileri güncelleştiren basitleştirilmiş bir Windows Presentation Foundation (WPF) uygulaması gösterir. Silverlight, Windows Phone benzer görünümler oluşturabilir veya [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulamalar.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Taşınabilir Sınıf Kitaplığı](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
