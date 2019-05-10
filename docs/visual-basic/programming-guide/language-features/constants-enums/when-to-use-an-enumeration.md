---
title: Bir Numaralandırmanın Ne Zaman Kullanılacağı (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: a43c55d4ad6a895957b53ae18c3641c5383a24ce
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64585071"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="42668-102">Bir Numaralandırmanın Ne Zaman Kullanılacağı (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42668-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="42668-103">Numaralandırmalar ilgili sabitlerinin kümeleriyle çalışmak için kolay bir yolunu sunar.</span><span class="sxs-lookup"><span data-stu-id="42668-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="42668-104">Bir numaralandırma veya `Enum`, değerler için simgesel bir addır.</span><span class="sxs-lookup"><span data-stu-id="42668-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="42668-105">Numaralandırmalar veri türleri olarak kabul edilir ve değişkenleri ve özellikleri ile kullanım için sabitler kümesini oluşturmak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="42668-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="42668-106">Bir Numaralandırmanın Ne Zaman Kullanılacağı</span><span class="sxs-lookup"><span data-stu-id="42668-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="42668-107">Her bir yordam değişkenleri sınırlı sayıda kabul eder, bir numaralandırma kullanmayı düşünün.</span><span class="sxs-lookup"><span data-stu-id="42668-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="42668-108">Özellikle anlamlı adlar kullanıldığında sabit listeleri için kodu daha anlaşılır ve daha okunabilir, olun.</span><span class="sxs-lookup"><span data-stu-id="42668-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="42668-109">Numaralandırmalar kullanmanın avantajları şunlardır:</span><span class="sxs-lookup"><span data-stu-id="42668-109">The benefits of using enumerations include:</span></span>  
  
- <span data-ttu-id="42668-110">Sırasını değiştirme ya da sayı yanlış yazmanız kaynaklanan hataları azaltır.</span><span class="sxs-lookup"><span data-stu-id="42668-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
- <span data-ttu-id="42668-111">Değerleri gelecekte değiştirilmesini daha kolay hale getirir.</span><span class="sxs-lookup"><span data-stu-id="42668-111">Makes it easy to change values in the future.</span></span>  
  
- <span data-ttu-id="42668-112">Hataları içine şekilde katlamayı olasılığını yani kod okumak daha kolay hale getirir.</span><span class="sxs-lookup"><span data-stu-id="42668-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
- <span data-ttu-id="42668-113">İleriye dönük uyumluluk sağlar.</span><span class="sxs-lookup"><span data-stu-id="42668-113">Ensures forward compatibility.</span></span> <span data-ttu-id="42668-114">Numaralandırmalar ile kodunuzu gelecekte birinin üyesi adlara karşılık gelen değerleri değişirse başarısız etkilenme olasılığı da düşer.</span><span class="sxs-lookup"><span data-stu-id="42668-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="42668-115">Adlandırma sabit listeleri</span><span class="sxs-lookup"><span data-stu-id="42668-115">Naming Enumerations</span></span>  
 <span data-ttu-id="42668-116">Numaralandırma üyeleri için bir adlandırma kuralını kullanın.</span><span class="sxs-lookup"><span data-stu-id="42668-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="42668-117">Visual Basic bir sabit listesi üye adı karşılaştığında, diğer başvurulan tür kitaplıkları aynı adı içeriyorsa bir özel durum.</span><span class="sxs-lookup"><span data-stu-id="42668-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="42668-118">Uygulama veya bileşen değerleri tanımlayan benzersiz bir ön ekini kullanın.</span><span class="sxs-lookup"><span data-stu-id="42668-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="42668-119">Bir sabit listesi üyesi için söz konusu olduğunda, sabit listesi adı üye adıyla nitelemeniz veya desteklemeli kullanın `Imports` deyimi.</span><span class="sxs-lookup"><span data-stu-id="42668-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="42668-120">Daha fazla bilgi için [numaralandırmalar ve ad niteliği](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="42668-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="42668-121">Önceden tanımlanmış sabit listeleri</span><span class="sxs-lookup"><span data-stu-id="42668-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="42668-122">Visual Basic sağlayan bir dizi önceden tanımlanmış sabit listeleri gibi `FirstDayOfWeek` ve `MsgBoxResult`, kodunuzu kolaylaştırmak için.</span><span class="sxs-lookup"><span data-stu-id="42668-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="42668-123">Bunların bir listesi için bkz. [sabitler ve numaralandırmalar](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="42668-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42668-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="42668-124">See also</span></span>

- [<span data-ttu-id="42668-125">Nasıl yapılır: Bir numaralandırma bildirme</span><span class="sxs-lookup"><span data-stu-id="42668-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="42668-126">Nasıl yapılır: Bir numaralandırma üyesine başvurma</span><span class="sxs-lookup"><span data-stu-id="42668-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="42668-127">Sabit Listeleri ve Ad Niteliği</span><span class="sxs-lookup"><span data-stu-id="42668-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="42668-128">Nasıl yapılır: Visual Basic'de numaralandırma yoluyla yineleme yapma</span><span class="sxs-lookup"><span data-stu-id="42668-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="42668-129">Nasıl yapılır: Bir numaralandırma değeriyle ilişkili dizeyi belirleme</span><span class="sxs-lookup"><span data-stu-id="42668-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="42668-130">Enum Deyimi</span><span class="sxs-lookup"><span data-stu-id="42668-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="42668-131">Sabitler ve Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="42668-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
