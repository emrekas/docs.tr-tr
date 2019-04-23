---
title: Genel Derleme Önbelleği
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache)
- ACLs [.NET Framework]
- global assembly cache
- cache [.NET Framework], global assembly cache
- global assembly cache, about
- access control lists [.NET Framework]
ms.assetid: cf5eacd0-d3ec-4879-b6da-5fd5e4372202
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d19410bd83605e6c7325a61e64a32a828846b7df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222581"
---
# <a name="global-assembly-cache"></a><span data-ttu-id="b552c-102">Genel Derleme Önbelleği</span><span class="sxs-lookup"><span data-stu-id="b552c-102">Global Assembly Cache</span></span>
<span data-ttu-id="b552c-103">Ortak dil çalışma zamanının yüklendiği her bilgisayarda, genel derleme önbelleği olarak adlandırılan bir makine düzeyinde kod önbelleği bulunur.</span><span class="sxs-lookup"><span data-stu-id="b552c-103">Each computer where the Common Language Runtime is installed has a machine-wide code cache called the Global Assembly Cache.</span></span> <span data-ttu-id="b552c-104">Özellikle bilgisayarda çeşitli uygulamalar tarafından paylaşılmak üzere belirtilen derlemeleri genel derleme önbelleği depolar.</span><span class="sxs-lookup"><span data-stu-id="b552c-104">The Global Assembly Cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span>  
  
 <span data-ttu-id="b552c-105">Derlemeleri için yalnızca ihtiyacınız olduğunda bunları genel bütünleştirilmiş kod önbelleğine yükleyerek paylaşmalısınız.</span><span class="sxs-lookup"><span data-stu-id="b552c-105">You should share assemblies by installing them into the Global Assembly Cache only when you need to.</span></span> <span data-ttu-id="b552c-106">Genel bir kılavuz olarak derleme bağımlılıklarını özel tutun ve derlemeyi paylaşmanız kesinlikle gerekli olmadığı sürece, derlemeleri uygulama dizinine yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="b552c-106">As a general guideline, keep assembly dependencies private, and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="b552c-107">Ayrıca, derlemeleri COM birlikte çalışma veya yönetilmeyen koda erişilebilir hale getirmek için genel derleme önbelleğine yüklemek gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="b552c-107">In addition, it is not necessary to install assemblies into the Global Assembly Cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b552c-108">Açıkça bir derlemeyi genel bütünleştirilmiş kod önbelleğine yüklemek istediğiniz olmayan senaryolar vardır.</span><span class="sxs-lookup"><span data-stu-id="b552c-108">There are scenarios where you explicitly do not want to install an assembly into the Global Assembly Cache.</span></span> <span data-ttu-id="b552c-109">Genel Derleme Önbelleği uygulamayı oluşturan derlemeleri birini yerleştirirseniz, artık çoğaltmak veya uygulamayı kullanarak yüklemek **xcopy** uygulama dizinini kopyalamak için komutu.</span><span class="sxs-lookup"><span data-stu-id="b552c-109">If you place one of the assemblies that make up an application in the Global Assembly Cache, you can no longer replicate or install the application by using the **xcopy** command to copy the application directory.</span></span> <span data-ttu-id="b552c-110">Derlemeyi de genel derleme önbelleğinde taşımanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b552c-110">You must move the assembly in the Global Assembly Cache as well.</span></span>  
  
 <span data-ttu-id="b552c-111">Bir derlemeyi genel bütünleştirilmiş kod önbelleğine dağıtmak için iki yolu vardır:</span><span class="sxs-lookup"><span data-stu-id="b552c-111">There are two ways to deploy an assembly into the Global Assembly Cache:</span></span>  
  
-   <span data-ttu-id="b552c-112">Genel Derleme Önbelleği ile çalışmak üzere tasarlanmış bir yükleyici kullanın.</span><span class="sxs-lookup"><span data-stu-id="b552c-112">Use an installer designed to work with the Global Assembly Cache.</span></span> <span data-ttu-id="b552c-113">Derlemeleri genel derleme önbelleğine yüklemek için tercih edilen seçenek budur.</span><span class="sxs-lookup"><span data-stu-id="b552c-113">This is the preferred option for installing assemblies into the Global Assembly Cache.</span></span>  
  
-   <span data-ttu-id="b552c-114">Adlı bir geliştirici araç [Genel Derleme Önbelleği aracını (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), tarafından sağlanan [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b552c-114">Use a developer tool called the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b552c-115">Dağıtım senaryolarında, derlemeleri genel derleme önbelleğine yüklemek için Windows Installer kullanın.</span><span class="sxs-lookup"><span data-stu-id="b552c-115">In deployment scenarios, use Windows Installer to install assemblies into the Global Assembly Cache.</span></span> <span data-ttu-id="b552c-116">Bütünleştirilmiş kod başvuru sayımı ve Windows Installer'ı kullanırken, sunulan diğer özellikleri sağlamaz çünkü yalnızca geliştirme senaryolarda, Genel Derleme Önbelleği aracını kullanın.</span><span class="sxs-lookup"><span data-stu-id="b552c-116">Use the Global Assembly Cache tool only in development scenarios, because it does not provide assembly reference counting and other features provided when using the Windows Installer.</span></span>  
  
 <span data-ttu-id="b552c-117">.NET Framework 4 ile başlayarak, genel derleme önbelleği için varsayılan konum olduğu **%windir%\Microsoft.NET\assembly**.</span><span class="sxs-lookup"><span data-stu-id="b552c-117">Starting with the .NET Framework 4, the default location for the Global Assembly Cache is **%windir%\Microsoft.NET\assembly**.</span></span> <span data-ttu-id="b552c-118">Önceki .NET Framework sürümlerinde varsayılan konumdur **%windir%\assembly**.</span><span class="sxs-lookup"><span data-stu-id="b552c-118">In earlier versions of the .NET Framework, the default location is **%windir%\assembly**.</span></span>  
  
 <span data-ttu-id="b552c-119">Yöneticiler, erişim denetimi listesi (ACL) kullanarak yazma denetlemek ve yürütme erişimi systemroot dizinini genellikle koruyun.</span><span class="sxs-lookup"><span data-stu-id="b552c-119">Administrators often protect the systemroot directory using an access control list (ACL) to control write and execute access.</span></span> <span data-ttu-id="b552c-120">Genel bütünleştirilmiş kod önbelleği systemroot dizininin alt dizininde yüklü olduğu için dizinin ACL'sini devralır.</span><span class="sxs-lookup"><span data-stu-id="b552c-120">Because the Global Assembly Cache is installed in a subdirectory of the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="b552c-121">Yalnızca yönetici ayrıcalıklarına sahip kullanıcılar, genel derleme önbelleğinden dosyaları silmek için izin önerilir.</span><span class="sxs-lookup"><span data-stu-id="b552c-121">It is recommended that only users with Administrator privileges be allowed to delete files from the Global Assembly Cache.</span></span>  
  
 <span data-ttu-id="b552c-122">Derlemeleri Genel Derleme Önbelleği'nde dağıtılan bir tanımlayıcı ad olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b552c-122">Assemblies deployed in the Global Assembly Cache must have a strong name.</span></span> <span data-ttu-id="b552c-123">Bir derlemeyi Genel Derleme Önbelleği'ne eklendiğinde, bütünlük kontrolleri derlemeyi oluşturan tüm dosyalar üzerinde gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="b552c-123">When an assembly is added to the Global Assembly Cache, integrity checks are performed on all files that make up the assembly.</span></span> <span data-ttu-id="b552c-124">Önbellek, bir derleme, örneğin, bir dosya değişmiş ancak bildirim değişikliği yansıtmaz oynanmadığını saptayabilmeleri emin olmak için bu bütünlük denetimi gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="b552c-124">The cache performs these integrity checks to ensure that an assembly has not been tampered with, for example, when a file has changed but the manifest does not reflect the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b552c-125">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b552c-125">See also</span></span>

- [<span data-ttu-id="b552c-126">Ortak Dil Çalışma Zamanı Modülündeki Bütünleştirilmiş Kodlar</span><span class="sxs-lookup"><span data-stu-id="b552c-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [<span data-ttu-id="b552c-127">Bütünleştirilmiş Kodlar ve Genel Derleme Önbelleği ile Çalışma</span><span class="sxs-lookup"><span data-stu-id="b552c-127">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="b552c-128">Kesin Adlandırılmış Bütünleştirilmiş Kodlar</span><span class="sxs-lookup"><span data-stu-id="b552c-128">Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/strong-named-assemblies.md)
