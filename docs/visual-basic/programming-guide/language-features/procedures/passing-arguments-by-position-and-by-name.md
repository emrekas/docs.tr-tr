---
title: Bağımsız Değişkenleri Konuma ve Ada Göre Geçirme (Visual Basic)
ms.date: 02/01/2018
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
ms.openlocfilehash: b872eda97d1e349ad781b12810e4b166d6e46fe1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837318"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="9bc98-102">Bağımsız Değişkenleri Konuma ve Ada Göre Geçirme (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bc98-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="9bc98-103">Çağırdığınızda bir `Sub` veya `Function` yordamı, bağımsız değişkenleri iletebilir *konuma göre* — yordam tanımında göründükleri sırayla — veya geçirebileceğiniz gibi *ada göre*, olmadan konuma haklısın.</span><span class="sxs-lookup"><span data-stu-id="9bc98-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="9bc98-104">Ada göre bir bağımsız değişken başarıyla sonuçlandıktan sonra bağımsız değişken adını ardından bir iki nokta üst üste ve bir eşittir işareti tarafından bildirilen belirtin (`:=`) ve ardından bağımsız değişken değeri.</span><span class="sxs-lookup"><span data-stu-id="9bc98-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="9bc98-105">Herhangi bir sırada adlandırılmış bağımsız değişkenler sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9bc98-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="9bc98-106">Örneğin, aşağıdaki `Sub` yordamın kullandığı üç bağımsız değişken:</span><span class="sxs-lookup"><span data-stu-id="9bc98-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="9bc98-107">Bu yordamı çağırdığınızda, bağımsız değişken konumu, ad veya her ikisinin bir karışımıyla kullanarak sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9bc98-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="9bc98-108">Konuma göre bağımsız değişkenleri geçirme</span><span class="sxs-lookup"><span data-stu-id="9bc98-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="9bc98-109">Çağırabilirsiniz `Display` bağımsız değişkenlerinden yöntemiyle konuma göre geçirilen ve aşağıdaki örnekte gösterildiği gibi virgülle ayrılmış:</span><span class="sxs-lookup"><span data-stu-id="9bc98-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="9bc98-110">İsteğe bağlı bağımsız değişken bir konumsal bağımsız değişken listesindeki atlarsanız, onun yerine bir virgül ile tutmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="9bc98-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="9bc98-111">Aşağıdaki örnek çağrıları `Display` olmadan yöntemi `age` bağımsız değişkeni:</span><span class="sxs-lookup"><span data-stu-id="9bc98-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="9bc98-112">Ada göre bağımsız değişkenleri geçirme</span><span class="sxs-lookup"><span data-stu-id="9bc98-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="9bc98-113">Alternatif olarak, çağırabilirsiniz `Display` adına göre geçirilen bağımsız değişkenler ile aşağıdaki örnekte gösterildiği gibi virgülle da sınırlı:</span><span class="sxs-lookup"><span data-stu-id="9bc98-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="9bc98-114">Birden fazla isteğe bağlı bağımsız değişken içeren bir yordamı çağırdığınızda, bu şekilde adıyla bağımsız değişkenleri geçirme özellikle yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="9bc98-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="9bc98-115">Ada göre bağımsız değişken sağlarsanız, konumsal bağımsız değişkenler eksik belirtmek için ardışık virgüller kullanmak zorunda değil.</span><span class="sxs-lookup"><span data-stu-id="9bc98-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="9bc98-116">Ada göre bağımsız değişken geçirme Ayrıca hangi bağımsız değişkenleri geçirme ve hangilerinin, atlama izlemek kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="9bc98-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="9bc98-117">Bağımsız değişkenleri konuma ve ada göre karıştırma</span><span class="sxs-lookup"><span data-stu-id="9bc98-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="9bc98-118">Aşağıdaki örnekte gösterildiği gibi hem konuma ve ada göre tek bir yordam çağrısında bağımsız değişken belirtebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="9bc98-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="9bc98-119">Önceki örnekte, hiçbir ek virgülle belirtilmemişse yerini tutmak için gerekli `age` bağımsız değişkeni, bu yana `birth` adına göre geçirilir.</span><span class="sxs-lookup"><span data-stu-id="9bc98-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="9bc98-120">Bağımsız değişken bir karışımını konumu ve adı, konumsal bağımsız değişkenler sağladığında 15.5 önce'sürümlerinde Visual Basic'in tüm ilk sırada olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9bc98-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="9bc98-121">Kalan herhangi bir bağımsız değişken adına göre bağımsız değişken sağlayın, sonra tüm adına göre geçirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="9bc98-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="9bc98-122">Örneğin, için aşağıdaki çağrı `Display` yöntemi derleyici hatası görüntüler [BC30241: Adlandırılmış bağımsız değişken bekleniyor](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="9bc98-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="9bc98-123">Visual Basic 15.5 ile başlayarak, doğru konumda bitiş konumsal bağımsız değişkenler, konumsal bağımsız değişkenler adlandırılmış bağımsız değişkenler izleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9bc98-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="9bc98-124">Visual Basic 15.5, önceki çağrısı altında derlenmişse `Display` yöntem başarıyla derlenir ve artık derleyici hatası oluşturur [BC30241](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="9bc98-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="9bc98-125">Bu özelliği karıştırın ve eşleştirin adlandırılmış ve konumsal bağımsız değişkenler herhangi bir sırada kodunuzu daha okunabilir hale getirmek için bir adlandırılmış bağımsız değişken kullanmak istediğinizde özellikle yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="9bc98-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="9bc98-126">Örneğin, aşağıdaki `Person` sınıf oluşturucusu türünden iki bağımsız değişkeni gerektirir `Person`, ikisi için de olabilir `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9bc98-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="9bc98-127">Temizle kodun amacı olmasına yardımcı olur, karma adlandırılmış ve konumsal bağımsız değişkenler kullanarak değerini `father` ve `mother` bağımsız değişkenleri olan `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="9bc98-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="9bc98-128">Konumsal bağımsız değişkenler adlandırılmış bağımsız değişkenler ile takip etmek için aşağıdaki öğe Visual Basic projenize eklemeniz gerekir (\*.vbproj) dosya:</span><span class="sxs-lookup"><span data-stu-id="9bc98-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="9bc98-129">Daha fazla bilgi için [Visual Basic dil sürümü ayarını](../../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="9bc98-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="9bc98-130">Bağımsız değişken adı tarafından sağlama ile ilgili kısıtlamalar</span><span class="sxs-lookup"><span data-stu-id="9bc98-130">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="9bc98-131">Gerekli bağımsız değişkenler girmekten kaçınmak için ada göre bağımsız değişkenler geçirilemez.</span><span class="sxs-lookup"><span data-stu-id="9bc98-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="9bc98-132">İsteğe bağlı bağımsız değişkenlere atlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9bc98-132">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="9bc98-133">Ada göre bir parametre dizisi geçiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="9bc98-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="9bc98-134">Bu yordamı çağırdığınızda, belirsiz sayıda parametre dizisi virgülle ayrılmış bağımsız değişkenleri sağlayın ve derleyicinin tek bir ada sahip birden fazla bağımsız değişken ilişkilendirilemiyor olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="9bc98-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc98-135">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9bc98-135">See also</span></span>

- [<span data-ttu-id="9bc98-136">Yordamlar</span><span class="sxs-lookup"><span data-stu-id="9bc98-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="9bc98-137">Yordam Parametreleri ve Bağımsız Değişkenleri</span><span class="sxs-lookup"><span data-stu-id="9bc98-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="9bc98-138">Nasıl yapılır: Bir yordama bağımsız değişkenler geçirme</span><span class="sxs-lookup"><span data-stu-id="9bc98-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="9bc98-139">Bağımsız Değişkenleri Değere ve Başvuruya Göre Geçirme</span><span class="sxs-lookup"><span data-stu-id="9bc98-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="9bc98-140">İsteğe Bağlı Parametreler</span><span class="sxs-lookup"><span data-stu-id="9bc98-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="9bc98-141">Parametre Dizileri</span><span class="sxs-lookup"><span data-stu-id="9bc98-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="9bc98-142">Optional</span><span class="sxs-lookup"><span data-stu-id="9bc98-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="9bc98-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="9bc98-143">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
