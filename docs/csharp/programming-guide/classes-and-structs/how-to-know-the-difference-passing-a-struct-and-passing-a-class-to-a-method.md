---
title: 'Nasıl yapılır: Bir yapı geçirme ile bir sınıf geçirme arasındaki farkı bilme bir yönteme - başvuru C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
ms.openlocfilehash: f131f647d5335a011c5f446f847ed43fda019ade
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559291"
---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a>Nasıl yapılır: Yapı geçirme ile Metoda sınıf başvurusu geçirme arasındaki farkı bilme (C# Programlama Kılavuzu)
Aşağıdaki örnek nasıl geçirme gösterir bir [yapı](../../../csharp/language-reference/keywords/struct.md) bir yönteme geçirme'dan farklı bir [sınıfı](../../../csharp/language-reference/keywords/class.md) örneğinin bir yönteme. Örnekte, iki bağımsız değişkenler (yapı ve sınıf örneği) değere göre geçirilir ve her iki yöntem bağımsız değişkeninin bir alanın değerini değiştirin. Yapı başarılı olduğunda ne iletilen bir sınıfın örneğini geçirdiğinizde ne geçirilen gelen değiştiğinden ancak sonuçları iki yöntemden biriyle aynı değildir.  
  
 Bir yapı olduğundan bir [değer türü](../../../csharp/language-reference/keywords/value-types.md)olduğunda, [yapı değişkeni değer olarak](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) bir yöntem için yöntemi alır ve yapı bağımsız değişkeni bir kopyası üzerinde çalışır. Yöntem erişim özgün struct çağırma yöntemi yok ve bu nedenle herhangi bir şekilde değiştiremezsiniz. Yöntemi yalnızca kopya değiştirebilirsiniz.  
  
 Bir sınıf örneği bir [başvuru türüne](../../../csharp/language-reference/keywords/reference-types.md), değer türü değil. Zaman [bir başvuru türü değere göre geçirilir](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) bir yönteme yöntemi bir sınıf örneği başvuru kopyasını alır. Diğer bir deyişle, yöntem, adresi örneğin bir kopya örneğin bir kopyasını alır. Bir adresi yöntemi çağrılırken, sınıf örneği olduğundan, çağrılan yöntem parametresinde adresi kopyasına sahip ve her iki adres aynı nesneye başvurur. Parametresi yalnızca bir kopya adres içerdiğinden, çağrılan yöntem yöntemi çağrılırken, sınıf örneğinin adresi değiştiremezsiniz. Ancak, çağrılan yöntem adresi hem özgün hem de kopya başvuru sınıf üyelerine erişmek için kullanabilirsiniz. Çağrılan yöntemi bir sınıf üyesinin değişirse, özgün sınıf örneği çağıran yöntem de değişir.  
  
 Aşağıdaki örnek çıktı, fark gösterilmiştir. Değerini `willIChange` alanı sınıf örneğinin yöntemine çağrı tarafından değiştirildiğinde `ClassTaker` sınıf örneğinin belirtilen alanı bulmak için parametreyi yöntemi adresini kullandığı için. `willIChange` Yöntemi çağrılırken yapıda alanına, yöntemine çağrı değiştirilmemiş `StructTaker` bağımsız değişkenin değerini struct'ın kendisi adresini değil bir kopyasını bir kopya olduğundan. `StructTaker` kopyalama ve kopyalama kayboluyor ne zaman değişiklikleri çağrısı `StructTaker` tamamlandı.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [Sınıflar](../../../csharp/programming-guide/classes-and-structs/classes.md)
- [Yapılar](../../../csharp/programming-guide/classes-and-structs/structs.md)
- [Parametreleri Geçirme](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)
