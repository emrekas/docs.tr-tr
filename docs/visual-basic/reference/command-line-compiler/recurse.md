---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 2fe1834c3e92c3eff016ffd7857a0473eb2e8b3a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816427"
---
# <a name="-recurse"></a><span data-ttu-id="60818-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="60818-102">-recurse</span></span>
<span data-ttu-id="60818-103">Belirtilen dizin veya proje dizininin tüm alt dizinlerdeki kaynak kodu dosyaları derler.</span><span class="sxs-lookup"><span data-stu-id="60818-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60818-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="60818-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="60818-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="60818-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="60818-106">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="60818-106">Optional.</span></span> <span data-ttu-id="60818-107">Aramayı başlatmak istediğiniz dizin.</span><span class="sxs-lookup"><span data-stu-id="60818-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="60818-108">Belirtilmemişse, arama proje dizininde başlar.</span><span class="sxs-lookup"><span data-stu-id="60818-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="60818-109">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="60818-109">Required.</span></span> <span data-ttu-id="60818-110">Aranacak dosya.</span><span class="sxs-lookup"><span data-stu-id="60818-110">The file(s) to search for.</span></span> <span data-ttu-id="60818-111">Joker karakterlere izin verilir.</span><span class="sxs-lookup"><span data-stu-id="60818-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60818-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="60818-112">Remarks</span></span>  
 <span data-ttu-id="60818-113">Proje dizininde eşleşen tüm dosyaları kullanmadan derlemek için bir dosya adında joker karakterler kullanabilirsiniz `-recurse`.</span><span class="sxs-lookup"><span data-stu-id="60818-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="60818-114">Hiçbir çıkış dosyası adı belirtilirse, derleyicinin işlenen ilk giriş dosyasının çıkış dosya adını alır.</span><span class="sxs-lookup"><span data-stu-id="60818-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="60818-115">Bu genellikle ilk görüntülendiğinde alfabetik olarak derlenmiş dosyalar listesinden dosyasıdır.</span><span class="sxs-lookup"><span data-stu-id="60818-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="60818-116">Bu nedenle, bir çıkış dosyası kullanarak belirtmek en iyi `-out` seçeneği.</span><span class="sxs-lookup"><span data-stu-id="60818-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60818-117">`-recurse` Seçeneği, Visual Studio geliştirme ortamında kullanılabilir değil; yalnızca komut satırından derleme yapılırken kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="60818-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60818-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="60818-118">Example</span></span>  
 <span data-ttu-id="60818-119">Aşağıdaki komut, geçerli dizindeki tüm Visual Basic dosyaları derler.</span><span class="sxs-lookup"><span data-stu-id="60818-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="60818-120">Aşağıdaki komut, tüm Visual Basic dosyaları derler `Test\ABC` dizin ve altındaki dizinleri ve ardından oluşturur `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="60818-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="60818-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="60818-121">See also</span></span>

- [<span data-ttu-id="60818-122">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="60818-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="60818-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60818-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="60818-124">Örnek Derleme Komut Satırları</span><span class="sxs-lookup"><span data-stu-id="60818-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
