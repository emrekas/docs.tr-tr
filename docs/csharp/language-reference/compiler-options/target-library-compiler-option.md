---
title: '-target: library (C# Derleyici Seçenekleri)'
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 2e0935965e9225ab524290429803fe4c9ccc80c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61662380"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="9da19-102">-target: library (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="9da19-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="9da19-103">**-Target: library** seçeneği bir yürütülebilir dosya (EXE) yerine bir dinamik bağlantı kitaplığı (DLL) oluşturmak derleyicinin neden olur.</span><span class="sxs-lookup"><span data-stu-id="9da19-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da19-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9da19-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="9da19-105">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9da19-105">Remarks</span></span>  
 <span data-ttu-id="9da19-106">DLL, .dll uzantısıyla oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="9da19-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="9da19-107">İle aksi belirtilmediği sürece [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) seçeneği, çıkış dosyası adı ilk giriş dosyasının adını alır.</span><span class="sxs-lookup"><span data-stu-id="9da19-107">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="9da19-108">Tüm komut satırında belirtildiğinde kadar sonraki dosyalar **-out** veya **-target: module** seçeneği .dll dosyası oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="9da19-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="9da19-109">Bir .dll dosyası oluştururken bir [ana](../../../csharp/programming-guide/main-and-command-args/index.md) yöntemi gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="9da19-109">When building a .dll file, a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="9da19-110">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="9da19-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="9da19-111">Projenin açın **özellikleri** sayfası.</span><span class="sxs-lookup"><span data-stu-id="9da19-111">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="9da19-112">Tıklayın **uygulama** özellik sayfası.</span><span class="sxs-lookup"><span data-stu-id="9da19-112">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="9da19-113">Değiştirme **çıkış türü** özelliği.</span><span class="sxs-lookup"><span data-stu-id="9da19-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="9da19-114">Bu derleyici seçeneğini program üzerinden ayarlamak konusunda daha fazla bilgi için bkz: <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="9da19-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9da19-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="9da19-115">Example</span></span>  
 <span data-ttu-id="9da19-116">Derleme `in.cs`, oluşturma `in.dll`:</span><span class="sxs-lookup"><span data-stu-id="9da19-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="9da19-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9da19-117">See also</span></span>

- [<span data-ttu-id="9da19-118">-target (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="9da19-118">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="9da19-119">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="9da19-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
