---
title: C# öznitelikleri - C# dili turu
description: Öznitelikleri kullanarak C# ' de bildirim temelli programlama hakkında bilgi edinin
ms.date: 08/10/2016
ms.assetid: 753bcfe2-7ddd-4487-9513-ba70937fc8e9
ms.openlocfilehash: a8ee40e5d4956667dd54cf25cc7993d041cba6e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61706565"
---
# <a name="attributes"></a>Öznitelikler

Bazı yönlerini davranışlarını denetleyen değiştiriciler, türleri, üyeleri ve diğer varlıkların bir C# programında destekler. Örneğin, bir yöntemin erişilebilirliği kullanılarak denetlenir `public`, `protected`, `internal`, ve `private` değiştiriciler. Bildirim temelli bilgileri kullanıcı tanımlı türde program varlıklara bağlı ve çalışma zamanında alınan C# bu özellik genelleştirir. Programlar belirtmek bu ek tanımlayıcı bilgiler tanımlama ve kullanma ***öznitelikleri***.

Aşağıdaki örnek bildirir bir `HelpAttribute` , ilişkili belgelere bağlantılar sağlamak için program varlıkları yerleştirildiği özniteliği.

[!code-csharp[AttributeDefined](../../../samples/snippets/csharp/tour/attributes/Program.cs#L3-L20)]

Tüm öznitelik sınıfları türetilmesi <xref:System.Attribute> temel standart kitaplığı tarafından sağlanan sınıfı. Öznitelik, köşeli ayraç içinde ilişkili bildirimi hemen önce tüm bağımsız değişkenleri yanı sıra bunların adı vererek uygulanabilir. Bir özniteliğin adı biterse `Attribute`, öznitelik başvurulduğunda bu bölümü adı atlanmış olabilir. Örneğin, `HelpAttribute` gibi kullanılabilir.

[!code-csharp[AttributeApplied](../../../samples/snippets/csharp/tour/attributes/Program.cs#L22-L28)]

Bu örnekte bağlayan bir `HelpAttribute` için `Widget` sınıfı. Başka bir ekler `HelpAttribute` için `Display` sınıfında yöntemi. Genel oluşturucular bir öznitelik sınıfı özniteliği için bir program varlığı eklendiğinde sağlanmalıdır bilgileri denetler. Ek bilgi öznitelik sınıfının ortak okuma-yazma özelliklerine başvurarak sağlanabilir (başvuru gibi `Topic` özelliği daha önce).

Öznitelikleri tarafından tanımlanan meta verileri okuyun ve yansıma kullanarak çalışma zamanında değiştirilebilir. Bu tekniği kullanarak belirli bir özniteliği istendiğinde program kaynakta sağlanan bilgileri ile öznitelik sınıfı için oluşturucu çağrılır ve sonuçta elde edilen öznitelik örneği döndürülür. Ek bilgi özellikleri aracılığıyla sağlandıysa, öznitelik örneği döndürülmeden önce bu özellikleri için belirtilen değerlere ayarlanır.

Aşağıdaki kod örneği nasıl alındığını anlatan `HelpAttribute` ilişkili örnekleri `Widget` sınıf ve onun `Display` yöntemi.

[!code-csharp[AttributeRead](../../../samples/snippets/csharp/tour/attributes/Program.cs#ReadAttributes)]

>[!div class="step-by-step"]
>[Önceki](delegates.md)