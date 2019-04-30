---
title: -win32icon (C# Derleyici Seçenekleri)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: 7bc7da8121ec1190908d9b94fc7c987f9888c020
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61662250"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="8b0ac-102">-win32icon (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="8b0ac-102">-win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="8b0ac-103">**-Win32icon** seçeneği çıktı dosyasına dosya Gezgini'nde istenen görünümü verir çıkış dosyasına bir .ico simge dosyası ekler.</span><span class="sxs-lookup"><span data-stu-id="8b0ac-103">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b0ac-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="8b0ac-104">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b0ac-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="8b0ac-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="8b0ac-106">Çıkış dosyanızı eklemek istediğiniz .ico dosyası.</span><span class="sxs-lookup"><span data-stu-id="8b0ac-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b0ac-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8b0ac-107">Remarks</span></span>  
 <span data-ttu-id="8b0ac-108">Bir .ico simge dosyası ile oluşturulan [kaynak derleyici](/windows/desktop/menurc/resource-compiler).</span><span class="sxs-lookup"><span data-stu-id="8b0ac-108">An .ico file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="8b0ac-109">Kaynak derleyicisi, bir Visual C++ programını derlerken çağrılır; .rc dosyasından bir .ico simge dosyası oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="8b0ac-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="8b0ac-110">Bkz: [- linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (için başvuru) veya [-kaynak](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (eklemek için) bir .NET Framework kaynak dosyası.</span><span class="sxs-lookup"><span data-stu-id="8b0ac-110">See [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="8b0ac-111">Bkz: [-win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) bir .res dosyası içeri aktarmak için.</span><span class="sxs-lookup"><span data-stu-id="8b0ac-111">See [-win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="8b0ac-112">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="8b0ac-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="8b0ac-113">Projenin açın **özellikleri** sayfaları.</span><span class="sxs-lookup"><span data-stu-id="8b0ac-113">Open the project's **Properties** pages.</span></span>  
  
2. <span data-ttu-id="8b0ac-114">Tıklayın **uygulama** özellik sayfası.</span><span class="sxs-lookup"><span data-stu-id="8b0ac-114">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="8b0ac-115">Değiştirme **uygulama simgesi** özelliği.</span><span class="sxs-lookup"><span data-stu-id="8b0ac-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="8b0ac-116">Bu derleyici seçeneğini program üzerinden ayarlamak konusunda daha fazla bilgi için bkz: <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="8b0ac-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b0ac-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="8b0ac-117">Example</span></span>  
 <span data-ttu-id="8b0ac-118">Derleme `in.cs` ve bir .ico simge dosyası ekleme `rf.ico` üretmek için `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="8b0ac-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b0ac-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8b0ac-119">See also</span></span>

- [<span data-ttu-id="8b0ac-120">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="8b0ac-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="8b0ac-121">Proje ve Çözüm Özelliklerini Yönetme</span><span class="sxs-lookup"><span data-stu-id="8b0ac-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
