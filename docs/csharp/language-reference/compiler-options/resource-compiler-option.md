---
title: -Kaynak (C# Derleyici Seçenekleri)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: ed9f4648ae632786ce860ce2c02637977f709c55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61662445"
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="184d3-102">-Kaynak (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="184d3-102">-resource (C# Compiler Options)</span></span>
<span data-ttu-id="184d3-103">Belirtilen kaynak çıkış dosyasına katıştırır.</span><span class="sxs-lookup"><span data-stu-id="184d3-103">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="184d3-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="184d3-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="184d3-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="184d3-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="184d3-106">Çıkış dosyasına eklemek istediğiniz .NET Framework kaynak dosyası.</span><span class="sxs-lookup"><span data-stu-id="184d3-106">The .NET Framework resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="184d3-107">`identifier` (isteğe bağlı)</span><span class="sxs-lookup"><span data-stu-id="184d3-107">`identifier` (optional)</span></span>  
 <span data-ttu-id="184d3-108">Kaynağın mantıksal adı; Kaynak yüklemek için kullanılan ad.</span><span class="sxs-lookup"><span data-stu-id="184d3-108">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="184d3-109">Dosya adı varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="184d3-109">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="184d3-110">`accessibility-modifier` (isteğe bağlı)</span><span class="sxs-lookup"><span data-stu-id="184d3-110">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="184d3-111">Kaynak erişilebilirliğini: genel veya özel.</span><span class="sxs-lookup"><span data-stu-id="184d3-111">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="184d3-112">Genel varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="184d3-112">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="184d3-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="184d3-113">Remarks</span></span>  
 <span data-ttu-id="184d3-114">Kullanım [- linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) kaynağı için bir derleme bağlama ve kaynak dosyası çıkış dosyasına ekleme.</span><span class="sxs-lookup"><span data-stu-id="184d3-114">Use [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="184d3-115">Varsayılan olarak, C# derleyicisi kullanılarak oluşturulduğunda kaynaklar derleme içinde geneldir.</span><span class="sxs-lookup"><span data-stu-id="184d3-115">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="184d3-116">Kaynakları özel hale getirmek için belirtin `private` erişilebilirlik değiştiricisi olarak.</span><span class="sxs-lookup"><span data-stu-id="184d3-116">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="184d3-117">Dışındaki bir erişilebilirliğe `public` veya `private` izin verilir.</span><span class="sxs-lookup"><span data-stu-id="184d3-117">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="184d3-118">Varsa `filename` , örneğin, tarafından oluşturulmuş bir .NET Framework kaynak dosyası [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) veya geliştirme ortamında üyelerle erişilebileceğini <xref:System.Resources> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="184d3-118">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="184d3-119">Daha fazla bilgi için bkz. <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="184d3-119">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="184d3-120">Diğer tüm kaynaklar için kullanmak `GetManifestResource` yöntemleri <xref:System.Reflection.Assembly> çalışma zamanında kaynağa erişmek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="184d3-120">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="184d3-121">**-res** öğesinin kısa biçimidir **-kaynak**.</span><span class="sxs-lookup"><span data-stu-id="184d3-121">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="184d3-122">Çıkış dosyası kaynakları sırası, komut satırında belirtilen siparişi belirlenir.</span><span class="sxs-lookup"><span data-stu-id="184d3-122">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="184d3-123">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="184d3-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="184d3-124">Bir kaynak dosyası projenize ekleyin.</span><span class="sxs-lookup"><span data-stu-id="184d3-124">Add a resource file to your project.</span></span>  
  
2. <span data-ttu-id="184d3-125">Eklemek istediğiniz dosyayı seçin **Çözüm Gezgini**.</span><span class="sxs-lookup"><span data-stu-id="184d3-125">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3. <span data-ttu-id="184d3-126">Seçin **derleme eylemi** dosya **özellikleri** penceresi.</span><span class="sxs-lookup"><span data-stu-id="184d3-126">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="184d3-127">Ayarlama **derleme eylemi** için **katıştırılmış kaynak**.</span><span class="sxs-lookup"><span data-stu-id="184d3-127">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="184d3-128">Bu derleyici seçeneğini program üzerinden ayarlamak hakkında daha fazla bilgi için bkz. <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span><span class="sxs-lookup"><span data-stu-id="184d3-128">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="184d3-129">Örnek</span><span class="sxs-lookup"><span data-stu-id="184d3-129">Example</span></span>  
 <span data-ttu-id="184d3-130">Derleme `in.cs` ve kaynak dosya ekleme `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="184d3-130">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="184d3-131">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="184d3-131">See also</span></span>

- [<span data-ttu-id="184d3-132">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="184d3-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="184d3-133">Proje ve Çözüm Özelliklerini Yönetme</span><span class="sxs-lookup"><span data-stu-id="184d3-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
