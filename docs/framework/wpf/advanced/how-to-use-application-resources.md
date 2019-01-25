---
title: 'Nasıl yapılır: Uygulama Kaynaklarını Kullanma'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: acd172448ebdefd6395feec6ad50e1c9491d9e27
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733603"
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="b545a-102">Nasıl yapılır: Uygulama Kaynaklarını Kullanma</span><span class="sxs-lookup"><span data-stu-id="b545a-102">How to: Use Application Resources</span></span>
<span data-ttu-id="b545a-103">Bu örnek, uygulama kaynaklarının nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="b545a-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b545a-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="b545a-104">Example</span></span>  
 <span data-ttu-id="b545a-105">Aşağıdaki örnek bir uygulama tanımı dosyası gösterir.</span><span class="sxs-lookup"><span data-stu-id="b545a-105">The following example shows an application definition file.</span></span> <span data-ttu-id="b545a-106">Uygulama tanımı dosyası kaynak bölüm tanımlar (için bir değer <xref:System.Windows.Application.Resources%2A> özelliği).</span><span class="sxs-lookup"><span data-stu-id="b545a-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="b545a-107">Uygulama düzeyinde tanımlanan kaynaklar, uygulamanın parçası olan diğer tüm sayfalar tarafından erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="b545a-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="b545a-108">Bu durumda, bildirilen stili kaynaktır.</span><span class="sxs-lookup"><span data-stu-id="b545a-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="b545a-109">Bir denetim şablonu içeren tam bir stil uzun bu nedenle, bu örnek içinde tanımlanan bir denetim şablonu atlar <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> özellik ayarlayıcısına stili.</span><span class="sxs-lookup"><span data-stu-id="b545a-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="b545a-110">Aşağıdaki örnekte gösterildiği bir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] önceki örnekte tanımlanan uygulama düzeyi kaynağa başvuran sayfa.</span><span class="sxs-lookup"><span data-stu-id="b545a-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="b545a-111">Kaynak kullanarak başvurulan bir [StaticResource işaretleme uzantısı](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) , istenen kaynağın benzersiz kaynak anahtarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="b545a-111">The resource is referenced by using a     [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="b545a-112">Kaynak arama kapsamı istenen kaynak için geçerli sayfanın dışında ve tanımlı uygulama düzeyi kaynakları içine devam eder "GelButton" anahtarı ile kaynak geçerli sayfada bulunur.</span><span class="sxs-lookup"><span data-stu-id="b545a-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="b545a-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b545a-113">See also</span></span>
- [<span data-ttu-id="b545a-114">XAML Kaynakları</span><span class="sxs-lookup"><span data-stu-id="b545a-114">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [<span data-ttu-id="b545a-115">Uygulama Yönetimine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="b545a-115">Application Management Overview</span></span>](../../../../docs/framework/wpf/app-development/application-management-overview.md)
- [<span data-ttu-id="b545a-116">Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="b545a-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
