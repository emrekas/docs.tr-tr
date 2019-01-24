---
title: '#elif - C# başvurusu'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 00a9298be6ecd6f5e775d930190ddb6e227e4711
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587235"
---
# <a name="elif-c-reference"></a>#elif (C# Başvurusu)
`#elif` bir bileşik koşullu yönergesi oluşturmanıza olanak sağlar. `#elif` Kullanılmazsa, ifade değerlendirilir önceki [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) veya hiçbir, isteğe bağlı, önceki `#elif` yönerge nevyhodnocovat için `true`. Varsa bir `#elif` ifadeyi hesaplar için `true`, derleyicinin kod arasında değerlendirir `#elif` ve sonraki koşullu yönergesi. Örneğin:  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 İşleçleri `==` (eşitlik) `!=` (eşitsizlik) `&&` (ve) ve `||` (veya) birden çok sembolleri değerlendirilecek. Ayrıca, simgeler ve işleçler parantezli gruplandırabilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 `#elif` kullanmakla eşdeğerdir:  
  
```csharp
#else  
#if  
```  
  
 Kullanarak `#elif` basittir çünkü her `#if` gerektiren bir [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)bilgileriyse bir `#elif` eşleşmeyen kullanılabilir `#endif`.  
  
 Bkz: [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) nasıl kullanılacağına ilişkin bir örnek `#elif`.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [C# Ön İşlemci Yönergeleri](../../../csharp/language-reference/preprocessor-directives/index.md)
