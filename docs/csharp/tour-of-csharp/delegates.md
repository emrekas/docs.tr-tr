---
title: C#Temsilciler - Turu C# dil
description: Geç bağlama ile bilgi C# temsilciler
ms.date: 08/10/2016
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: 2744f774392ef021974535de535b063264ae9a54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61706396"
---
# <a name="delegates"></a>Temsilciler

A ***temsilci türü*** belirli bir parametre olan yöntemlere başvuruları temsil listesi ve dönüş türü. Temsilciler, yöntemleri değişkenine atanır ve parametre olarak geçirilen varlıklar olarak değerlendirmek mümkün kılar. Diğer dillerde bulunan işlev işaretçileri kavramı temsilcileri benzerdir ancak işlev işaretçileri, nesne yönelimli ve tür kullanımı uyumlu temsilciler.

Aşağıdaki örnek bildirir ve adlandırılmış bir temsilci türü kullanır `Function`.

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

Örneği `Function` temsilci türü, alan herhangi bir yöntemi başvurabilir bir `double` bağımsız değişkeni ve döndürür bir `double` değeri. `Apply` Yöntemi öğelerine verilen işlevi uygular bir `double[]`, döndüren bir `double[]` sonuçları. İçinde `Main` yöntemi `Apply` üç farklı işlevlere uygulamak için kullanılan bir `double[]`.

Bir temsilci bir statik yöntem başvurabilir (gibi `Square` veya `Math.Sin` önceki örnekte) veya bir örnek yöntemi (gibi `m.Multiply` önceki örnekte). Bir örnek yöntemi başvuran bir temsilci Ayrıca belirli bir nesnenin başvuruda bulunduğundan ve temsilci örnek yöntemi çağrıldığında, bu nesne haline gelir `this` çağrısı.

Temsilciler da "anında oluşturulan satır içi yöntemler" anonim işlevler kullanılarak oluşturulabilir. Anonim İşlevler, yerel değişkenler çevreleyen yöntemlerden görebilirsiniz. Bu nedenle, yukarıdaki çarpan örneği daha kolay bir çarpan sınıf kullanmadan yazılabilir:

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

Bir ilgi çekici ve kullanışlı bir temsilci, bilmiyorsanız veya yöntemin başvurduğu sınıfı hakkında dikkatli olun, özelliğidir; önemli olan başvurulan yöntemi aynı parametre ve dönüş türü temsilciyle sahiptir.

>[!div class="step-by-step"]
>[Önceki](enums.md)
>[İleri](attributes.md)