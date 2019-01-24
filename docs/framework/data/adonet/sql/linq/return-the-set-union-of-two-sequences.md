---
title: İki dizinin küme birleşimini döndürür
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: a2d51e8052c839ea4cd11dec07a3aef95d59d0f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546968"
---
# <a name="return-the-set-union-of-two-sequences"></a>İki dizinin küme birleşimini döndürür
Kullanım <xref:System.Linq.Queryable.Union%2A> işlecini iki dizinin küme birleşimini döndürür.  
  
## <a name="example"></a>Örnek  
 Bu örnekte <xref:System.Linq.Queryable.Union%2A> tüm ülkelerde, vardır ya da bir dizisini döndürmek için `Customers` veya `Employees`.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 İçinde [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> işleci için multisets multisets sırasız birleşimi tanımlanır (etkili bir şekilde sonucunu [ `UNION ALL` ](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) yan tümcesinde SQL).

Daha fazla bilgi ve örnekler için bkz. <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.
  
## <a name="see-also"></a>Ayrıca bkz.
- [Sorgu Örnekleri](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Standart Sorgu İşleci Çevirisi](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
