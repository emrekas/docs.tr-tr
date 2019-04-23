---
title: -keyfile (C# Derleyici Seçenekleri)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: 3e11cbca004aedd7d4f992abf2f766de4f4f5935
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344656"
---
# <a name="-keyfile-c-compiler-options"></a><span data-ttu-id="0d2c3-102">-keyfile (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="0d2c3-102">-keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="0d2c3-103">Şifreleme anahtarını içeren dosya adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-103">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d2c3-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0d2c3-104">Syntax</span></span>  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d2c3-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="0d2c3-105">Arguments</span></span>  
  
|<span data-ttu-id="0d2c3-106">Terim</span><span class="sxs-lookup"><span data-stu-id="0d2c3-106">Term</span></span>|<span data-ttu-id="0d2c3-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="0d2c3-107">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="0d2c3-108">Tanımlayıcı ad anahtarını içeren dosyanın adı.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-108">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d2c3-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0d2c3-109">Remarks</span></span>  
 <span data-ttu-id="0d2c3-110">Bu seçenek kullanıldığında, derleyici ortak anahtarı derleme bildirimine belirtilen dosyadan ekler ve ardından son derlemeyi özel anahtarla imzalar.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-110">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="0d2c3-111">Bir anahtar dosyası oluşturmak için sn -k türü `file` komut satırına.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-111">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="0d2c3-112">Derleme yaparsanız **-target: module**, anahtar dosyasının adını modülünde tutulan ve bir derleme ile derleme yaparken, oluşturulan bütünleştirilmiş dahil [- addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0d2c3-112">If you compile with **-target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="0d2c3-113">Derleyici ile şifreleme bilgilerinizi de geçirebilirsiniz [- keycontaıner](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0d2c3-113">You can also pass your encryption information to the compiler with [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span> <span data-ttu-id="0d2c3-114">Kullanım [- delaysıgn](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) kısmen imzalı bir derleme istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-114">Use [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="0d2c3-115">-Keyfile hem - keycontaıner (komut satırı seçeneği veya özel öznitelik) aynı derlemede belirtilmesi durumunda, derleyici önce anahtar kapsayıcısı deneyin.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-115">In case both -keyfile and -keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="0d2c3-116">Bu başarılı olursa derleme anahtar kapsayıcısındaki bilgilerle imzalanır.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-116">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="0d2c3-117">Derleyicinin anahtar kapsayıcısını bulamazsa, - keyfile ile belirtilen dosyayı çalışacaktır.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-117">If the compiler does not find the key container, it will try the file specified with -keyfile.</span></span> <span data-ttu-id="0d2c3-118">Bu başarılı olursa derleme anahtar dosyası içindeki bilgilerle imzalanır ve anahtar bilgileri anahtar kapsayıcısının içine yüklenir (sn benzer -i) ve böylece sonraki derlemede, anahtar kapsayıcısı geçerli olacaktır.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-118">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="0d2c3-119">Bir anahtar dosyası yalnızca ortak anahtar içerebileceğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-119">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="0d2c3-120">Daha fazla bilgi için [bkz](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) ve [derlemeyi imzalamayı geciktirme](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="0d2c3-120">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0d2c3-121">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="0d2c3-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="0d2c3-122">Açık **özellikleri** proje sayfası.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-122">Open the **Properties** page for the project.</span></span>  
  
2. <span data-ttu-id="0d2c3-123">Tıklayın **imzalama** özellik sayfası.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-123">Click the **Signing** property page.</span></span>  
  
3. <span data-ttu-id="0d2c3-124">Değiştirme **bir tanımlayıcı ad anahtar dosyası seç** özelliği.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-124">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="0d2c3-125">Bu derleyici seçeneği ile program aracılığıyla erişebileceğiniz <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-125">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d2c3-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0d2c3-126">See also</span></span>

- [<span data-ttu-id="0d2c3-127">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="0d2c3-127">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="0d2c3-128">Proje ve Çözüm Özelliklerini Yönetme</span><span class="sxs-lookup"><span data-stu-id="0d2c3-128">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
