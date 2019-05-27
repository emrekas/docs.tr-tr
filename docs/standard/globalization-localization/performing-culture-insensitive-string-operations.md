---
title: Kültüre Duyarsız Dize İşlemlerini Gerçekleştirme
ms.date: 08/22/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6054df642176976db4feb2aba682a20ca6b3dda5
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053120"
---
# <a name="performing-culture-insensitive-string-operations"></a><span data-ttu-id="5cf0b-102">Kültüre duyarsız dize işlemlerini gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="5cf0b-102">Performing culture-insensitive string operations</span></span>
<span data-ttu-id="5cf0b-103">Varsayılan olarak kültüre duyarlı dize işlemleri çoğu .NET Framework yöntemlerini açıkça geçirerek kullanılacak kültürü belirtmenize olanak tanıyan bir yöntemi aşırı yüklemeler sağlar bir <xref:System.Globalization.CultureInfo> parametresi.</span><span class="sxs-lookup"><span data-stu-id="5cf0b-103">Most .NET Framework methods that perform culture-sensitive string operations by default provide method overloads that allow you to explicitly specify the culture to use by passing a <xref:System.Globalization.CultureInfo> parameter.</span></span> <span data-ttu-id="5cf0b-104">Bu aşırı yüklemeler eşlemeleri ve sıralama kuralları ve kültüre duyarlı olmayan sonuçlar garanti durumunda kültürel farklılıklara ortadan kaldırmak sağlar.</span><span class="sxs-lookup"><span data-stu-id="5cf0b-104">These overloads allow you to eliminate cultural variations in case mappings and sorting rules and guarantee culture-insensitive results.</span></span>  
  
 <span data-ttu-id="5cf0b-105">Bu bölüm, kültüre duyarlı olan .NET Framework yöntemlerini kullanarak kültüre duyarsız dize işlemlerini nasıl gerçekleştireceğinizi göstermek için aşağıdaki konuları sağlar. varsayılan değer.</span><span class="sxs-lookup"><span data-stu-id="5cf0b-105">This section provides the following topics to demonstrate how to perform culture-insensitive string operations using .NET Framework methods that are culture-sensitive by default.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5cf0b-106">Bu bölümde</span><span class="sxs-lookup"><span data-stu-id="5cf0b-106">In this section</span></span>  
 [<span data-ttu-id="5cf0b-107">Kültüre Duyarsız Dize Karşılaştırmalarını Gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="5cf0b-107">Performing Culture-Insensitive String Comparisons</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 <span data-ttu-id="5cf0b-108">Nasıl kullanılacağını açıklar <xref:System.String.Compare%2A?displayProperty=nameWithType> ve <xref:System.String.CompareTo%2A?displayProperty=nameWithType> yöntemleri kültüre duyarsız dize karşılaştırmalarını gerçekleştirme.</span><span class="sxs-lookup"><span data-stu-id="5cf0b-108">Describes how to use the <xref:System.String.Compare%2A?displayProperty=nameWithType> and <xref:System.String.CompareTo%2A?displayProperty=nameWithType> methods to perform culture-insensitive string comparisons.</span></span>  
  
 [<span data-ttu-id="5cf0b-109">Kültüre Duyarsız Büyük/Küçük Harf Değişikliklerini Gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="5cf0b-109">Performing Culture-Insensitive Case Changes</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 <span data-ttu-id="5cf0b-110">Nasıl kullanılacağını açıklar <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, ve <xref:System.Char.ToLower%2A?displayProperty=nameWithType> yöntemleri kültüre duyarsız büyük/küçük harf değişikliklerini gerçekleştirme.</span><span class="sxs-lookup"><span data-stu-id="5cf0b-110">Describes how to use the <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods to perform culture-insensitive case changes.</span></span>  
  
 [<span data-ttu-id="5cf0b-111">Koleksiyonlarda Kültüre Duyarsız Dize İşlemlerini Gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="5cf0b-111">Performing Culture-Insensitive String Operations in Collections</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 <span data-ttu-id="5cf0b-112">Nasıl kullanılacağını açıklar <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> sınıfı <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> ve <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> koleksiyonlarında kültüre duyarsız işlemleri gerçekleştirmek için.</span><span class="sxs-lookup"><span data-stu-id="5cf0b-112">Describes how to use the <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> class, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> and <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> to perform culture-insensitive operations in collections.</span></span>  
  
 [<span data-ttu-id="5cf0b-113">Dizilerde Kültüre Duyarsız Dize İşlemlerini Gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="5cf0b-113">Performing Culture-Insensitive String Operations in Arrays</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 <span data-ttu-id="5cf0b-114">Nasıl kullanılacağını açıklar <xref:System.Array.Sort%2A?displayProperty=nameWithType> ve <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> dizilerde kültüre duyarsız işlemleri gerçekleştirmek için yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="5cf0b-114">Describes how to use the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods to perform culture-insensitive operations in arrays.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5cf0b-115">İlgili bölümler</span><span class="sxs-lookup"><span data-stu-id="5cf0b-115">Related sections</span></span>  
 [<span data-ttu-id="5cf0b-116">Kültüre Duyarsız Dize İşlemleri</span><span class="sxs-lookup"><span data-stu-id="5cf0b-116">Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 <span data-ttu-id="5cf0b-117">Neden dizelerde işlemleri gerçekleştirirken kültürünü bilmeniz gereken açıklar ve kültüre duyarlı işlemleri gerçekleştirmek zaman ve ne zaman kültüre duyarlı işlemleri gerçekleştirmek için yönergeler sağlar.</span><span class="sxs-lookup"><span data-stu-id="5cf0b-117">Describes why you should be aware of culture when performing operations on strings and provides guidelines for when to perform culture-sensitive operations and when to perform culture-insensitive operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cf0b-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5cf0b-118">See also</span></span>

- [<span data-ttu-id="5cf0b-119">Sıralama ağırlık tablolar (için Windows sistemlerinde .NET)</span><span class="sxs-lookup"><span data-stu-id="5cf0b-119">Sorting Weight Tables (for .NET on Windows systems)</span></span>](https://www.microsoft.com/download/details.aspx?id=10921)
- [<span data-ttu-id="5cf0b-120">Varsayılan Unicode Harmanlama öğesi tablosu (Linux ve Macos'ta .NET Core)</span><span class="sxs-lookup"><span data-stu-id="5cf0b-120">Default Unicode Collation Element Table (for .NET Core on Linux and macOS)</span></span>](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
