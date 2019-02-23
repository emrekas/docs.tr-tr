---
title: -keycontaıner
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 18aa82610d337354647a74d2f4ebe768925e2de0
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746357"
---
# <a name="-keycontainer"></a><span data-ttu-id="8b848-102">-keycontaıner</span><span class="sxs-lookup"><span data-stu-id="8b848-102">-keycontainer</span></span>
<span data-ttu-id="8b848-103">Bir derlemeyi tanımlayıcı bir ad vermek bir anahtar çifti için bir anahtar kapsayıcısı adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="8b848-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b848-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="8b848-104">Syntax</span></span>  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b848-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="8b848-105">Arguments</span></span>  
  
|<span data-ttu-id="8b848-106">Terim</span><span class="sxs-lookup"><span data-stu-id="8b848-106">Term</span></span>|<span data-ttu-id="8b848-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="8b848-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="8b848-108">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="8b848-108">Required.</span></span> <span data-ttu-id="8b848-109">Anahtarı içeren kapsayıcı dosya.</span><span class="sxs-lookup"><span data-stu-id="8b848-109">Container file that contains the key.</span></span> <span data-ttu-id="8b848-110">Dosya adı tırnak içine alın ("") adı boşluk içeriyorsa.</span><span class="sxs-lookup"><span data-stu-id="8b848-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b848-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8b848-111">Remarks</span></span>  
 <span data-ttu-id="8b848-112">Derleyici, derleme bildirimine ortak anahtar ekleyerek ve son derlemeyi özel anahtarla oturum açarak paylaşılabilir bir bileşen oluşturur.</span><span class="sxs-lookup"><span data-stu-id="8b848-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="8b848-113">Bir anahtar dosyası oluşturmak için şunu yazın `sn -k file` komut satırına.</span><span class="sxs-lookup"><span data-stu-id="8b848-113">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="8b848-114">`-i` Seçeneği, bir kapsayıcının içine bir anahtar çifti yükler.</span><span class="sxs-lookup"><span data-stu-id="8b848-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="8b848-115">Daha fazla bilgi için [Sn.exe (tanımlayıcı ad aracı)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="8b848-115">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="8b848-116">Derleme yaparsanız `-target:module`, anahtar dosyasının adını modülünde tutulan ve bir derleme ile derleme yaparken, oluşturulan bütünleştirilmiş dahil [- addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="8b848-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="8b848-117">Bu seçenek özel bir öznitelik belirtebilirsiniz (<xref:System.Reflection.AssemblyKeyNameAttribute>) herhangi bir Microsoft Ara dili (MSIL) modülü için kaynak kodunda.</span><span class="sxs-lookup"><span data-stu-id="8b848-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="8b848-118">Derleyici ile şifreleme bilgilerinizi de geçirebilirsiniz [- keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="8b848-118">You can also pass your encryption information to the compiler with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="8b848-119">Kullanım [- delaysıgn](../../../visual-basic/reference/command-line-compiler/delaysign.md) kısmen imzalı bir derleme istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="8b848-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="8b848-120">Bkz: [bkz](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) derleme imzalama hakkında daha fazla bilgi.</span><span class="sxs-lookup"><span data-stu-id="8b848-120">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b848-121">`-keycontainer` Seçeneği, Visual Studio geliştirme ortamında kullanılabilir değil; yalnızca komut satırından derleme yapılırken kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="8b848-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b848-122">Örnek</span><span class="sxs-lookup"><span data-stu-id="8b848-122">Example</span></span>  
 <span data-ttu-id="8b848-123">Aşağıdaki kod, kaynak dosyasını derler `Input.vb` ve bir anahtar kapsayıcı belirtir.</span><span class="sxs-lookup"><span data-stu-id="8b848-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b848-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8b848-124">See also</span></span>
- [<span data-ttu-id="8b848-125">.NET derlemeleri</span><span class="sxs-lookup"><span data-stu-id="8b848-125">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="8b848-126">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="8b848-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8b848-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="8b848-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="8b848-128">Örnek Derleme Komut Satırları</span><span class="sxs-lookup"><span data-stu-id="8b848-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
