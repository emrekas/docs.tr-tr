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
# <a name="performing-culture-insensitive-string-operations"></a>Kültüre duyarsız dize işlemlerini gerçekleştirme
Varsayılan olarak kültüre duyarlı dize işlemleri çoğu .NET Framework yöntemlerini açıkça geçirerek kullanılacak kültürü belirtmenize olanak tanıyan bir yöntemi aşırı yüklemeler sağlar bir <xref:System.Globalization.CultureInfo> parametresi. Bu aşırı yüklemeler eşlemeleri ve sıralama kuralları ve kültüre duyarlı olmayan sonuçlar garanti durumunda kültürel farklılıklara ortadan kaldırmak sağlar.  
  
 Bu bölüm, kültüre duyarlı olan .NET Framework yöntemlerini kullanarak kültüre duyarsız dize işlemlerini nasıl gerçekleştireceğinizi göstermek için aşağıdaki konuları sağlar. varsayılan değer.  
  
## <a name="in-this-section"></a>Bu bölümde  
 [Kültüre Duyarsız Dize Karşılaştırmalarını Gerçekleştirme](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Nasıl kullanılacağını açıklar <xref:System.String.Compare%2A?displayProperty=nameWithType> ve <xref:System.String.CompareTo%2A?displayProperty=nameWithType> yöntemleri kültüre duyarsız dize karşılaştırmalarını gerçekleştirme.  
  
 [Kültüre Duyarsız Büyük/Küçük Harf Değişikliklerini Gerçekleştirme](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Nasıl kullanılacağını açıklar <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, ve <xref:System.Char.ToLower%2A?displayProperty=nameWithType> yöntemleri kültüre duyarsız büyük/küçük harf değişikliklerini gerçekleştirme.  
  
 [Koleksiyonlarda Kültüre Duyarsız Dize İşlemlerini Gerçekleştirme](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Nasıl kullanılacağını açıklar <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> sınıfı <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> ve <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> koleksiyonlarında kültüre duyarsız işlemleri gerçekleştirmek için.  
  
 [Dizilerde Kültüre Duyarsız Dize İşlemlerini Gerçekleştirme](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Nasıl kullanılacağını açıklar <xref:System.Array.Sort%2A?displayProperty=nameWithType> ve <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> dizilerde kültüre duyarsız işlemleri gerçekleştirmek için yöntemleri.  
  
## <a name="related-sections"></a>İlgili bölümler  
 [Kültüre Duyarsız Dize İşlemleri](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Neden dizelerde işlemleri gerçekleştirirken kültürünü bilmeniz gereken açıklar ve kültüre duyarlı işlemleri gerçekleştirmek zaman ve ne zaman kültüre duyarlı işlemleri gerçekleştirmek için yönergeler sağlar.

## <a name="see-also"></a>Ayrıca bkz.

- [Sıralama ağırlık tablolar (için Windows sistemlerinde .NET)](https://www.microsoft.com/download/details.aspx?id=10921)
- [Varsayılan Unicode Harmanlama öğesi tablosu (Linux ve Macos'ta .NET Core)](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
