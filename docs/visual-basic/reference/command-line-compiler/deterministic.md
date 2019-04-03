---
title: -deterministic
ms.date: 04/11/2018
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
ms.openlocfilehash: d3558976002e273aee239e518f0387033cb82873
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836148"
---
# <a name="-deterministic"></a><span data-ttu-id="c1824-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="c1824-102">-deterministic</span></span>

<span data-ttu-id="c1824-103">Bayt için çıktısı, aynı girişleri için derlemeler arasında özdeş bir derleme oluşturmak derleyicinin neden olur.</span><span class="sxs-lookup"><span data-stu-id="c1824-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="c1824-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c1824-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="c1824-105">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c1824-105">Remarks</span></span>

<span data-ttu-id="c1824-106">Derleyici bir zaman damgası ve rastgele sayı oluşturulan bir GUID ekler olduğundan varsayılan olarak, belirli bir giriş kümesini derleyici çıktısını benzersizdir.</span><span class="sxs-lookup"><span data-stu-id="c1824-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="c1824-107">Kullandığınız `-deterministic` üretmek için seçeneği bir *belirlenimci derlemeyi*, bir giriş aynı kaldığı sürece ikili içeriğe sahip derlemeler arasında aynı.</span><span class="sxs-lookup"><span data-stu-id="c1824-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="c1824-108">Derleyici, aşağıdaki girişleri gerekircilik amacıyla göz önünde bulundurur:</span><span class="sxs-lookup"><span data-stu-id="c1824-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="c1824-109">Komut satırı parametreleri dizisi.</span><span class="sxs-lookup"><span data-stu-id="c1824-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="c1824-110">Derleyicinin .rsp yanıt dosyasının içeriği.</span><span class="sxs-lookup"><span data-stu-id="c1824-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="c1824-111">Kullanılan derleme kesin sürümünü ve onun başvurulmuş derlemeler.</span><span class="sxs-lookup"><span data-stu-id="c1824-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="c1824-112">Geçerli dizin yolu.</span><span class="sxs-lookup"><span data-stu-id="c1824-112">The current directory path.</span></span>
- <span data-ttu-id="c1824-113">Tüm dosyaları ikili içeriğini açıkça derleyici doğrudan veya dolaylı olarak dahil olmak üzere geçirilen:</span><span class="sxs-lookup"><span data-stu-id="c1824-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span> 
    - <span data-ttu-id="c1824-114">Kaynak dosyaları</span><span class="sxs-lookup"><span data-stu-id="c1824-114">Source files</span></span>
    - <span data-ttu-id="c1824-115">Başvurulan derlemeler</span><span class="sxs-lookup"><span data-stu-id="c1824-115">Referenced assemblies</span></span>
    - <span data-ttu-id="c1824-116">Başvurulan modül</span><span class="sxs-lookup"><span data-stu-id="c1824-116">Referenced modules</span></span>
    - <span data-ttu-id="c1824-117">Kaynaklar</span><span class="sxs-lookup"><span data-stu-id="c1824-117">Resources</span></span>
    - <span data-ttu-id="c1824-118">Tanımlayıcı ad anahtar dosyası</span><span class="sxs-lookup"><span data-stu-id="c1824-118">The strong name key file</span></span>
    - <span data-ttu-id="c1824-119">@ yanıt dosyaları</span><span class="sxs-lookup"><span data-stu-id="c1824-119">@ response files</span></span>
    - <span data-ttu-id="c1824-120">Çözümleyiciler</span><span class="sxs-lookup"><span data-stu-id="c1824-120">Analyzers</span></span>
    - <span data-ttu-id="c1824-121">Rulesets</span><span class="sxs-lookup"><span data-stu-id="c1824-121">Rulesets</span></span>
    - <span data-ttu-id="c1824-122">Çözümleyiciler tarafından kullanılan ek dosyalar</span><span class="sxs-lookup"><span data-stu-id="c1824-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="c1824-123">Geçerli kültür (hangi tanılama ve özel durum iletileri üretilir dilin).</span><span class="sxs-lookup"><span data-stu-id="c1824-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="c1824-124">Varsayılan kodlama (veya mevcut kod sayfasında) kodlama belirtilmezse.</span><span class="sxs-lookup"><span data-stu-id="c1824-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="c1824-125">Varlığı, var olmayan ve derleyicinin arama yolları dosya içeriklerini (örneğin, tarafından belirtilen `/lib` veya `/recurse`).</span><span class="sxs-lookup"><span data-stu-id="c1824-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="c1824-126">Derleyici çalıştığı CLR platform.</span><span class="sxs-lookup"><span data-stu-id="c1824-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="c1824-127">Değerini `%LIBPATH%`, çözümleyici bağımlılık yükleniyor etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="c1824-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="c1824-128">Kaynakları genel kullanıma açık olduğunda, belirlenimci derlemeyi güvenilir bir kaynaktan bir ikili derlenmiş olup olmadığını kurmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c1824-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="c1824-129">Ayrıca bir ikili değişiklikleri bağımlı derleme adımları yürütülecek gerekip gerekmediğini belirlemek için bir sürekli derleme sistemi de yararlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="c1824-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="c1824-130">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c1824-130">See also</span></span>

- [<span data-ttu-id="c1824-131">Visual Basic komut satırı derleyicisi</span><span class="sxs-lookup"><span data-stu-id="c1824-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c1824-132">Örnek Derleme Komut Satırları</span><span class="sxs-lookup"><span data-stu-id="c1824-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
