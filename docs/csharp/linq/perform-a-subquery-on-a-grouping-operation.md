---
title: (C# üzerinde LINQ) gruplandırma işleminde alt sorgu gerçekleştirme
description: C# içinde LINQ kullanarak bir gruplandırma işleminde alt sorgu gerçekleştirme yapma.
ms.date: 12/01/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: a3757a7d358a310dd1404f85e34178f6e561bcb9
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857443"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a>Gruplandırma işleminde alt sorgu gerçekleştirme

Bu makalede, kaynak verileri gruplar halinde sıralar ve sonra bir alt sorgu her bir grup üzerinde tek tek gerçekleştiren bir sorgu oluşturmak için iki farklı yolu gösterilmektedir. Her örnekte temel tekniği kullanarak kaynak öğeleri gruplandırmak için olan bir *devamlılık* adlı `newGroup`ve ardından yeni bir alt sorgu karşı oluşturma `newGroup`. Bu alt sorgu, dış sorgu tarafından oluşturulan her yeni gruba göre çalıştırılır. Bu örnekte son çıkışı değil bir grup ancak anonim türler düz dizisi olduğunu unutmayın.  
  
Gruba hakkında daha fazla bilgi için bkz. [group yan tümcesi](../language-reference/keywords/group-clause.md).  
  
Devamlılıklar hakkında daha fazla bilgi için bkz: [içine](../language-reference/keywords/into.md). Aşağıdaki örnek, veri kaynağı olarak bir bellek içi veri yapısı kullanır, ancak tüm LINQ veri kaynağı türü için aynı ilkeler geçerlidir.  
  
## <a name="example"></a>Örnek

> [!NOTE]
> Bu örnekte örnek koda tanımlanan nesneleri başvuruları içeren [nesneler koleksiyonunu sorgulama](query-a-collection-of-objects.md).

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)] 

Yukarıdaki kod parçacığında sorgu ayrıca yöntem sözdizimini kullanarak yazılabilir. Aşağıdaki kod parçacığı, yöntem sözdizimi kullanılarak yazılmış anlamsal olarak eşdeğer bir sorgu yok.

[!code-csharp[csProgGuideLINQ#86](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_2.cs)]

## <a name="see-also"></a>Ayrıca bkz.

- [Dil ile Tümleşik Sorgu (LINQ)](index.md)
