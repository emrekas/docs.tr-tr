---
title: 'Nasıl yapılır: Sayfa Yenileme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], refreshing
- refreshing pages [WPF]
ms.assetid: 06dd1bbd-81c4-40ad-ac0d-7a5b326b1465
ms.openlocfilehash: 71a71c91384a8905413358d023531afec23f2d41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947676"
---
# <a name="how-to-refresh-a-page"></a><span data-ttu-id="b0416-102">Nasıl yapılır: Sayfa Yenileme</span><span class="sxs-lookup"><span data-stu-id="b0416-102">How to: Refresh a Page</span></span>
<span data-ttu-id="b0416-103">Bu örnek nasıl çağrılacağını gösterir <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> geçerli içeriği yenilemek için yöntemi bir <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="b0416-103">This example shows how to call the <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> method to refresh the current content in a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0416-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="b0416-104">Example</span></span>  
 <span data-ttu-id="b0416-105"><xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> Geçerli içeriği yeniler bir <xref:System.Windows.Navigation.NavigationWindow> kaynağından yüklenecek.</span><span class="sxs-lookup"><span data-stu-id="b0416-105"><xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> refreshes the current content in a <xref:System.Windows.Navigation.NavigationWindow> to be reloaded from its source.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateRefreshCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigaterefreshcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateRefreshCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigaterefreshcode)]
