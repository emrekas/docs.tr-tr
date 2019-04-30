---
title: -pathmap (C# Derleyici Seçenekleri)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 063cee694e8367a86fead2f1258c3cbda5ab7018
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61662601"
---
# <a name="-pathmap-c-compiler-options"></a><span data-ttu-id="6e8fd-102">-pathmap (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="6e8fd-102">-pathmap (C# Compiler Options)</span></span>

<span data-ttu-id="6e8fd-103">**- Pathmap** derleyici seçeneği, fiziksel yollar, derleyici tarafından kaynak yol adları çıktısına eşlemeyle ilgili bilgi belirtir.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-103">The **-pathmap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e8fd-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6e8fd-104">Syntax</span></span>

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a><span data-ttu-id="6e8fd-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="6e8fd-105">Arguments</span></span>

 <span data-ttu-id="6e8fd-106">`path1` Geçerli ortamda kaynak dosyalarının tam yolu</span><span class="sxs-lookup"><span data-stu-id="6e8fd-106">`path1` The full path to the source files in the current environment</span></span>

 <span data-ttu-id="6e8fd-107">`sourcePath1` Kaynak yolu için yerine `path1` herhangi bir çıktı dosyaları içinde.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-107">`sourcePath1` The source path substituted for `path1` in any output files.</span></span>

<span data-ttu-id="6e8fd-108">Birden çok eşleşen kaynak yolları belirlemek için her virgül ile ayırın.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-108">To specify multiple mapped source paths, separate each with a comma.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e8fd-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6e8fd-109">Remarks</span></span>

<span data-ttu-id="6e8fd-110">Derleyici, aşağıdaki nedenlerden dolayı çıktısını kaynak yolu Yazar:</span><span class="sxs-lookup"><span data-stu-id="6e8fd-110">The compiler writes the source path into its output for the following reasons:</span></span>

1. <span data-ttu-id="6e8fd-111">Kaynak yolu için bağımsız değişken yerine zaman <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> için isteğe bağlı parametresi uygulanır.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-111">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="6e8fd-112">Kaynak yolu bir PDB dosyasına eklenir.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-112">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="6e8fd-113">PDB dosyasının yolu (taşınabilir çalıştırılabilir) PE dosyasına eklenir.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-113">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

<span data-ttu-id="6e8fd-114">Bu seçenek derleyici çıktı dosyaları yazılmalıdır karşılık gelen bir yola çalıştırıldığı makine üzerinde her fiziksel yolu eşler.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-114">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span>

## <a name="example"></a><span data-ttu-id="6e8fd-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="6e8fd-115">Example</span></span>

<span data-ttu-id="6e8fd-116">Derleme `t.cs` dizinde **C:\\çalışma\\testleri** ve bu dizine harita **\publish** çıktı:</span><span class="sxs-lookup"><span data-stu-id="6e8fd-116">Compile `t.cs` in the directory **C:\\work\\tests** and map that directory to **\publish** in the output:</span></span>

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a><span data-ttu-id="6e8fd-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6e8fd-117">See also</span></span>

- [<span data-ttu-id="6e8fd-118">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="6e8fd-118">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="6e8fd-119">Proje ve Çözüm Özelliklerini Yönetme</span><span class="sxs-lookup"><span data-stu-id="6e8fd-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
