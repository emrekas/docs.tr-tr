---
title: 'Nasıl yapılır: Veri Akışı Bloğunda Paralellik Derecesini Belirtme'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4395f6f8b59cca7b092a9d4d5d44c079244a29ef
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592011"
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a>Nasıl yapılır: Veri Akışı Bloğunda Paralellik Derecesini Belirtme
Bu belgenin nasıl ayarlanacağı açıklanır <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> bir yürütme veri akışı bloğunun aynı anda birden fazla ileti işlemek üzere etkinleştirmek için özelliği. Uzun süre çalışan bir hesaplama gerçekleştiren bir veri akışı bloğu olan ve paralel ileti işlemesini yararlanabilir, bunun yapılması yararlıdır. Bu örnekte <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> eşzamanlı olarak; ancak birden çok veri akışı işlemlerini gerçekleştirmek için sınıf, TPL veri akışı kitaplığı sağlayan önceden tanımlanmış yürütme bloğu türü hiçbirinde maksimum paralellik derecesi belirtebilirsiniz <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, ve <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iki veri akışı hesaplamaları gerçekleştirir ve her hesaplama için gerekli olan süre yazdırır. İlk hesaplama, varsayılan bir en fazla 1, paralellik derecesini belirtir. Bir en büyük bir paralellik derecesi 1 iletileri seri olarak işlemek veri akışı bloğu neden olur. İkinci hesaplama ilk benzer bir en fazla kullanılabilir işlemci sayısına eşit olan çalıştırılır. paralellik derecesini belirtir. Bu, paralel olarak birden çok işlemi gerçekleştirmek veri akışı bloğu sağlar.  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Varsayılan olarak, iletileri iletilerin alındığı sırada her önceden tanımlı veri akışı bloğu yayar.  Bir en büyük ölçüde 1'den büyük bir paralellik derecesi belirttiğinizde birden çok ileti aynı anda işlenir ancak bunlar yine de kullanıma alındı sıraya yayılır.  
  
 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> özelliği en büyük paralellik derecesini temsil ettiğinden, veri akışı bloğu belirttiğinizden daha düşük derecede paralellikle çalışabilir. Veri akışı bloğu işlevsel gereksinimlerini karşılamak için veya mevcut sistem kaynaklarının yetersizliği için hesap için daha düşük bir paralellik derecesi kullanabilirsiniz. Bir veri akışı bloğu asla belirttiğinizden daha büyük bir paralellik derecesi seçer.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Veri akışı](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
