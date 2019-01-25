---
title: (C# üzerinde LINQ) çalışma zamanında koşul filtrelerini dinamik olarak belirtme
description: C# içinde LINQ kullanarak çalışma zamanında koşul filtrelerini dinamik olarak belirtme hakkında bilgi edinin.
ms.date: 12/01/2016
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: 314be8f98b9ff014f14bef11a1f3581eff8574b4
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857742"
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="3f98b-103">Çalışma zamanında koşul filtrelerini dinamik olarak belirtme</span><span class="sxs-lookup"><span data-stu-id="3f98b-103">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="3f98b-104">Bazı durumlarda, doğrulamaları kaç kaynak öğeleri uygulamak sahip olduğunuz çalışma zamanına kadar bilmiyorum `where` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="3f98b-104">In some cases, you don't know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="3f98b-105">Birden çok koşul filtrelerini dinamik olarak belirtmek için tek bir yolu <xref:System.Linq.Enumerable.Contains%2A> yöntemi, aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="3f98b-105">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="3f98b-106">Örneğin, iki şekilde oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="3f98b-106">The example is constructed in two ways.</span></span> <span data-ttu-id="3f98b-107">İlk olarak, projeyi programda sağlanan değerleri filtreleyerek çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="3f98b-107">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="3f98b-108">Ardından projeyi yeniden çalışma zamanında sağlanan giriş kullanılarak çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="3f98b-108">Then the project is run again by using input provided at run time.</span></span>

## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="3f98b-109">Contains yöntemi kullanarak filtre uygulamak için</span><span class="sxs-lookup"><span data-stu-id="3f98b-109">To filter by using the Contains method</span></span>

1. <span data-ttu-id="3f98b-110">Yeni bir konsol uygulaması'nı açın ve adlandırın `PredicateFilters`.</span><span class="sxs-lookup"><span data-stu-id="3f98b-110">Open a new console application and name it `PredicateFilters`.</span></span>

2. <span data-ttu-id="3f98b-111">Kopyalama `StudentClass` gelen sınıfı [nesneler koleksiyonunu sorgulama](query-a-collection-of-objects.md) ve ad alanına yapıştırın `PredicateFilters` sınıfı altında `Program`.</span><span class="sxs-lookup"><span data-stu-id="3f98b-111">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="3f98b-112">`StudentClass` bir listesini sağlar `Student` nesneleri.</span><span class="sxs-lookup"><span data-stu-id="3f98b-112">`StudentClass` provides a list of `Student` objects.</span></span>

3. <span data-ttu-id="3f98b-113">Açıklama `Main` yönteminde `StudentClass`.</span><span class="sxs-lookup"><span data-stu-id="3f98b-113">Comment out the `Main` method in `StudentClass`.</span></span>

4. <span data-ttu-id="3f98b-114">Sınıf değiştirin `Program` aşağıdaki kod ile:</span><span class="sxs-lookup"><span data-stu-id="3f98b-114">Replace class `Program` with the following code:</span></span>

     [!code-csharp[csProgGuideLINQ#26](~/samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]

5. <span data-ttu-id="3f98b-115">Aşağıdaki satırı ekleyin `Main` sınıfındaki yöntemi `DynamicPredicates`, bildirimi altında `ids`.</span><span class="sxs-lookup"><span data-stu-id="3f98b-115">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>

     ```csharp
     QueryById(ids);
     ```

6. <span data-ttu-id="3f98b-116">Projeyi çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="3f98b-116">Run the project.</span></span>

7. <span data-ttu-id="3f98b-117">Aşağıdaki çıktıyı konsol penceresinde görüntülenir:</span><span class="sxs-lookup"><span data-stu-id="3f98b-117">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="3f98b-118">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="3f98b-118">Garcia: 114</span></span>

     <span data-ttu-id="3f98b-119">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="3f98b-119">O'Donnell: 112</span></span>

     <span data-ttu-id="3f98b-120">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="3f98b-120">Omelchenko: 111</span></span>

8. <span data-ttu-id="3f98b-121">Sonraki adımda projeyi yeniden çalıştırmak için çalışma zamanında dizi yerine Giriş kullanarak bu saati girildi. `ids`.</span><span class="sxs-lookup"><span data-stu-id="3f98b-121">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="3f98b-122">Değişiklik `QueryByID(ids)` için `QueryByID(args)` içinde `Main` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3f98b-122">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>

9. <span data-ttu-id="3f98b-123">Komut satırı bağımsız değişkenleri ile projeyi Çalıştır `122 117 120 115`.</span><span class="sxs-lookup"><span data-stu-id="3f98b-123">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="3f98b-124">Projeyi çalıştırdığınızda, bu değerleri öğelerini haline `args`, parametresi `Main` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3f98b-124">When the project is run, those values become elements of `args`, the parameter of the `Main` method.</span></span>

10. <span data-ttu-id="3f98b-125">Aşağıdaki çıktıyı konsol penceresinde görüntülenir:</span><span class="sxs-lookup"><span data-stu-id="3f98b-125">The following output is displayed in a console window:</span></span>

     <span data-ttu-id="3f98b-126">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="3f98b-126">Adams: 120</span></span>

     <span data-ttu-id="3f98b-127">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="3f98b-127">Feng: 117</span></span>

     <span data-ttu-id="3f98b-128">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="3f98b-128">Garcia: 115</span></span>

     <span data-ttu-id="3f98b-129">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="3f98b-129">Tucker: 122</span></span>

## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="3f98b-130">Switch deyimi kullanarak filtre uygulamak için</span><span class="sxs-lookup"><span data-stu-id="3f98b-130">To filter by using a switch statement</span></span>

1. <span data-ttu-id="3f98b-131">Kullanabileceğiniz bir `switch` arasından seçim yapmak deyimi önceden alternatif sorgular.</span><span class="sxs-lookup"><span data-stu-id="3f98b-131">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="3f98b-132">Aşağıdaki örnekte, `studentQuery` farklı bir kullanan `where` bağlı olarak hangi sınıf düzeyinde veya yıl, belirtilen çalışma zamanında yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="3f98b-132">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>

2. <span data-ttu-id="3f98b-133">Aşağıdaki yöntemi kopyalayın ve sınıfına yapıştırın `DynamicPredicates`.</span><span class="sxs-lookup"><span data-stu-id="3f98b-133">Copy the following method and paste it into class `DynamicPredicates`.</span></span>

     [!code-csharp[csProgGuideLINQ#27](~/samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]

3. <span data-ttu-id="3f98b-134">İçinde `Main` yöntemi çağrısını `QueryByID` aşağıdaki çağrısıyla, gönderdiği ilk öğenin `args` kendi bağımsız değişkeni olarak bir dizi: `QueryByYear(args[0])`.</span><span class="sxs-lookup"><span data-stu-id="3f98b-134">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>

4. <span data-ttu-id="3f98b-135">Projeyi, 1 ile 4 arasında bir tamsayı değeri bir komut satırı bağımsız değişkeni ile çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="3f98b-135">Run the project with a command line argument of an integer value between 1 and 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f98b-136">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3f98b-136">See also</span></span>

- [<span data-ttu-id="3f98b-137">Dil ile Tümleşik Sorgu (LINQ)</span><span class="sxs-lookup"><span data-stu-id="3f98b-137">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="3f98b-138">where yan tümcesi</span><span class="sxs-lookup"><span data-stu-id="3f98b-138">where clause</span></span>](../language-reference/keywords/where-clause.md)
