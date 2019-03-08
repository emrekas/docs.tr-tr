---
title: İstemci Tarafı Sağlayıcı Derlemesini Kaydetme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- registering client-side provider assemblies
- client-side provider assemblies, registering
- UI Automation, registering provider assemblies
- provider assemblies, registering
ms.assetid: a03af4d9-2771-43cc-b07b-d468dca23190
ms.openlocfilehash: 85f9fd7b7af87a6645a12c7dda313a3e023db298
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674425"
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="4c540-102">İstemci Tarafı Sağlayıcı Derlemesini Kaydetme</span><span class="sxs-lookup"><span data-stu-id="4c540-102">Register a Client-Side Provider Assembly</span></span>
> [!NOTE]
>  <span data-ttu-id="4c540-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="4c540-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4c540-104">En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4c540-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4c540-105">Bu konuda, istemci tarafı UI Otomasyon sağlayıcıları içeren bir DLL kaydettirmek gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="4c540-105">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c540-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="4c540-106">Example</span></span>  
 <span data-ttu-id="4c540-107">Aşağıdaki örnek, bir konsol penceresi için bir sağlayıcı içeren bir derlemeyi kaydettirmek gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="4c540-107">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="4c540-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4c540-108">See also</span></span>
- [<span data-ttu-id="4c540-109">İstemci Tarafı UI Otomasyonu Sağlayıcı Oluşturma</span><span class="sxs-lookup"><span data-stu-id="4c540-109">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
