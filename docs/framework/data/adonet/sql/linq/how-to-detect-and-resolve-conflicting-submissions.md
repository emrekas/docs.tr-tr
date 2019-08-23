---
title: 'Nasıl yapılır: Çakışan Gönderimleri Algılama ve Çözümleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: ff33196f83e2c0d8d759e4ffc3fb7442e8ba0e3b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940093"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>Nasıl yapılır: Çakışan Gönderimleri Algılama ve Çözümleme
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], çok kullanıcılı değişikliklerden oluşan çakışmaları saptamak ve çözmek için çok sayıda kaynak sağlar. Daha fazla bilgi için [nasıl yapılır: Değişiklik çakışmalarını](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)yönetin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir `try` `catch` / özeldurumuyakalayanbirbloğugösterir<xref:System.Data.Linq.ChangeConflictException> . Her çakışma için varlık ve üye bilgileri konsol penceresinde görüntülenir.  
  
> [!NOTE]
> Bilgi alımını desteklemek için `using System.Reflection` yönergesini (`Imports System.Reflection` Visual Basic) eklemeniz gerekir. Daha fazla bilgi için bkz. <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Veri Değişiklikleri Yapma ve Gönderme](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [Nasıl yapılır: Değişiklik çakışmalarını yönetme](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
