---
title: 'Nasıl yapılır: PriorityBinding Uygulama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: aaf2caff1e2684e08c7eb65125536f1070203d70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020861"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="031d9-102">Nasıl yapılır: PriorityBinding Uygulama</span><span class="sxs-lookup"><span data-stu-id="031d9-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="031d9-103"><xref:System.Windows.Data.PriorityBinding> içinde [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bağlamaları listesi belirterek çalışır.</span><span class="sxs-lookup"><span data-stu-id="031d9-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="031d9-104">Bağlamaları listesi en düşük önceliği en yüksek öncelik aralığı sıralanır.</span><span class="sxs-lookup"><span data-stu-id="031d9-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="031d9-105">En yüksek öncelikli bağlama bir değer döndürürse başarıyla işlendiğinde yoktur hiçbir zaman listedeki diğer bağlamalar işlem gerekmez.</span><span class="sxs-lookup"><span data-stu-id="031d9-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="031d9-106">En yüksek öncelikli bağlama uyumluluğunun değerlendirilebilmesi için çok uzun sürüyor durumu olabilir, başarıyla bir değer döndüren bir sonraki en yüksek öncelikli bir daha yüksek bir öncelik değeri başarıyla döndürünceye kadar kullanılır.</span><span class="sxs-lookup"><span data-stu-id="031d9-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="031d9-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="031d9-107">Example</span></span>  
 <span data-ttu-id="031d9-108">Göstermek için nasıl <xref:System.Windows.Data.PriorityBinding> çalıştığını `AsyncDataSource` nesnesi şu üç özellik ile oluşturuldu: `FastDP`, `SlowerDP`, ve `SlowestDP`.</span><span class="sxs-lookup"><span data-stu-id="031d9-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="031d9-109">Get erişimcisine `FastDP` değerini döndürür `_fastDP` veri üyesi.</span><span class="sxs-lookup"><span data-stu-id="031d9-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="031d9-110">Get erişimcisine `SlowerDP` değerini döndürmeden önce 3 saniye bekler `_slowerDP` veri üyesi.</span><span class="sxs-lookup"><span data-stu-id="031d9-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="031d9-111">Get erişimcisine `SlowestDP` değerini döndürmeden önce 5 saniye bekler `_slowestDP` veri üyesi.</span><span class="sxs-lookup"><span data-stu-id="031d9-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="031d9-112">Bu örnek yalnızca gösterim amaçlıdır.</span><span class="sxs-lookup"><span data-stu-id="031d9-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="031d9-113">[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] Kat bir alan kümesi olandan daha yavaş olan özellikleri tanımlamaya karşı önerir.</span><span class="sxs-lookup"><span data-stu-id="031d9-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="031d9-114">Daha fazla bilgi için [seçme arasında özellikleri ve yöntemleri](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="031d9-114">For more information, see [Choosing Between Properties and Methods](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span></span>  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="031d9-115"><xref:System.Windows.Controls.TextBlock.Text%2A> Özelliğine bağlayan yukarıdaki `AsyncDS` kullanarak <xref:System.Windows.Data.PriorityBinding>:</span><span class="sxs-lookup"><span data-stu-id="031d9-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="031d9-116">Bağlama altyapısı işlediğinde <xref:System.Windows.Data.Binding> nesneler, ilk başladıktan <xref:System.Windows.Data.Binding>, bağlı `SlowestDP` özelliği.</span><span class="sxs-lookup"><span data-stu-id="031d9-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="031d9-117">Olduğunda bu <xref:System.Windows.Data.Binding> olduğundan, 5 saniye için bu nedenle sonraki uyku için işlenen, bir değer başarıyla dönmez <xref:System.Windows.Data.Binding> öğesi işlenir.</span><span class="sxs-lookup"><span data-stu-id="031d9-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="031d9-118">Sonraki <xref:System.Windows.Data.Binding> 3 saniye için uyku için bir değer başarıyla döndürmez.</span><span class="sxs-lookup"><span data-stu-id="031d9-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="031d9-119">Bağlama altyapısı ardından sonraki taşır <xref:System.Windows.Data.Binding> bağlı öğe, `FastDP` özelliği.</span><span class="sxs-lookup"><span data-stu-id="031d9-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="031d9-120">Bu <xref:System.Windows.Data.Binding> "Hızlı Value" değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="031d9-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="031d9-121"><xref:System.Windows.Controls.TextBlock> Artık "Hızlı Value" değeri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="031d9-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="031d9-122">3 saniye geçtikten sonra `SlowerDP` özelliği "Daha yavaş Value" değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="031d9-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="031d9-123"><xref:System.Windows.Controls.TextBlock> "Daha yavaş value" değerini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="031d9-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="031d9-124">5 saniye geçtikten sonra `SlowestDP` özelliği, "En yavaş Value" değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="031d9-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="031d9-125">Bu bağlama, ilk listelenmediğinden en yüksek önceliğe sahip.</span><span class="sxs-lookup"><span data-stu-id="031d9-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="031d9-126"><xref:System.Windows.Controls.TextBlock> Artık "yavaş value" görüntüler.</span><span class="sxs-lookup"><span data-stu-id="031d9-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="031d9-127">Bkz: <xref:System.Windows.Data.PriorityBinding> bağlamadan başarılı bir dönüş değeri olarak kabul hakkında bilgi.</span><span class="sxs-lookup"><span data-stu-id="031d9-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031d9-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="031d9-128">See also</span></span>

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [<span data-ttu-id="031d9-129">Veri Bağlamaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="031d9-129">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="031d9-130">Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="031d9-130">How-to Topics</span></span>](data-binding-how-to-topics.md)
