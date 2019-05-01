---
title: Kullanıcı Tarafından Filtrelenmiş Özel Durum İşleyicilerini Kullanma
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 228bae8db833abfa3c8c906d57e2177cde644548
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945463"
---
# <a name="using-user-filtered-exception-handlers"></a>Kullanıcı Tarafından Filtrelenmiş Özel Durum İşleyicilerini Kullanma

Şu anda, Visual Basic, kullanıcı tarafından filtrelenmiş özel durumu destekler. Kullanıcı tarafından filtrelenmiş özel durum işleyicileri catch ve özel durum için tanımladığınız gereksinimlerine göre özel durumları işleyin. Bu işleyicilerini **Catch** deyimiyle **olduğunda** anahtar sözcüğü.  
  
 Bu teknik, belirli bir özel durum nesnesi için birden çok hata karşılık gelen yararlıdır. Bu durumda, nesne, genellikle hatayla ilişkili söz konusu hata kodunu içeren bir özelliğe sahiptir. Yalnızca, işlemek istediğiniz belirli hata seçmek için ifade hata kodu özelliğini kullanabilirsiniz **Catch** yan tümcesi.  
  
 Aşağıdaki Visual Basic örnek gösterir **Catch/olduğunda** deyimi.  
  
```vb
Try  
    'Try statements.  
    Catch When Err = VBErr_ClassLoadException
    'Catch statements.
End Try  
```  
  
 Kullanıcı tarafından filtrelenmiş yan tümcesinin ifadesi herhangi bir yolla sınırlı değildir. Kullanıcı tarafından filtrelenmiş ifadenin yürütülmesi sırasında bir özel durum meydana gelirse, o özel durumu atılır ve filtre ifadesi false olarak değerlendirildi olarak kabul edilir. Bu durumda, ortak dil çalışma zamanı, geçerli özel durum işleyicisi için arama devam eder.  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a>Özel durum ve kullanıcı tarafından filtrelenmiş yan tümceleri birleştirme  
 Catch deyimi, hem özel hem de kullanıcı tarafından filtrelenmiş yan tümceleri içerebilir. Çalışma zamanı özel duruma önce test eder. Özel durum başarılı olursa, çalışma zamanı kullanıcı filtresini yürütür. Genel filtre sınıfı filtrede bildirilen değişken başvuru içerebilir. İki filtre yan tümcesi sırasını ters unutmayın.  
  
 Aşağıdaki Visual Basic örnek, belirli özel durum gösterir `ClassLoadException` içinde **Catch** deyimi hem de kullanıcı tarafından filtrelenmiş yan tümcesini kullanarak **olduğunda** anahtar sözcüğü.  
  
```vb
Try  
    'Try statements.
    Catch cle As ClassLoadException When cle.IsRecoverable()  
    'Catch statements.
End Try  
```  

## <a name="see-also"></a>Ayrıca bkz.

- [Özel Durumlar](index.md)
