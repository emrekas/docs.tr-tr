---
title: 'Nasıl yapılır: Gözlemci Uygulama'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b410b9381246cef2e61086e333c4c5b07646a575
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301067"
---
# <a name="how-to-implement-an-observer"></a>Nasıl yapılır: Gözlemci Uygulama
Gözlemci tasarım deseni için bildirimleri kaydeden bir gözlemci veri izler ve bir veya daha fazla gözlemciler için bildirim gönderen bir sağlayıcı arasındaki bölme işleminin gerektirir. Bu konu, bir gözlemci oluşturulacağını açıklar. İlgili konu başlığında, [nasıl yapılır: Sağlayıcıyı uygulama](../../../docs/standard/events/how-to-implement-a-provider.md), bir sağlayıcı oluşturma anlatılmaktadır.  
  
### <a name="to-create-an-observer"></a>Gözlemci oluşturmak için  
  
1. Gözlemci uygulayan bir tür tanımlamak <xref:System.IObserver%601?displayProperty=nameWithType> arabirimi. Örneğin, aşağıdaki kod adlı bir tür tanımlar `TemperatureReporter` diğer bir deyişle oluşturulmuş <xref:System.IObserver%601?displayProperty=nameWithType> bir genel tür bağımsız değişkeni uygulamasıyla `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2. Gözlemci bildirimleri sağlayıcısı çağrıları önce iptal ederseniz, <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> uygulaması barındıracak özel bir değişken tanımlayın <xref:System.IDisposable> sağlayıcının tarafından döndürülen uygulama <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> yöntemi. Ayrıca sağlayıcının çağıran bir abonelik yöntemi tanımlamalıdır <xref:System.IObservable%601.Subscribe%2A> yöntemi ve depoları döndürülen <xref:System.IDisposable> nesne. Örneğin, aşağıdaki kod adlı özel bir değişken tanımlar `unsubscriber` ve tanımlayan bir `Subscribe` sağlayıcının çağıran yöntemi <xref:System.IObservable%601.Subscribe%2A> yöntemi ve döndürülen nesneyi atar `unsubscriber` değişkeni.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3. Gözlemci sağlayıcısı çağrıları önce bildirim almayı durdurmak sağlayan bir yöntem tanımlayın, <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> uygulanması gerekirse bu özellik,. Aşağıdaki örnekte tanımlayan bir `Unsubscribe` yöntemi.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4. Uygulamaları tarafından tanımlanan üç yöntemi sağlamak <xref:System.IObserver%601> arabirimi: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, ve <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>. Sağlayıcı ve uygulama gereksinimlerine bağlı olarak <xref:System.IObserver%601.OnError%2A> ve <xref:System.IObserver%601.OnCompleted%2A> yöntemleri Koçan uygulamaları olabilir. Unutmayın <xref:System.IObserver%601.OnError%2A> yöntemi işlememek geçirilen <xref:System.Exception> nesnesi bir özel durum olarak ve <xref:System.IObserver%601.OnCompleted%2A> sağlayıcının çağırmak yöntem ücretsizdir <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> uygulaması. Aşağıdaki örnekte gösterildiği <xref:System.IObserver%601> uygulaması `TemperatureReporter` sınıfı.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, tam kaynak kodunu içerir. `TemperatureReporter` sağlar sınıfını <xref:System.IObserver%601> uygulaması için uygulama izleme bir sıcaklık.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.IObserver%601>
- [Gözlemci Tasarım Deseni](../../../docs/standard/events/observer-design-pattern.md)
- [Nasıl yapılır: Sağlayıcıyı uygulama](../../../docs/standard/events/how-to-implement-a-provider.md)
- [Gözlemci Tasarım Deseni En İyi Yöntemleri](../../../docs/standard/events/observer-design-pattern-best-practices.md)
