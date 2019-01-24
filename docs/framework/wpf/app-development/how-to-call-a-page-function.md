---
title: 'Nasıl yapılır: Sayfa İşlevi Çağırma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
ms.openlocfilehash: 4cd839cc959c1e3730418d2feab80b9aef642161
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542827"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="1da7d-102">Nasıl yapılır: Sayfa İşlevi Çağırma</span><span class="sxs-lookup"><span data-stu-id="1da7d-102">How to: Call a Page Function</span></span>
<span data-ttu-id="1da7d-103">Bu örnek bir Sayfa işlevinden çağırmak nasıl gösterir bir [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sayfası.</span><span class="sxs-lookup"><span data-stu-id="1da7d-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1da7d-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="1da7d-104">Example</span></span>  
 <span data-ttu-id="1da7d-105">Sayfasını kullanarak işlevi gezinebilirsiniz bir [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], bir sayfasına gittiğinizde olduğu gibi.</span><span class="sxs-lookup"><span data-stu-id="1da7d-105">You can navigate to a page function using a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], just as you can when you navigate to a page.</span></span> <span data-ttu-id="1da7d-106">Bu, aşağıdaki örnekte gösterilir.</span><span class="sxs-lookup"><span data-stu-id="1da7d-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="1da7d-107">Sayfa işlevine veri iletmek gerekiyorsa bir örneğini oluşturun ve bir özelliği ayarlayarak veri geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1da7d-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="1da7d-108">Veya aşağıdaki örnekte gösterildiği gibi varsayılan olmayan bir Oluşturucu kullanarak verileri geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1da7d-108">Or, as the following example shows, you can pass the data using a non-default constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="1da7d-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1da7d-109">See also</span></span>
- <xref:System.Windows.Navigation.PageFunction%601>
