---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: 8fc5d1afd9e9723e6b3c58e100b0519ef8fdfab4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968370"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Bir yordam parametresinin, belirtilen türde öğe için isteğe bağlı bir dizi aldığını belirtir. `ParamArray`, yalnızca bir parametre listesinin son parametresinde kullanılabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 `ParamArray`yordama rastgele sayıda bağımsız değişken geçirmenize olanak sağlar. Bir `ParamArray` parametre, her zaman [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)kullanılarak bildirilmiştir.  
  
 Uygun veri türünde bir diziyi, virgülle ayrılmış bir `ParamArray` değer listesini veya hiç bir şeyi geçirerek bir parametreye bir veya daha fazla bağımsız değişken sağlayabilirsiniz. Ayrıntılar için, [parametre dizilerindeki](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)"ParamArray çağırma" konusuna bakın.  
  
> [!IMPORTANT]
> Süresiz olarak büyük olabilecek bir dizi ile uğraşmanız durumunda, uygulamanızın bazı iç kapasitesini çok fazla çalıştırmaya yönelik bir risk vardır. Çağıran koddan bir parametre dizisini kabul ediyorsanız, uzunluğunu sınamanız ve uygulamanız için çok büyükse uygun adımları uygulamanız gerekir.  
  
 `ParamArray` Değiştirici şu bağlamlarda kullanılabilir:  
  
 [Declare Deyimi](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function Deyimi](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Deyimi](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Deyimi](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Anahtar Sözcükler](../../../visual-basic/language-reference/keywords/index.md)
- [Parametre Dizileri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
