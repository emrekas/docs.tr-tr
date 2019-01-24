---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: ff4b1729f1b9fb1d698b4b5b1e3711ce3d27b4db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655562"
---
# <a name="-rootnamespace"></a><span data-ttu-id="10806-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="10806-102">-rootnamespace</span></span>
<span data-ttu-id="10806-103">Tüm tür bildirimleri için bir ad alanını belirtir.</span><span class="sxs-lookup"><span data-stu-id="10806-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10806-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="10806-104">Syntax</span></span>  
  
```  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="10806-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="10806-105">Arguments</span></span>  
  
|<span data-ttu-id="10806-106">Terim</span><span class="sxs-lookup"><span data-stu-id="10806-106">Term</span></span>|<span data-ttu-id="10806-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="10806-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="10806-108">Geçerli proje için tüm tür bildirimleri içine almak, ad alanının adı.</span><span class="sxs-lookup"><span data-stu-id="10806-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10806-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="10806-109">Remarks</span></span>  
 <span data-ttu-id="10806-110">Visual Studio yürütülebilir dosyası (Devenv.exe) oluşturulmuş bir projeyi derlemek için Visual Studio tümleşik geliştirme ortamında kullanım kullanırsanız `-rootnamespace` değerini belirtmek için <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="10806-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="10806-111">Bkz: [Devenv komut satırı anahtarları](/visualstudio/ide/reference/devenv-command-line-switches) daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="10806-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="10806-112">Ortak dil çalışma zamanı MSIL Disassembler kullanın (`Ildasm.exe`), çıkış dosyasında ad alanı adları görüntülemek için.</span><span class="sxs-lookup"><span data-stu-id="10806-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="10806-113">-Rootnamespace Visual Studio tümleşik geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="10806-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="10806-114">1.  Seçili bir projeyi **Çözüm Gezgini**.</span><span class="sxs-lookup"><span data-stu-id="10806-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="10806-115">Üzerinde **proje** menüsünü tıklatın **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="10806-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="10806-116">2.  Tıklayın **uygulama** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="10806-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="10806-117">3.  Değer değiştirme **kök Namespace** kutusu.</span><span class="sxs-lookup"><span data-stu-id="10806-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10806-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="10806-118">Example</span></span>  
 <span data-ttu-id="10806-119">Aşağıdaki kod derlenir `In.vb` ve ad alanındaki tüm tür bildirimleri kapsayan `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="10806-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="10806-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="10806-120">See also</span></span>

- [<span data-ttu-id="10806-121">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="10806-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="10806-122">Ildasm.exe (IL Ayrıştırıcı)</span><span class="sxs-lookup"><span data-stu-id="10806-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="10806-123">Örnek Derleme Komut Satırları</span><span class="sxs-lookup"><span data-stu-id="10806-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
