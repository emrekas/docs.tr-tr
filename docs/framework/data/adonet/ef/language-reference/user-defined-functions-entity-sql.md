---
title: Kullanıcı tanımlı işlevler (varlık SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 7810f2b643ace0b8219855db80c6ed5466df1c1a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694665"
---
# <a name="user-defined-functions-entity-sql"></a>Kullanıcı tanımlı işlevler (varlık SQL)
Entity SQL kullanıcı tanımlı işlevler çağırma sorguda destekler. Bu işlevlerin satır içi sorgu tanımlayabilirsiniz (bkz [nasıl yapılır: Bir kullanıcı tanımlı işlevi çağırma](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) ya da kavramsal modelin parçası olarak (bkz [nasıl yapılır: Kavramsal modelde özel işlevleri tanımlamak](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)). Entity SQL komutu tanımlı kavramsal model işlevler [DefiningExpression](https://msdn.microsoft.com/library/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) öğesinin bir [işlevi](https://msdn.microsoft.com/library/dc3beca7-55cf-4977-8db0-5064cdbab134) kavramsal model öğesi.  
  
 Varlık SQL sorgusu komutun kendisindeki işlevleri tanımlamanızı sağlar. [İşlevi](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) işleci satır içi işlevleri tanımlar. İşlev imzası benzersiz olduğu sürece bu işlevler işlevi aynı ada sahip olabilir ve birden çok işlevleri tek bir komutta tanımlayabilirsiniz. Daha fazla bilgi için [işlev aşırı yükleme çözünürlüğü](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
- [İşlevler](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
