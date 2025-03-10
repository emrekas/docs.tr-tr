---
title: 'Nasıl yapılır: Bağlama Kaynağı Belirtme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 55d47757-2648-4a52-987f-b767953f168c
ms.openlocfilehash: 418dc77ce7638698d4850b06dafcea57787e1015
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959696"
---
# <a name="how-to-specify-the-binding-source"></a>Nasıl yapılır: Bağlama Kaynağı Belirtme
Veri bağlamada bağlama kaynak nesnesi, verilerinizi elde ettiğiniz nesneye başvurur. Bu konuda, bağlama kaynağını belirtmenin farklı yolları açıklanmaktadır.  
  
## <a name="example"></a>Örnek  
 Birkaç özelliği ortak bir kaynağa bağlıyorsanız, tüm veri bağlama özelliklerinin ortak bir kaynağı devraldığı bir `DataContext` kapsam oluşturmak için kullanışlı bir yol sağlayan özelliğini kullanmak istersiniz.  
  
 Aşağıdaki örnekte, veri bağlamı uygulamanın kök öğesinde oluşturulmuştur. Bu, tüm alt öğelerin bu veri bağlamını devralmasını sağlar. Bağlama verisi, doğrudan eşleme yoluyla başvurulan ve kaynak `NetIncome` `incomeDataSource`anahtarı verilen özel bir veri sınıfından gelir.  
  
 [!code-xaml[DirectionalBinding#DataContext1](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext1)]  
[!code-xaml[DirectionalBinding#DataContext2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#datacontext2)]  
  
 Aşağıdaki örnek, `NetIncome` sınıfının tanımını gösterir.  
  
 [!code-csharp[DirectionalBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/billsdata.cs#dataobject)]
 [!code-vb[DirectionalBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DirectionalBinding/VisualBasic/NetIncome.vb#dataobject)]  
  
> [!NOTE]
> Yukarıdaki örnekte, biçimlendirme içindeki nesne başlatılır ve kaynak olarak kullanılır. Zaten kodda örneği oluşturulmuş bir nesneye bağlamak istiyorsanız, `DataContext` özelliği programlı olarak ayarlamanız gerekir. Bir örnek için bkz. [xaml 'de bağlama Için verileri kullanılabilir hale getirme](how-to-make-data-available-for-binding-in-xaml.md).  
  
 Alternatif olarak, tek tek Bağlamalarınızın kaynağını açıkça belirtmek isterseniz, aşağıdaki seçeneklere sahip olursunuz. Bu, devralınan veri bağlamına göre önceliklidir.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|<xref:System.Windows.Data.Binding.Source%2A>|Kaynağı bir nesnenin örneğine ayarlamak için bu özelliği kullanın. Birçok özelliğin aynı veri bağlamını devraldığı bir kapsam oluşturma işlevselliğine ihtiyaç duymadıysanız özelliği yerine <xref:System.Windows.Data.Binding.Source%2A> `DataContext` özelliğini kullanabilirsiniz. Daha fazla bilgi için bkz. <xref:System.Windows.Data.Binding.Source%2A>.|  
|<xref:System.Windows.Data.Binding.RelativeSource%2A>|Bu, bağlama Hedefinizdeki konuma göre kaynağı belirtmek istediğinizde yararlıdır. Bu özelliği kullanabileceğiniz bazı yaygın senaryolar, öğenizin bir özelliğini aynı öğenin başka bir özelliğine bağlamak istediğinizde veya bir stil ya da şablonda bir bağlama tanımlıyorsanız. Daha fazla bilgi için bkz. <xref:System.Windows.Data.Binding.RelativeSource%2A>.|  
|<xref:System.Windows.Data.Binding.ElementName%2A>|Bağlamak istediğiniz öğeyi temsil eden bir dize belirtirsiniz. Bu, uygulamanızdaki başka bir öğenin özelliğine bağlamak istediğinizde yararlıdır. Örneğin, uygulamanızda başka bir <xref:System.Windows.Controls.Slider> denetimin yüksekliğini denetlemek için kullanmak istiyorsanız veya denetikinizi <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> <xref:System.Windows.Controls.ListBox> denetikizin özelliğine bağlamak istiyorsanız. Daha fazla bilgi için bkz. <xref:System.Windows.Data.Binding.ElementName%2A>.|  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.FrameworkElement.DataContext%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.DataContext%2A?displayProperty=nameWithType>
- [Özellik Değeri Devralma](../advanced/property-value-inheritance.md)
- [Veri Bağlamaya Genel Bakış](data-binding-overview.md)
- [Bağlama Bildirimlerine Genel Bakış](binding-declarations-overview.md)
- [Nasıl Yapılır Konuları](data-binding-how-to-topics.md)
