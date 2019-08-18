---
title: Derlemeler Oluşturma
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 314a94be140b392964951299fba2fed4ac7e6e68
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566795"
---
# <a name="creating-assemblies"></a><span data-ttu-id="d7e34-102">Derlemeler Oluşturma</span><span class="sxs-lookup"><span data-stu-id="d7e34-102">Creating Assemblies</span></span>

<span data-ttu-id="d7e34-103">Visual Studio gibi bir IDE veya Windows SDK tarafından sunulan derleyiciler ve araçlar aracılığıyla tek dosyalı veya çok dosyalı derlemeler oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d7e34-103">You can create single-file or multifile assemblies using an IDE, such as Visual Studio, or the compilers and tools provided by the Windows SDK.</span></span> <span data-ttu-id="d7e34-104">En basit derleme basit bir ada sahip tek bir dosyadır ve tek bir uygulama etki alanına yüklenir.</span><span class="sxs-lookup"><span data-stu-id="d7e34-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="d7e34-105">Bu derlemeye, uygulama dizini dışındaki diğer derlemeler tarafından başvurulamaz ve sürüm denetimi çalışmıyor.</span><span class="sxs-lookup"><span data-stu-id="d7e34-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="d7e34-106">Derlemeden oluşan uygulamayı kaldırmak için, bulunduğu dizini silmeniz yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="d7e34-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="d7e34-107">Birçok geliştirici için, bu özelliklere sahip bir derleme, bir uygulamanın dağıtılması için gerekli olan bir derlemedir.</span><span class="sxs-lookup"><span data-stu-id="d7e34-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>

<span data-ttu-id="d7e34-108">Çeşitli kod modüllerinden ve kaynak dosyalarından çok dosyalı bir derleme oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d7e34-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="d7e34-109">Ayrıca, birden çok uygulama tarafından paylaşılabilen bir derleme da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d7e34-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="d7e34-110">Paylaşılan bir derlemenin tanımlayıcı adı olması ve genel derleme önbelleğinde dağıtılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d7e34-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>

<span data-ttu-id="d7e34-111">Aşağıdaki faktörlere bağlı olarak kod modüllerini ve kaynakları derlemeler halinde gruplandırırken çeşitli seçenekleriniz vardır:</span><span class="sxs-lookup"><span data-stu-id="d7e34-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>

- <span data-ttu-id="d7e34-112">Sürüm Oluşturma</span><span class="sxs-lookup"><span data-stu-id="d7e34-112">Versioning</span></span>

     <span data-ttu-id="d7e34-113">Aynı sürüm bilgisine sahip olması gereken grup modülleri.</span><span class="sxs-lookup"><span data-stu-id="d7e34-113">Group modules that should have the same version information.</span></span>

- <span data-ttu-id="d7e34-114">Dağıtım</span><span class="sxs-lookup"><span data-stu-id="d7e34-114">Deployment</span></span>

     <span data-ttu-id="d7e34-115">Dağıtım modelinizi destekleyen grup kodu modülleri ve kaynakları.</span><span class="sxs-lookup"><span data-stu-id="d7e34-115">Group code modules and resources that support your model of deployment.</span></span>

- <span data-ttu-id="d7e34-116">Pencereleri</span><span class="sxs-lookup"><span data-stu-id="d7e34-116">Reuse</span></span>

     <span data-ttu-id="d7e34-117">Bir amaç için mantıksal olarak birlikte kullanılabilen modülleri gruplandırın.</span><span class="sxs-lookup"><span data-stu-id="d7e34-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="d7e34-118">Örneğin, program bakımı için seyrek kullanılan türler ve sınıflardan oluşan bir derleme aynı derlemeye yerleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="d7e34-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="d7e34-119">Ayrıca, birden çok uygulamayla paylaşmayı planladığınız türler bir derlemede gruplandırılmalıdır ve derleme tanımlayıcı bir adla imzalanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d7e34-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>

- <span data-ttu-id="d7e34-120">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="d7e34-120">Security</span></span>

     <span data-ttu-id="d7e34-121">Aynı güvenlik izinleri gerektiren türleri içeren modülleri gruplandırın.</span><span class="sxs-lookup"><span data-stu-id="d7e34-121">Group modules containing types that require the same security permissions.</span></span>

- <span data-ttu-id="d7e34-122">Kapsamlar</span><span class="sxs-lookup"><span data-stu-id="d7e34-122">Scoping</span></span>

     <span data-ttu-id="d7e34-123">Görünürlüğü aynı derleme ile kısıtlanması gereken türler içeren modülleri gruplandırın.</span><span class="sxs-lookup"><span data-stu-id="d7e34-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>

<span data-ttu-id="d7e34-124">Yönetilmeyen COM uygulamaları için ortak dil çalışma zamanı derlemeleri kullanılabilir hale geldiğinde özel hususlar yapılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d7e34-124">Special considerations must be made when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="d7e34-125">Yönetilmeyen kodla çalışma hakkında daha fazla bilgi için bkz. [com 'da .NET Framework bileşenleri gösterme](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="d7e34-125">For more information about working with unmanaged code, see [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7e34-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d7e34-126">See also</span></span>

- [<span data-ttu-id="d7e34-127">Bütünleştirilmiş Kodlarla Programlama</span><span class="sxs-lookup"><span data-stu-id="d7e34-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="d7e34-128">Bütünleştirilmiş Kod Sürümü Oluşturma</span><span class="sxs-lookup"><span data-stu-id="d7e34-128">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)
- [<span data-ttu-id="d7e34-129">Nasıl yapılır: Tek dosya derlemesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="d7e34-129">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)
- [<span data-ttu-id="d7e34-130">Nasıl yapılır: Çoklu dosya derlemesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="d7e34-130">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="d7e34-131">Çalışma Zamanının Bütünleştirilmiş Kodların Konumunu Bulması</span><span class="sxs-lookup"><span data-stu-id="d7e34-131">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="d7e34-132">Çok Dosyalı Bütünleştirilmiş Kodlar</span><span class="sxs-lookup"><span data-stu-id="d7e34-132">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
