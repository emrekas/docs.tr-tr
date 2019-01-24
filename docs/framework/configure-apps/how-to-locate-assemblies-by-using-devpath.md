---
title: 'Nasıl yapılır: DEVPATH kullanarak derlemelerin bulun'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 11ed84b01adf57eb526eaa1e71c6968e48c64cc2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627557"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="5a3c3-102">Nasıl yapılır: DEVPATH kullanarak derlemelerin bulun</span><span class="sxs-lookup"><span data-stu-id="5a3c3-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="5a3c3-103">Geliştiriciler, oluşturmakta olduğunuz paylaşılan bir derleme birden çok uygulama ile doğru şekilde çalıştığından emin olmak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="5a3c3-104">Geliştirme döngüsü sırasında genel derleme önbelleğinde sürekli derleme almak yerine Geliştirici derlemesi için derleme çıktı dizinine işaret eden bir DEVPATH ortam değişkeni oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="5a3c3-105">Örneğin, MySharedAssembly adlı paylaşılan bir derleme oluşturuyorsanız ve çıkış dizini C:\MySharedAssembly\Debug olduğunu varsayın.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="5a3c3-106">DEVPATH değişkeninde C:\MySharedAssembly\Debug koyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="5a3c3-107">Ardından belirtmelisiniz [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) makine yapılandırma dosyasındaki öğesi.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="5a3c3-108">Bu öğe DEVPATH derlemeleri bulmak için kullanılacak ortak dil çalışma zamanı söyler.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="5a3c3-109">Paylaşılan derleme çalışma zamanı tarafından bulunabilir olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="5a3c3-110">Bütünleştirilmiş kod başvuruları kullanımı çözümlemek için özel bir dizin belirtmek için [ \<codeBase > öğesi](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) veya [ \<yoklama > öğesi](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) bölümünde anlatıldığı gibi bir yapılandırma dosyası [Bir derlemenin konumunu belirtme](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="5a3c3-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="5a3c3-111">Ayrıca, uygulama dizininin bir alt dizinde derleme koyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="5a3c3-112">Daha fazla bilgi için [çalışma zamanı derlemeleri nasıl konumlandırır](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="5a3c3-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a3c3-113">Yalnızca geliştirme için hedeflenen bir Gelişmiş özelliğinin budur.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="5a3c3-114">Aşağıdaki örnek, çalışma zamanı derlemeleri DEVPATH ortam değişkeni tarafından belirtilen dizinlerde arama gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a3c3-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="5a3c3-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="5a3c3-116">Bu ayar varsayılan olarak false.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a3c3-117">Yalnızca geliştirme sırasında bu ayarı kullanın.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-117">Use this setting only at development time.</span></span> <span data-ttu-id="5a3c3-118">Çalışma zamanı, tanımlayıcı adlı derlemeler DEVPATH içinde bulunan sürümlerinde denetlemez.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="5a3c3-119">Yalnızca bulduğu ilk derlemeyi de kullanır.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a3c3-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5a3c3-120">See also</span></span>
- [<span data-ttu-id="5a3c3-121">.NET Framework uygulamalarını yapılandırma</span><span class="sxs-lookup"><span data-stu-id="5a3c3-121">Configuring .NET Framework Apps</span></span>](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
