---
title: 'Nasıl yapılır: Son olarak - kullanarak temizleme kodu yürütme C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: 0ec661e5fb0e13eaf8c3c8e4a7b274ab58853f58
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978091"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a>Nasıl yapılır: Finally anahtar sözcüğünü kullanarak temizleme kodu yürütme (C# Programlama Kılavuzu)
Amacı, bir `finally` deyimdir bile bir özel durum nesneleri, genellikle dış kaynakları tutan nesnelerin gerekli temizleme hemen olmasını sağlamak için. Bu tür temizleme örneği çağırır <xref:System.IO.Stream.Close%2A> üzerinde bir <xref:System.IO.FileStream> nesne gibi ortak dil çalışma zamanı tarafından toplanan çöp olmasını beklemek yerine hemen kullandıktan sonra:  
  
 [!code-csharp[csProgGuideExceptions#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#16)]  
  
## <a name="example"></a>Örnek  
 Önceki kodun içine açmak için bir `try-catch-finally` deyimi, temizleme kodunu ayrılmış çalışan koddan gibi.  
  
 [!code-csharp[csProgGuideExceptions#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#17)]  
  
 Dilediğiniz zaman içinde bir özel durum gerçekleşebileceği için `try` önce block `OpenWrite()` çağrısı, veya `OpenWrite()` çağrının kendisini işlemi başarısız olabilir, biz kapatmak denediğinizde dosyayı açık olduğunu garanti edilmez. `finally` Blok emin olmak için bir denetim ekler <xref:System.IO.FileStream> nesne `null` çağırmadan önce <xref:System.IO.Stream.Close%2A> yöntemi. Olmadan `null` denetleyin, `finally` blok throw kendi <xref:System.NullReferenceException>, ancak özel durumları atma `finally` mümkünse blokları kaçınılmalıdır.  
  
 Veritabanı bağlantısı kapatıldığından kuşkulanılıyor için başka bir iyi aday olan bir `finally` blok. Veritabanı sunucusu için izin verilen bağlantı sayısını bazen sınırlı olduğundan, veritabanı bağlantıları mümkün olan en kısa sürede kapatmalısınız. Bağlantınızı kapatmadan önce bir özel durum oluşturulursa, başka bir durum budur kullanıldığında `finally` blok çöp toplama için bekleyen daha iyidir.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [Özel Durumlar ve Özel Durum İşleme](../../../csharp/programming-guide/exceptions/index.md)
- [Özel Durum İşleme](../../../csharp/programming-guide/exceptions/exception-handling.md)
- [using Deyimi](../../../csharp/language-reference/keywords/using-statement.md)
- [try-catch](../../../csharp/language-reference/keywords/try-catch.md)
- [try-finally](../../../csharp/language-reference/keywords/try-finally.md)
- [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)
