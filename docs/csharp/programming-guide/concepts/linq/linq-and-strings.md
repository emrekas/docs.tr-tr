---
title: LINQ ve dizeler (C#)
ms.date: 07/20/2015
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
ms.openlocfilehash: c7a1b86cc611d5f38ceab814b4594f5ad953fbc4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744628"
---
# <a name="linq-and-strings-c"></a><span data-ttu-id="82bf0-102">LINQ ve dizeler (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-102">LINQ and strings (C#)</span></span>

<span data-ttu-id="82bf0-103">LINQ Sorgu dizeleri ve dizelerden oluşan koleksiyonları dönüştürmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-103">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="82bf0-104">Metin dosyalarında yarı yapısal verilerle özellikle yararlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-104">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="82bf0-105">LINQ sorguları, geleneksel dize işlevleri ve normal ifadeler ile birleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-105">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="82bf0-106">Örneğin, kullanabileceğiniz <xref:System.String.Split%2A?displayProperty=nameWithType> veya <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> sonra sorgulayabilir veya LINQ kullanarak değiştirme dizeleri bir dizi oluşturmak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="82bf0-106">For example, you can use the <xref:System.String.Split%2A?displayProperty=nameWithType> or <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="82bf0-107">Kullanabileceğiniz <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> yönteminde `where` bir LINQ sorgu yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="82bf0-107">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="82bf0-108">LINQ Sorgu veya değiştirmek için kullanabileceğiniz <xref:System.Text.RegularExpressions.MatchCollection> normal bir ifade tarafından döndürülen sonuç.</span><span class="sxs-lookup"><span data-stu-id="82bf0-108">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>

<span data-ttu-id="82bf0-109">Bu bölümde açıklanan olan tekniklerle da XML'e yarı yapılandırılmış metin verileri dönüştürmek için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="82bf0-109">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="82bf0-110">Daha fazla bilgi için [nasıl yapılır: CSV dosyalarından XML oluşturma](how-to-generate-xml-from-csv-files.md).</span><span class="sxs-lookup"><span data-stu-id="82bf0-110">For more information, see [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md).</span></span>

<span data-ttu-id="82bf0-111">Bu bölümdeki örnekler, iki kategoriye ayrılır:</span><span class="sxs-lookup"><span data-stu-id="82bf0-111">The examples in this section fall into two categories:</span></span>

## <a name="querying-a-block-of-text"></a><span data-ttu-id="82bf0-112">Metin bloğu sorgulama</span><span class="sxs-lookup"><span data-stu-id="82bf0-112">Querying a block of text</span></span>

<span data-ttu-id="82bf0-113">Sorgu, analiz ve daha küçük dizeleri sorgulanabilir bir diziye bölerek kullanarak metin blokları değiştirme <xref:System.String.Split%2A?displayProperty=nameWithType> yöntemi veya <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="82bf0-113">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A?displayProperty=nameWithType> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="82bf0-114">Kaynak metni sözcükler, cümle, paragraf, sayfaları veya başka bir ölçüt bölmek ve sorgunuzda gerekirse ek bölmelerini gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="82bf0-114">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>

- [<span data-ttu-id="82bf0-115">Nasıl yapılır: Bir sözcüğün bir dizede (LINQ) geçtiğini sayma (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-115">How to: Count Occurrences of a Word in a String (LINQ) (C#)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
  <span data-ttu-id="82bf0-116">Basit metin üzerinde sorgulamak için LINQ kullanma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-116">Shows how to use LINQ for simple querying over text.</span></span>

- [<span data-ttu-id="82bf0-117">Nasıl yapılır: Belirli bir sözcükler (LINQ) kümesini içeren cümleleri sorgulama (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-117">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

  <span data-ttu-id="82bf0-118">Metin dosyaları rastgele sınırlarındaki bölme ve her parça karşı sorguları gerçekleştirmeyi gösterir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-118">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>

- [<span data-ttu-id="82bf0-119">Nasıl yapılır: (LINQ) bir dizedeki karakterleri sorgulama (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-119">How to: Query for Characters in a String (LINQ) (C#)</span></span>](how-to-query-for-characters-in-a-string-linq.md)

  <span data-ttu-id="82bf0-120">Bir dize sorgulanabilir tür olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-120">Demonstrates that a string is a queryable type.</span></span>

- [<span data-ttu-id="82bf0-121">Nasıl yapılır: Normal ifadelerle LINQ sorgularını birleştirme (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-121">How to: Combine LINQ Queries with Regular Expressions (C#)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)

  <span data-ttu-id="82bf0-122">Filtrelenmiş sorgu sonuçlarına karmaşık desen için LINQ sorgularında normal ifadeleri kullanma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-122">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>

## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="82bf0-123">Metin biçimindeki yarı yapılandırılmış verileri Sorgulama</span><span class="sxs-lookup"><span data-stu-id="82bf0-123">Querying semi-structured data in text format</span></span>

<span data-ttu-id="82bf0-124">Satırları, genellikle sekme veya virgülle sınırlandırılmış dosyalar veya sabit uzunluklu satırları gibi benzer biçimlendirmeye sahip olan bir dizi farklı türlerde metin dosyaları oluşur.</span><span class="sxs-lookup"><span data-stu-id="82bf0-124">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="82bf0-125">Bu tür bir metin dosyası belleğe okuduktan sonra sorgu ve/veya satırları değiştirmek için LINQ kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="82bf0-125">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="82bf0-126">LINQ sorguları ayrıca birden çok kaynaktan veri birleştirme görevini basitleştirir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-126">LINQ queries also simplify the task of combining data from multiple sources.</span></span>

- [<span data-ttu-id="82bf0-127">Nasıl yapılır: (LINQ) iki liste arasında ayarlanmış farkı bulma (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-127">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)

  <span data-ttu-id="82bf0-128">Bir liste ancak diğer mevcut olan tüm dizeleri bulmak gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-128">Shows how to find all the strings that are present in one list but not the other.</span></span>

- [<span data-ttu-id="82bf0-129">Nasıl yapılır: Herhangi bir sözcük veya alana (LINQ) göre filtre metin verilerini sıralama veya (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-129">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

  <span data-ttu-id="82bf0-130">Herhangi bir sözcük veya alana göre metin satırlarını sıralama işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-130">Shows how to sort text lines based on any word or field.</span></span>

- [<span data-ttu-id="82bf0-131">Nasıl yapılır: (LINQ) sınırlandırılmış bir dosyanın alanlarını yeniden sıralama (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-131">How to: Reorder the Fields of a Delimited File (LINQ) (C#)</span></span>](how-to-reorder-the-fields-of-a-delimited-file-linq.md)

  <span data-ttu-id="82bf0-132">Bir .csv dosyası bir satırda alanları yeniden sıralama işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-132">Shows how to reorder fields in a line in a .csv file.</span></span>

- [<span data-ttu-id="82bf0-133">Nasıl yapılır: (LINQ) dize koleksiyonlarını birleştirme ve karşılaştırma (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-133">How to: Combine and Compare String Collections (LINQ) (C#)</span></span>](how-to-combine-and-compare-string-collections-linq.md)

  <span data-ttu-id="82bf0-134">Dize listesi çeşitli şekillerde birleştirme işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-134">Shows how to combine string lists in various ways.</span></span>

- [<span data-ttu-id="82bf0-135">Nasıl yapılır: (LINQ) birden fazla kaynaktan nesne koleksiyonları doldurma (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-135">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)

  <span data-ttu-id="82bf0-136">Veri kaynağı olarak birden çok metin dosyasını kullanarak nesne koleksiyonları oluşturma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-136">Shows how to create object collections by using multiple text files as data sources.</span></span>

- [<span data-ttu-id="82bf0-137">Nasıl yapılır: Dosyalardan içerik (LINQ) katılın (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-137">How to: Join Content from Dissimilar Files (LINQ) (C#)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)
  
  <span data-ttu-id="82bf0-138">Eşleşen bir anahtar kullanarak iki liste dizelerde tek bir dize olarak birleştirilecek gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-138">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>

- [<span data-ttu-id="82bf0-139">Nasıl yapılır: Gruplar (LINQ) kullanarak bir dosyayı birden çok dosyaya bölme (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-139">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
  
  <span data-ttu-id="82bf0-140">Veri kaynağı olarak tek bir dosyayı kullanarak yeni dosyalar oluşturma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-140">Shows how to create new files by using a single file as a data source.</span></span>

- [<span data-ttu-id="82bf0-141">Nasıl yapılır: Sütun değerleri bir CSV metinde dosyasında (LINQ) işlem (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-141">How to: Compute Column Values in a CSV Text File (LINQ) (C#)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
  
  <span data-ttu-id="82bf0-142">Metin verileri .csv dosyalarındaki matematiksel hesaplamalar gerçekleştirmek nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="82bf0-142">Shows how to perform mathematical computations on text data in .csv files.</span></span>

## <a name="see-also"></a><span data-ttu-id="82bf0-143">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="82bf0-143">See also</span></span>

- [<span data-ttu-id="82bf0-144">Dil ile tümleşik sorgu (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="82bf0-144">Language-Integrated Query (LINQ) (C#)</span></span>](index.md)
- [<span data-ttu-id="82bf0-145">Nasıl yapılır: CSV dosyalarından XML oluşturma</span><span class="sxs-lookup"><span data-stu-id="82bf0-145">How to: Generate XML from CSV Files</span></span>](how-to-generate-xml-from-csv-files.md)
