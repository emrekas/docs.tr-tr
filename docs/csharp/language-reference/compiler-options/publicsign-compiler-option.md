---
title: -publicsign (C# Derleyici Seçenekleri)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: de7d9c98b0f279b52bc93711c5b986a2b2e57215
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61662536"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="a4364-102">-publicsign (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="a4364-102">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="a4364-103">Bu seçenek, bir ortak anahtar uygulamak derleyicinin ancak aslında derlemeyi imzalamayı değil.</span><span class="sxs-lookup"><span data-stu-id="a4364-103">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="a4364-104">**- Publicsign** seçeneği de ayarlar biraz derlemesinde çalışma zamanı dosyanın gerçekten imzalı olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="a4364-104">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4364-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a4364-105">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="a4364-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="a4364-106">Arguments</span></span>

<span data-ttu-id="a4364-107">Yok.</span><span class="sxs-lookup"><span data-stu-id="a4364-107">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4364-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a4364-108">Remarks</span></span>

<span data-ttu-id="a4364-109">**- Publicsign** seçeneği kullanılmasını gerektiren [- keyfile](keyfile-compiler-option.md) veya [- keycontaıner](keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a4364-109">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="a4364-110">**Keyfile** veya **keycontainer** seçeneklerini ortak anahtarı belirtin.</span><span class="sxs-lookup"><span data-stu-id="a4364-110">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="a4364-111">**- Publicsign** ve **- delaysıgn** seçenekleri karşılıklı olarak birbirini dışlar.</span><span class="sxs-lookup"><span data-stu-id="a4364-111">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="a4364-112">"Sahte işareti" veya "OSS işareti" olarak da adlandırılır, ortak imzalama çıkış bir derlemede ortak anahtarı içerir ve "imzalı" bayrağını ayarlar, ancak derlemeyi özel anahtarla gerçekten imzalamak değil.</span><span class="sxs-lookup"><span data-stu-id="a4364-112">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="a4364-113">Bu kişiler yayımlanan "tam olarak imzalı" derlemeleri ile uyumludur, ancak derlemeleri imzalamak için kullanılan özel anahtar erişimi olmayan derlemeler oluşturmak istediğiniz açık kaynak projeleri için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="a4364-113">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="a4364-114">Neredeyse hiçbir tüketiciler derleme tam olarak imzalı denetlemek gerçekten gerekli olduğundan, bunlar genel olarak derlenen bütünleştirilmiş kodlarda nerede tam olarak imzalı bir kullanılan neredeyse her senaryoda kendisini adamıştır.</span><span class="sxs-lookup"><span data-stu-id="a4364-114">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a4364-115">Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="a4364-115">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="a4364-116">Açık **özellikleri** proje sayfası.</span><span class="sxs-lookup"><span data-stu-id="a4364-116">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="a4364-117">Değiştirme **gecikme yalnızca oturum** özelliği.</span><span class="sxs-lookup"><span data-stu-id="a4364-117">Modify the **Delay sign only** property.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4364-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a4364-118">See also</span></span>

- [<span data-ttu-id="a4364-119">C# Derleyici - delaysıgn seçeneği</span><span class="sxs-lookup"><span data-stu-id="a4364-119">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)
- [<span data-ttu-id="a4364-120">C# derleyicisi - keyfıle seçeneği</span><span class="sxs-lookup"><span data-stu-id="a4364-120">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="a4364-121">C# Derleyici - keycontaıner seçeneği</span><span class="sxs-lookup"><span data-stu-id="a4364-121">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)
- [<span data-ttu-id="a4364-122">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="a4364-122">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="a4364-123">Proje ve Çözüm Özelliklerini Yönetme</span><span class="sxs-lookup"><span data-stu-id="a4364-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
