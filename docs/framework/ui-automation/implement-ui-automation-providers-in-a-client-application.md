---
title: UI Otomasyon Sağlayıcıları İstemci Programına Uygulama
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: b368ab3bc842fda5a99a64e0220093ebd60698b0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105930"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="8d54c-102">UI Otomasyon Sağlayıcıları İstemci Programına Uygulama</span><span class="sxs-lookup"><span data-stu-id="8d54c-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
>  <span data-ttu-id="8d54c-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="8d54c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8d54c-104">En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="8d54c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8d54c-105">Bu konu nasıl bir uygulama içinde istemci tarafı UI Otomasyon sağlayıcısında uygulanacağını gösteren kod örneği içerir.</span><span class="sxs-lookup"><span data-stu-id="8d54c-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="8d54c-106">Bu genel olmayan bir senaryodur.</span><span class="sxs-lookup"><span data-stu-id="8d54c-106">This is an uncommon scenario.</span></span> <span data-ttu-id="8d54c-107">Çoğu zaman bir UI otomasyon istemci uygulaması, sunucu tarafı sağlayıcı ya da bir DLL içinde yer alan istemci tarafı sağlayıcı kullanır.</span><span class="sxs-lookup"><span data-stu-id="8d54c-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d54c-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="8d54c-108">Example</span></span>  
 <span data-ttu-id="8d54c-109">Aşağıdaki kod örneği, bir konsol penceresi için basit bir sağlayıcı uygular.</span><span class="sxs-lookup"><span data-stu-id="8d54c-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="8d54c-110">Kod herhangi bir kullanışlı işlevsellik yok, ancak istemci kodu içinde bir sağlayıcı ayarlama ve kullanarak kaydetme temel adımları göstermek için tasarlanmıştır <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d54c-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="8d54c-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8d54c-111">See also</span></span>

- [<span data-ttu-id="8d54c-112">UI Otomasyonu Sağlayıcılara Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="8d54c-112">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="8d54c-113">İstemci Tarafı Sağlayıcı Bütünleştirilmiş Kodunu Kaydetme</span><span class="sxs-lookup"><span data-stu-id="8d54c-113">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
- [<span data-ttu-id="8d54c-114">İstemci Tarafı UI Otomasyonu Sağlayıcı Oluşturma</span><span class="sxs-lookup"><span data-stu-id="8d54c-114">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
- [<span data-ttu-id="8d54c-115">İstemci Tarafı UI Otomasyonu Sağlayıcıyı Uygulama</span><span class="sxs-lookup"><span data-stu-id="8d54c-115">Client-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)
