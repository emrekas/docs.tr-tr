---
title: 'Nasıl yapılır: XML Ad Alanlarını Kullanarak Veri Bağlama'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 38bf6e8f88b0325193d49148cd6c33031f7b0a6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150000"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="56f68-102">Nasıl yapılır: XML Ad Alanlarını Kullanarak Veri Bağlama</span><span class="sxs-lookup"><span data-stu-id="56f68-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="56f68-103">Örnek</span><span class="sxs-lookup"><span data-stu-id="56f68-103">Example</span></span>  
 <span data-ttu-id="56f68-104">Bu örnek belirtilen ad alanlarını nasıl ele alınacağını gösterir, [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] bağlama kaynağı.</span><span class="sxs-lookup"><span data-stu-id="56f68-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="56f68-105">Varsa, [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] verileri içeren aşağıdaki [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ad alanı tanımı:</span><span class="sxs-lookup"><span data-stu-id="56f68-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="56f68-106">Kullanabileceğiniz <xref:System.Windows.Data.XmlNamespaceMapping> öğesi ad alanına eşlemek için bir <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, aşağıdaki örnekte olduğu gibi.</span><span class="sxs-lookup"><span data-stu-id="56f68-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="56f68-107">Ardından <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> başvurmak için [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ad alanı.</span><span class="sxs-lookup"><span data-stu-id="56f68-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="56f68-108"><xref:System.Windows.Controls.ListBox> Bu örnekte görüntüler *başlık* ve *dc:date* her *öğesi*.</span><span class="sxs-lookup"><span data-stu-id="56f68-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="56f68-109">Unutmayın <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> belirtmeniz gerekmez kullanılanla eşleşen [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] önek değişirse; kaynak [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] kaynak eşleştirme hala çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="56f68-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="56f68-110">Bu örnekte, [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] veriler bir web hizmetinden gelir ancak <xref:System.Windows.Data.XmlNamespaceMapping> öğesi, satır içi ile de çalışır [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] veya [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] katıştırılmış dosyasındaki verileri.</span><span class="sxs-lookup"><span data-stu-id="56f68-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f68-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="56f68-111">See also</span></span>

- [<span data-ttu-id="56f68-112">XMLDataProvider ve XPath Sorgularını Kullanarak XML Verilerine Bağlama</span><span class="sxs-lookup"><span data-stu-id="56f68-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="56f68-113">Veri Bağlamaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="56f68-113">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="56f68-114">Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="56f68-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
