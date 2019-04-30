---
title: Grup sonuçları bitişik anahtarlara (C# üzerinde LINQ)
description: C# içinde LINQ kullanarak bitişik anahtarlara göre sonuçları gruplandırmak nasıl.
ms.date: 08/14/2018
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: b5753c85bb07be4fc84b78a299eece961969ff9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61659910"
---
# <a name="group-results-by-contiguous-keys"></a>Sonuçları bitişik anahtarlara göre gruplama

Aşağıdaki örnek, bitişik anahtarların sıraları temsil eden öbeklere öğeleri gruplayın gösterilmektedir. Örneğin, aşağıdaki anahtar-değer çiftleri dizisi verilen varsayın:

|Anahtar|Değer|
|---------|-----------|
|BİR|Biz|
|BİR|Düşünme|
|BİR|,|
|B|LINQ|
|C|is|
|BİR|gerçekten|
|B|seyrek erişimli|
|B|!|

Aşağıdaki gruplar bu sırayla oluşturulur:

1. Düşünüyoruz,

2. LINQ

3. is

4. gerçekten

5. seyrek!

Çözüm, iş parçacığı açısından güvenli ve akıcı bir şekilde sonuçları döndüren bir genişletme yöntemi olarak uygulanır. Diğer bir deyişle, kaynak sırası boyunca hareket ettikçe, grupları üretir. Farklı `group` veya `orderby` operatörleri onu başlayabilir çağırana grupları döndüren tüm dizinin okumadan önce.

İş parçacığı güvenliği kaynak sırası yinelendiğinde gibi her bir grup veya öbek bir kopyasını kaynak kod yorumlar bölümünde açıklandığı gibi kullanılarak gerçekleştirilir. Kaynak sırası büyük bir dizi bitişik öğesi varsa, ortak dil çalışma zamanı oluşturabilecek bir <xref:System.OutOfMemoryException>.

## <a name="example"></a>Örnek

Aşağıdaki örnek, hem genişletme yöntemi hem de onu kullanan istemci kodu gösterir:

[!code-csharp[cscsrefContiguousGroups#1](~/samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]

Projenizde genişletme yöntemini kullanmak için kopyalayın `MyExtensions` statik sınıf için yeni veya mevcut bir kaynak kod dosyası ve, gerekirse ekleme bir `using` bulunduğu olduğu ad alanı için yönerge.

## <a name="see-also"></a>Ayrıca bkz.

- [Dil ile Tümleşik Sorgu (LINQ)](index.md)
