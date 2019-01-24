---
title: Windows Store uygulamaları için .NET için MEF
ms.date: 03/30/2017
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2c6f28a88c709c27df82250fcbdc22de210e93a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663303"
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="efd09-102">Windows Store uygulamaları için .NET için MEF</span><span class="sxs-lookup"><span data-stu-id="efd09-102">MEF for .NET for Windows Store Apps</span></span>
<span data-ttu-id="efd09-103"><xref:System.Composition?displayProperty=nameWithType> ve bunun alt ad alanları içeren geliştirmek için türler Genişletilebilir [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulamalar Yönetilen Genişletilebilirlik Çerçevesi (MEF) ile.</span><span class="sxs-lookup"><span data-stu-id="efd09-103"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="efd09-104">Bu ad alanları parçası olan [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] alt kümesi için [!INCLUDE[win8](../../../includes/win8-md.md)] işletim sistemi.</span><span class="sxs-lookup"><span data-stu-id="efd09-104">These namespaces are part of the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subset for the [!INCLUDE[win8](../../../includes/win8-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="efd09-105">Bu ad alanları .NET Framework ile dağıtılan çekirdek sınıf kitaplığının bir parçası değildir.</span><span class="sxs-lookup"><span data-stu-id="efd09-105">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="efd09-106">Bu ad alanlarını yüklemek için projenizi Visual Studio'da açın, **NuGet paketlerini Yönet** gelen **proje** menü ve çevrimiçi Microsoft.birleştirme paketini arayın.</span><span class="sxs-lookup"><span data-stu-id="efd09-106">To install these namespaces, open your project in Visual Studio, choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
-   <span data-ttu-id="efd09-107"><xref:System.Composition?displayProperty=nameWithType> MEF çekirdek oluşturan sınıfları sağlar için [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] uygulamalar.</span><span class="sxs-lookup"><span data-stu-id="efd09-107"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
-   <span data-ttu-id="efd09-108"><xref:System.Composition.Convention?displayProperty=nameWithType> bir kural tabanlı yapılandırma modeli ile MEF kullanma destekleyen türler sağlar.</span><span class="sxs-lookup"><span data-stu-id="efd09-108"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
-   <span data-ttu-id="efd09-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> ana bilgisayar uygulaması geliştiricileri için yararlı olan MEF türler sağlar.</span><span class="sxs-lookup"><span data-stu-id="efd09-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
-   <span data-ttu-id="efd09-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> bileşim motoru tarafından dahili olarak kullanılan MEF türler sağlar.</span><span class="sxs-lookup"><span data-stu-id="efd09-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="efd09-111">Hakkında daha fazla bilgi için [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] ve ad alanları ve içerdiği türleri listesini görmek [.NET için Windows Store uygulamalarına genel bakış](https://go.microsoft.com/fwlink/p/?LinkID=238312) Windows geliştirme Merkezi'nde.</span><span class="sxs-lookup"><span data-stu-id="efd09-111">For more information about [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](https://go.microsoft.com/fwlink/p/?LinkID=238312) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd09-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="efd09-112">See also</span></span>
- [<span data-ttu-id="efd09-113">.NET için Windows Store uygulamalarına genel bakış</span><span class="sxs-lookup"><span data-stu-id="efd09-113">.NET for Windows Store apps overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=238312)
- [<span data-ttu-id="efd09-114">.NET için Windows Store uygulamaları – desteklenen API'ler</span><span class="sxs-lookup"><span data-stu-id="efd09-114">.NET for Windows Store apps – supported APIs</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=247912)
- [<span data-ttu-id="efd09-115">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="efd09-115">Managed Extensibility Framework (MEF)</span></span>](../../../docs/framework/mef/index.md)
