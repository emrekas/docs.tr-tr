---
title: 'Nasıl yapılır: Uygulama Etki Alanını Yapılandırma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe0c7ecf1b0daf0e9ea56ec590083fe1ccd2d693
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705616"
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="40a3f-102">Nasıl yapılır: Uygulama Etki Alanını Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="40a3f-102">How to: Configure an Application Domain</span></span>
<span data-ttu-id="40a3f-103">Ortak dil çalışma zamanı kullanarak yeni bir uygulama etki alanı için yapılandırma bilgilerini sağlayabilir <xref:System.AppDomainSetup> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="40a3f-103">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="40a3f-104">Kendi uygulama etki alanları oluştururken, en önemli özelliği <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="40a3f-104">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="40a3f-105">Diğer **AppDomainSetup** özellikleri, belirli bir uygulama etki alanını yapılandırmak için temel olarak çalışma zamanı ana bilgisayarları tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="40a3f-105">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="40a3f-106">**ApplicationBase** uygulamanın kök dizin özelliği tanımlar.</span><span class="sxs-lookup"><span data-stu-id="40a3f-106">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="40a3f-107">Çalışma zamanı türü isteği karşılamak gerektiğinde türü tarafından belirtilen dizindeki içeren derleme yoklamaları **ApplicationBase** özelliği.</span><span class="sxs-lookup"><span data-stu-id="40a3f-107">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40a3f-108">Yeni bir uygulama etki alanı yalnızca devralınan **ApplicationBase** Oluşturucusu özelliği.</span><span class="sxs-lookup"><span data-stu-id="40a3f-108">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="40a3f-109">Aşağıdaki örnek, bir örneğini oluşturur. **AppDomainSetup** sınıfının yeni bir uygulama etki alanı oluşturmak için bu sınıfın kullandığı, bilgileri konsola yazar ve ardından uygulama etki alanını kaldırır.</span><span class="sxs-lookup"><span data-stu-id="40a3f-109">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40a3f-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="40a3f-110">Example</span></span>  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="40a3f-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="40a3f-111">See also</span></span>

- [<span data-ttu-id="40a3f-112">Uygulama etki alanlarıyla programlama</span><span class="sxs-lookup"><span data-stu-id="40a3f-112">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="40a3f-113">Uygulama Etki Alanlarını Kullanma</span><span class="sxs-lookup"><span data-stu-id="40a3f-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
