---
title: soyut - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: 64f650df0a9f6e6279e21b9cbd5ff444ef5c7a49
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758442"
---
# <a name="abstract-c-reference"></a>abstract (C# Başvurusu)
`abstract` Değiştiricisi değiştirilmekte olan bir şey yok veya eksik bir uygulama olduğunu gösterir. Soyut değiştiricisi sınıflar, yöntemler, özellikler, dizin oluşturucular ve olaylar ile kullanılabilir. Kullanım `abstract` değiştiricisi bir sınıf yalnızca, kendi örneği değil, diğer sınıfların temel sınıf olarak düşünüldüğünü göstermek için bir sınıf bildiriminde. Üyeleri, soyut soyut sınıftan türeyen sınıflar tarafından uygulanması gereken olarak işaretlendi.
  
## <a name="example"></a>Örnek  
 Bu örnekte, sınıf `Square` uygulaması sağlamalısınız `GetArea` öğesinden türetildiği için `Shape`:  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 Soyut sınıflar, aşağıdaki özelliklere sahiptir:  
  
- Bir soyut sınıfı oluşturulamıyor.  
  
- Bir Özet sınıf, soyut yöntemler ve erişimcileri içerebilir.  
  
- Bir Özet sınıf değiştirmek mümkün değildir [korumalı](../../../csharp/language-reference/keywords/sealed.md) değiştiricisi çünkü iki değiştirici karşı anlamları vardır. `sealed` Değiştiricisi devralınan öğesinden bir sınıf engeller ve `abstract` değiştiricisi bir sınıf devralma gerektirir.  
  
- Soyut bir sınıftan bir Özet olmayan sınıftan devralınan tüm soyut yöntemler ve erişimcileri gerçek uygulamaları içermesi gerekir.  
  
 Kullanım `abstract` yöntemi veya özelliği uygulaması içermiyor belirtmek için bir yöntem veya özellik bildiriminde değiştiricisi.  
  
 Soyut yöntemler aşağıdaki özelliklere sahiptir:  
  
- Soyut Metoda örtük olarak sanal bir yöntemdir.  
  
- Soyut yöntem bildirimleri yalnızca soyut sınıfları izin verilir.  
  
- Bir soyut yöntem bildiriminde gerçek uygulaması sağladığından, herhangi bir yöntem gövdesi yoktur; yöntem bildiriminde yalnızca noktalı virgül ile sona erer ve imza izleyen hiçbir küme ayracı ({}) vardır. Örneğin:  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     Uygulama yöntemi tarafından sağlanan [geçersiz kılma](../../../csharp/language-reference/keywords/override.md), soyut olmayan sınıf üyesi olduğu.  
  
- Kullanılacak bir hata olduğunu [statik](../../../csharp/language-reference/keywords/static.md) veya [sanal](../../../csharp/language-reference/keywords/virtual.md) soyut yöntem bildiriminde değiştiriciler.  
  
 Soyut özellikler, bildirim ve çağırma söz dizimi farklılıkları dışında soyut yöntemler gibi davranır.  
  
- Kullanılacak bir hata olduğunu `abstract` değiştirici statik bir özellik.  
  
- Devralınan soyut bir özelliğin kullanan bir özellik bildirimi dahil olmak üzere türetilen bir sınıfta kılınabilir [geçersiz kılma](../../../csharp/language-reference/keywords/override.md) değiştiricisi.  
  
 Soyut sınıflar hakkında daha fazla bilgi için bkz: [soyut ve korumalı sınıflar ve sınıf üyeleri](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Bir soyut sınıf uygulama için tüm arabirim üyeleri sağlamanız gerekir.  
  
 Bir arabirimi uygulayan bir Özet sınıf, arabirim yöntemleri soyut yöntemler üzerine eşleyebilir. Örneğin:  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a>Örnek  
 Bu örnekte, sınıf `DerivedClass` soyut bir sınıftan türetilen `BaseClass`. Soyut bir yöntemi soyut sınıfını içeren `AbstractMethod`ve iki soyut Özellikler `X` ve `Y`.  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 Önceki örnekte, böyle bir deyimi kullanarak soyut sınıfın örneği çalışırsanız:  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
Derleyici 'BaseClass' soyut sınıfının bir örneğini oluşturamazsınız belirten bir hata alırsınız.  
  
## <a name="c-language-specification"></a>C# Dil Belirtimi  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [Değiştiriciler](../../../csharp/language-reference/keywords/modifiers.md)
- [virtual](../../../csharp/language-reference/keywords/virtual.md)
- [override](../../../csharp/language-reference/keywords/override.md)
- [C# Anahtar Sözcükleri](../../../csharp/language-reference/keywords/index.md)
