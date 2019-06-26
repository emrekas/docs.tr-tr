---
title: Derleyicinin ürettiği özel durumlar - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 28e6ba0c20948aa769a1517c664db80b5beb6b68
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67398024"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a>Derleyicinin Ürettiği Özel Durumlar (C# Programlama Kılavuzu)
Temel işlemleri başarısız olduğunda bazı özel durumlar, .NET Framework'ün ortak dil çalışma zamanı tarafından (CLR) otomatik olarak atılır. Bu özel durumları ve bunların hata koşulları aşağıdaki tabloda listelenmiştir.  
  
|Özel Durum|Açıklama|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|Gibi aritmetik işlemler sırasında oluşan özel durumlar için temel sınıf <xref:System.DivideByZeroException> ve <xref:System.OverflowException>.|  
|<xref:System.ArrayTypeMismatchException>|Öğesinin gerçek türü dizinin gerçek türü ile uyumsuz olduğundan bir dizi belirli bir öğeyi depolanamıyor zaman oluşturulur.|  
|<xref:System.DivideByZeroException>|Bir bölme bir tamsayı değeri sıfıra girişimde zaman oluşturulur.|  
|<xref:System.IndexOutOfRangeException>|Dizi dizini sıfırdan küçük veya dizi sınırları dışında olduğunda dizin için bir girişimde zaman oluşturulur.|  
|<xref:System.InvalidCastException>|Açık dönüştürme bir arabirim veya türetilmiş bir tür için bir temel türden çalışma zamanında başarısız olduğunda oluşturulur.|  
|<xref:System.NullReferenceException>|Değeri olan bir nesneye başvurmak denediğinizde durum [null](../../../csharp/language-reference/keywords/null.md).|  
|<xref:System.OutOfMemoryException>|Kullanarak bellek ayırma denemesi olduğunda oluşturulan [yeni](../../../csharp/language-reference/operators/new-operator.md) işleci başarısız olur. Bu, ortak dil çalışma zamanı için kullanılabilir bellek tükendi gösterir.|  
|<xref:System.OverflowException>|Aritmetik işlemin içinde olduğunda oluşturulan bir `checked` bağlam taşıyor.|  
|<xref:System.StackOverflowException>|Çok fazla bekleyen yöntem çağrılarını sağlayarak yürütme yığın kaldığında oluşturulur; genellikle çok derin veya sonsuz özyineleme gösterir.|  
|<xref:System.TypeInitializationException>|Statik oluşturucu ve hiçbir uyumlu özel durum oluşturduğunda durum `catch` bunu yakalayıp yakalamayacağınıza karar yan tümcesi bulunmaktadır.|  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [Özel Durumlar ve Özel Durum İşleme](../../../csharp/programming-guide/exceptions/index.md)
- [Özel Durum İşleme](../../../csharp/programming-guide/exceptions/exception-handling.md)
- [try-catch](../../../csharp/language-reference/keywords/try-catch.md)
- [try-finally](../../../csharp/language-reference/keywords/try-finally.md)
- [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)
