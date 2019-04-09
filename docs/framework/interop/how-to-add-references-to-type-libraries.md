---
title: 'Nasıl yapılır: Tür Kitaplıklarına Başvurular Ekleme'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dab83be5250cd68348c860c4aff7991ec7655648
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172048"
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="2a9d5-102">Nasıl yapılır: Tür Kitaplıklarına Başvurular Ekleme</span><span class="sxs-lookup"><span data-stu-id="2a9d5-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="2a9d5-103">Visual Studio, bir tür kitaplığına bir başvuru eklediğinizde, meta verileri içeren bir birlikte çalışma derlemesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="2a9d5-104">Visual Studio, bir birincil birlikte çalışma derlemesi varsa, yeni bir birlikte çalışma bütünleştirilmiş kodu oluşturuluyor önce mevcut bütünleştirilmiş kodu kullanır.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="2a9d5-105">Visual Studio'da bir tür kitaplığına bir başvuru eklemek için</span><span class="sxs-lookup"><span data-stu-id="2a9d5-105">To add a reference to a type library in Visual Studio</span></span>  
  
1.  <span data-ttu-id="2a9d5-106">Bir Windows Setup.exe dosyasını yükleme sizin için gerçekleştirir, bilgisayarınızda COM DLL veya EXE dosyasının yükleyin.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2.  <span data-ttu-id="2a9d5-107">Seçin **proje**, **Başvurusu Ekle**.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-107">Choose **Project**, **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="2a9d5-108">Başvuru Yöneticisi'nde seçin **COM**.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-108">In the Reference Manager, choose **COM**.</span></span>  
  
4.  <span data-ttu-id="2a9d5-109">Tür kitaplığını listeden seçin veya .tlb dosyasına göz at.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5.  <span data-ttu-id="2a9d5-110">**Tamam**’ı seçin.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-110">Choose **OK**.</span></span>  
  
6.  <span data-ttu-id="2a9d5-111">Çözüm Gezgini içinde eklenen yeni başvuru için kısayol menüsünü açın ve ardından **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7.  <span data-ttu-id="2a9d5-112">İçinde **özellikleri** penceresinde emin **birlikte çalışma türlerini katıştır** özelliği **True**.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="2a9d5-113">Bu, uygulamanız ile birincil birlikte çalışma derlemelerini dağıtma gereksinimini ortadan kaldıran, yürütülebilir dosyaları, COM türleri için tür bilgisi katıştırma Visual Studio neden olur.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a9d5-114">Menü ve iletişim kutusu seçenekleri, kullanmakta olduğunuz Visual Studio sürümüne bağlı olarak değişiklik gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="2a9d5-115">Komut satırı derlemesi için bir tür kitaplığına bir başvuru eklemek için</span><span class="sxs-lookup"><span data-stu-id="2a9d5-115">To add a reference to a type library for command-line compilation</span></span>  
  
1.  <span data-ttu-id="2a9d5-116">Birlikte çalışma derlemesi açıklandığı gibi oluşturmak [nasıl yapılır: Tür kitaplıklarından birlikte çalışma derlemeleri oluşturma](how-to-generate-interop-assemblies-from-type-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="2a9d5-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2.  <span data-ttu-id="2a9d5-117">Kullanım [/link (C# derleyici seçenekleri)](../../csharp/language-reference/compiler-options/link-compiler-option.md) veya [/Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) COM için tür bilgilerini katıştırma derleyici seçeneğiyle birlikte çalışma bütünleştirilmiş kod adı, yürütülebilir dosyaların türleri.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-117">Use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9d5-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2a9d5-118">See also</span></span>

- [<span data-ttu-id="2a9d5-119">Tür Kitaplığını Derleme Olarak İçeri Aktarma</span><span class="sxs-lookup"><span data-stu-id="2a9d5-119">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="2a9d5-120">COM Bileşenlerini .NET Framework'te Gösterme</span><span class="sxs-lookup"><span data-stu-id="2a9d5-120">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="2a9d5-121">İzlenecek yol: Yönetilen derlemeler Visual Studio'da türler katıştırma (C#)</span><span class="sxs-lookup"><span data-stu-id="2a9d5-121">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](/docs/csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) 
- [<span data-ttu-id="2a9d5-122">İzlenecek yol: Visual Studio'da (Visual Basic) yönetilen derlemelerden türler katıştırma</span><span class="sxs-lookup"><span data-stu-id="2a9d5-122">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>](/docs/visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [<span data-ttu-id="2a9d5-123">/link (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="2a9d5-123">/link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="2a9d5-124">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a9d5-124">/link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
