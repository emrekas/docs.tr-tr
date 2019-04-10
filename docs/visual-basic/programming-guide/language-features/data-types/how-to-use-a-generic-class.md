---
title: 'Nasıl yapılır: Genel bir sınıf (Visual Basic) kullanma'
ms.date: 07/20/2015
helpviewer_keywords:
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters [Visual Basic], data type
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
ms.openlocfilehash: c7fb4c95b6ef09508df57b3a0c08a651b122e251
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59302411"
---
# <a name="how-to-use-a-generic-class-visual-basic"></a><span data-ttu-id="32662-102">Nasıl yapılır: Genel bir sınıf (Visual Basic) kullanma</span><span class="sxs-lookup"><span data-stu-id="32662-102">How to: Use a Generic Class (Visual Basic)</span></span>
<span data-ttu-id="32662-103">Alan bir sınıf *tür parametrelerindeki* çağrılır bir *genel sınıf*.</span><span class="sxs-lookup"><span data-stu-id="32662-103">A class that takes *type parameters* is called a *generic class*.</span></span> <span data-ttu-id="32662-104">Genel sınıf kullanıyorsanız, oluşturabileceğiniz bir *oluşturulan sınıfı* sağlama tarafından gelen bir *tür bağımsız değişkeni* bu parametrelerin her biri için.</span><span class="sxs-lookup"><span data-stu-id="32662-104">If you are using a generic class, you can generate a *constructed class* from it by supplying a *type argument* for each of these parameters.</span></span> <span data-ttu-id="32662-105">Ardından oluşturulan sınıf türünde bir değişken bildirebilir ve oluşturulan sınıfın bir örneğini oluşturun ve bu değişkene atayın.</span><span class="sxs-lookup"><span data-stu-id="32662-105">You can then declare a variable of the constructed class type, and you can create an instance of the constructed class and assign it to that variable.</span></span>  
  
 <span data-ttu-id="32662-106">Sınıflara ek olarak tanımlayabilir ve genel yapılar, arabirimler, yordamları ve temsilciler kullanın.</span><span class="sxs-lookup"><span data-stu-id="32662-106">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
 <span data-ttu-id="32662-107">Tanımlanan genel bir sınıf aşağıdaki yordamın kullandığı [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ve bir örnek oluşturur.</span><span class="sxs-lookup"><span data-stu-id="32662-107">The following procedure takes a generic class defined in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and creates an instance from it.</span></span>  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a><span data-ttu-id="32662-108">Bir tür parametresi bir alan bir sınıf kullanma</span><span class="sxs-lookup"><span data-stu-id="32662-108">To use a class that takes a type parameter</span></span>  
  
1. <span data-ttu-id="32662-109">Kaynak dosyasının başında, dahil bir [Imports deyimi (.NET Namespace ve türü)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) içeri aktarmak için <xref:System.Collections.Generic?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="32662-109">At the beginning of your source file, include an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="32662-110">Bu sayede başvurmak <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> gibi diğer kuyruk sınıflarından ayırt etmek için tam olarak nitelemek gerek kalmadan sınıfı <xref:System.Collections.Queue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="32662-110">This allows you to refer to the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class without having to fully qualify it to differentiate it from other queue classes such as <xref:System.Collections.Queue?displayProperty=nameWithType>.</span></span>  
  
2. <span data-ttu-id="32662-111">Normal bir şekilde oluşturur, ancak ekleme `(Of type)` hemen sonra sınıf adı.</span><span class="sxs-lookup"><span data-stu-id="32662-111">Create the object in the normal way, but add `(Of type)` immediately after the class name.</span></span>  
  
     <span data-ttu-id="32662-112">Aşağıdaki örnek, aynı sınıf kullanır (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) farklı veri türlerinin öğeleri tutmak iki sıranın nesneleri oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="32662-112">The following example uses the same class (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) to create two queue objects that hold items of different data types.</span></span> <span data-ttu-id="32662-113">Her kuyruk sonuna öğe ekler ve ardından kaldırır ve her kuyruk önüne öğeleri görüntülemektedir.</span><span class="sxs-lookup"><span data-stu-id="32662-113">It adds items to the end of each queue and then removes and displays items from the front of each queue.</span></span>  
  
     [!code-vb[VbVbalrDataTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="32662-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="32662-114">See also</span></span>

- [<span data-ttu-id="32662-115">Veri Türleri</span><span class="sxs-lookup"><span data-stu-id="32662-115">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="32662-116">Visual Basic'de Genel Türler</span><span class="sxs-lookup"><span data-stu-id="32662-116">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="32662-117">Dil Bağımsızlığı ve Dilden Bağımsız Bileşenler</span><span class="sxs-lookup"><span data-stu-id="32662-117">Language Independence and Language-Independent Components</span></span>](../../../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="32662-118">Of</span><span class="sxs-lookup"><span data-stu-id="32662-118">Of</span></span>](../../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="32662-119">Imports Deyimi (.NET Ad Alanı ve Türü)</span><span class="sxs-lookup"><span data-stu-id="32662-119">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="32662-120">Nasıl yapılır: Farklı veri türlerinde aynı işlevselliği sağlayabilen bir sınıf tanımlama</span><span class="sxs-lookup"><span data-stu-id="32662-120">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="32662-121">Yineleyiciler</span><span class="sxs-lookup"><span data-stu-id="32662-121">Iterators</span></span>](../../../../visual-basic/programming-guide/concepts/iterators.md)
