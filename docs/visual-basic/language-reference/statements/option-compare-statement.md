---
title: Option Compare deyimi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Compare
- vb.OptionCompare
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword [Visual Basic]
- binary comparison [Visual Basic]
- strings [Visual Basic], returning from functions
- binary comparison [Visual Basic], Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword [Visual Basic], Option Compare statement
- Binary keyword [Visual Basic], Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement [Visual Basic]
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
ms.openlocfilehash: e7c1e8e4431b7a653bb3a086589c35921f8001b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024748"
---
# <a name="option-compare-statement"></a><span data-ttu-id="ab621-102">Option Compare Deyimi</span><span class="sxs-lookup"><span data-stu-id="ab621-102">Option Compare Statement</span></span>
<span data-ttu-id="ab621-103">Dize verileri karşılaştırılırken kullanılan varsayılan karşılaştırma yöntemini bildirir.</span><span class="sxs-lookup"><span data-stu-id="ab621-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab621-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ab621-104">Syntax</span></span>  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="ab621-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="ab621-105">Parts</span></span>  
  
|<span data-ttu-id="ab621-106">Terim</span><span class="sxs-lookup"><span data-stu-id="ab621-106">Term</span></span>|<span data-ttu-id="ab621-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="ab621-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="ab621-108">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="ab621-108">Optional.</span></span> <span data-ttu-id="ab621-109">Dize karşılaştırmaları karakterlerin dahili ikili gösterimi türetilmiş bir sıralama düzeni göre sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="ab621-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="ab621-110">Bu karşılaştırma türünü dizeler metin olarak yorumlanacağını olmayan karakterler içeren özellikle yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="ab621-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="ab621-111">Bu durumda, eğilim karşılaştırmalar büyük/küçük harf duyarsızlığı gibi alfabetik eşitliğini için istemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="ab621-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="ab621-112">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="ab621-112">Optional.</span></span> <span data-ttu-id="ab621-113">Dize karşılaştırmaları büyük/küçük harfe metin sıralama düzeni, sisteminizin yerel ayarı tarafından belirlenen göre sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="ab621-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="ab621-114">Bu tür bir karşılaştırma dizeleri, tüm metin karakterleri ve hesabı gibi büyük/küçük harfe ve yakından ilgili harf alfabetik denklikleri alırken Karşılaştırılacak istiyorsanız kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="ab621-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="ab621-115">Örneğin, düşünmek isteyebilirsiniz `A` ve `a` eşit olmasını ve `Ä` ve `ä` önce gelmesi `B` ve `b`.</span><span class="sxs-lookup"><span data-stu-id="ab621-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab621-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ab621-116">Remarks</span></span>  
 <span data-ttu-id="ab621-117">Kullandıysanız, `Option Compare` deyimi, bir dosyada başka bir kaynak kod deyimlerini önce görünmelidir.</span><span class="sxs-lookup"><span data-stu-id="ab621-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="ab621-118">`Option Compare` Deyimi dize karşılaştırma yöntemini belirtir (`Binary` veya `Text`).</span><span class="sxs-lookup"><span data-stu-id="ab621-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="ab621-119">Varsayılan metin karşılaştırma yöntemi: `Binary`.</span><span class="sxs-lookup"><span data-stu-id="ab621-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="ab621-120">A `Binary` karşılaştırması, her dizedeki her karakterin sayısal Unicode değerini karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="ab621-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="ab621-121">A `Text` karşılaştırma, sözcük anlamını geçerli kültüründeki göre her bir Unicode karakter karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="ab621-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="ab621-122">Microsoft Windows içinde sıralama düzeni kod sayfası tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="ab621-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="ab621-123">Daha fazla bilgi için [kod sayfaları](/cpp/c-runtime-library/code-pages).</span><span class="sxs-lookup"><span data-stu-id="ab621-123">For more information, see [Code Pages](/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="ab621-124">Aşağıdaki örnekte, İngilizce/Avrupa kod sayfası (ANSI 1252) karakterleri kullanılarak sıralanır `Option Compare Binary`, tipik ikili sıralama düzeninde üretir.</span><span class="sxs-lookup"><span data-stu-id="ab621-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="ab621-125">Ne zaman aynı aynı kod sayfasında karakter sıralanır kullanarak `Option Compare Text`, aşağıdaki metni sıralama düzeninin üretilir.</span><span class="sxs-lookup"><span data-stu-id="ab621-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="ab621-126">Bir seçenek karşılaştırırken deyimi mevcut değil</span><span class="sxs-lookup"><span data-stu-id="ab621-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="ab621-127">Kaynak kodu içermiyorsa bir `Option Compare` deyimi **Option Compare** ayarını [derleme sayfası, Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ab621-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="ab621-128">Komut satırı derleyicisini kullanmak, ayarı tarafından belirtilen [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) derleyici seçeneği kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ab621-128">If you use the command-line compiler, the setting specified by the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="ab621-129">Option Compare IDE içinde ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="ab621-129">To set Option Compare in the IDE</span></span>  
  
1. <span data-ttu-id="ab621-130">İçinde **Çözüm Gezgini**, bir proje seçin.</span><span class="sxs-lookup"><span data-stu-id="ab621-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="ab621-131">Üzerinde **proje** menüsünü tıklatın **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="ab621-131">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="ab621-132">Tıklayın **derleme** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="ab621-132">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="ab621-133">Değer kümesindeki **Option Compare** kutusu.</span><span class="sxs-lookup"><span data-stu-id="ab621-133">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="ab621-134">Bir proje oluşturduğunuzda **Option Compare** ayarını **derleme** sekmesinde ayarlanmış **Option Compare** ayarı **seçenekleri** iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="ab621-134">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="ab621-135">Bu, üzerinde ayarı değiştirmek için **Araçları** menüsünde tıklatın **seçenekleri**.</span><span class="sxs-lookup"><span data-stu-id="ab621-135">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="ab621-136">İçinde **seçenekleri** iletişim kutusunda **projeler ve çözümler**ve ardından **VB varsayılanları**.</span><span class="sxs-lookup"><span data-stu-id="ab621-136">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="ab621-137">İlk varsayılan ayarda **VB varsayılanları** olduğu **ikili**.</span><span class="sxs-lookup"><span data-stu-id="ab621-137">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="ab621-138">Option Compare komut satırında ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="ab621-138">To set Option Compare on the command line</span></span>  
  
- <span data-ttu-id="ab621-139">Dahil [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) derleyici seçeneğini **vbc** komutu.</span><span class="sxs-lookup"><span data-stu-id="ab621-139">Include the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab621-140">Örnek</span><span class="sxs-lookup"><span data-stu-id="ab621-140">Example</span></span>  
 <span data-ttu-id="ab621-141">Aşağıdaki örnekte `Option Compare` ikili karşılaştırma varsayılan dize karşılaştırma yöntemini ayarlamak için ifade.</span><span class="sxs-lookup"><span data-stu-id="ab621-141">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="ab621-142">Bu kodu kullanmak için açıklama durumundan çıkarın `Option Compare Binary` bildirimi ve kaynak dosyasının en üstüne yerleştir.</span><span class="sxs-lookup"><span data-stu-id="ab621-142">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#45)]  
  
## <a name="example"></a><span data-ttu-id="ab621-143">Örnek</span><span class="sxs-lookup"><span data-stu-id="ab621-143">Example</span></span>  
 <span data-ttu-id="ab621-144">Aşağıdaki örnekte `Option Compare` varsayılan dize karşılaştırma yöntemini büyük/küçük harfe metin sıralama düzeni ayarlamak için ifade.</span><span class="sxs-lookup"><span data-stu-id="ab621-144">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="ab621-145">Bu kodu kullanmak için açıklama durumundan çıkarın `Option Compare Text` bildirimi ve kaynak dosyasının en üstüne yerleştir.</span><span class="sxs-lookup"><span data-stu-id="ab621-145">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="ab621-146">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ab621-146">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>
- <xref:Microsoft.VisualBasic.Strings.Replace%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="ab621-147">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="ab621-147">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="ab621-148">Karşılaştırma İşleçleri</span><span class="sxs-lookup"><span data-stu-id="ab621-148">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="ab621-149">Visual Basic'de Karşılaştırma işleçleri</span><span class="sxs-lookup"><span data-stu-id="ab621-149">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="ab621-150">Like İşleci</span><span class="sxs-lookup"><span data-stu-id="ab621-150">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="ab621-151">Dize İşlevleri</span><span class="sxs-lookup"><span data-stu-id="ab621-151">String Functions</span></span>](../../../visual-basic/language-reference/functions/string-functions.md)
- [<span data-ttu-id="ab621-152">Option Explicit Deyimi</span><span class="sxs-lookup"><span data-stu-id="ab621-152">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="ab621-153">Option Strict Deyimi</span><span class="sxs-lookup"><span data-stu-id="ab621-153">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
