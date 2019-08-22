---
title: 'Nasıl yapılır: Uygulama Oturumları Arasında Uygulama Kapsamı Özelliklerini Koruma ve Geri Yükleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application-scope properties [WPF], persisting
- persisting application-scope properties [WPF]
- properties [WPF], persisting
- restoring application-scope properties [WPF]
- properties [WPF], restoring
- application-scope properties [WPF], restoring
ms.assetid: 55d5904a-f444-4eb5-abd3-6bc74dd14226
ms.openlocfilehash: d9c2dda2745e7528902b6b1c4f46d17264d1a8d8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666721"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="7255c-102">Nasıl yapılır: Uygulama Oturumları Arasında Uygulama Kapsamı Özelliklerini Koruma ve Geri Yükleme</span><span class="sxs-lookup"><span data-stu-id="7255c-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="7255c-103">Bu örnek, bir uygulama kapandığında uygulama kapsamı özelliklerinin nasıl devam ettirilemeyeceğini ve bir uygulamanın bir sonraki başlatıldığında uygulama kapsamı özelliklerinin nasıl geri yükleneceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="7255c-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7255c-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="7255c-104">Example</span></span>  
 <span data-ttu-id="7255c-105">Uygulama, uygulama kapsamı özelliklerini için devam ettirir ve yalıtılmış depolama alanından geri yükler.</span><span class="sxs-lookup"><span data-stu-id="7255c-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="7255c-106">Yalıtılmış depolama, dosya erişim izni olmayan uygulamalar tarafından güvenli bir şekilde kullanılabilecek, korumalı bir depolama alanıdır.</span><span class="sxs-lookup"><span data-stu-id="7255c-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="7255c-107">*App. xaml* dosyası, ilk Örneğin `App_Startup` vurgulanan satırlarında gösterildiği gibi, yöntemi <xref:System.Windows.Application.Startup?displayProperty=nameWithType> olay işleyicisi olarak ve `App_Exit` <xref:System.Windows.Application.Exit?displayProperty=nameWithType> olay işleyicisi olarak yöntemini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="7255c-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="7255c-108">İkinci örnek, *app.xaml.cs* ve *app. xaml. vb* dosyalarının, uygulama kapsamı özelliklerini geri yükleyen yöntemi ve `App_Startup` `App_Exit` uygulama kapsamını kaydeden yöntemini vurgulayan bir bölümünü gösterir özelliklerinin.</span><span class="sxs-lookup"><span data-stu-id="7255c-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=14-45)]
