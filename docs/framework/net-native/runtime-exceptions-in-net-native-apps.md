---
title: .NET Native Uygulamalarında Çalışma Zamanı Özel Durumları
ms.date: 03/30/2017
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6472f02cf2633d936252bfd2a8daa3ff711a4db8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967870"
---
# <a name="runtime-exceptions-in-net-native-apps"></a>.NET Native Uygulamalarında Çalışma Zamanı Özel Durumları
Hata ayıklama ve yayın yapılandırmaları tamamen farklı olduğundan, Evrensel Windows Platformu uygulamanızın sürüm yapılarını hedef platformlarda test etmek önemlidir. Varsayılan olarak, hata ayıklama yapılandırması uygulamanızı derlemek için .NET Core çalışma zamanını kullanır, ancak yayın yapılandırması uygulamanızı yerel koda derlemek için .NET Native kullanır.  
  
> [!IMPORTANT]
> Uygulamanızın yayın sürümlerini sınarken karşılaşabileceğiniz [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)ve [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) özel durumları ile ilgili bilgi için, bkz. "4. Adım: Eksik meta verileri el ile çözümleyin: [Başlarken](../../../docs/framework/net-native/getting-started-with-net-native.md) konusunun yanı sıra [yansıma ve .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md) ile [çalışma zamanı yönergeleri (RD. xml) yapılandırma dosyası başvurusu](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
## <a name="debug-and-release-builds"></a>Hata ayıklama ve yayın yapıları  
 Hata ayıklama derlemesi .NET Core çalışma zamanına karşı yürütüldüğünde, yerel koda derlenmemiş. Bu, normalde çalışma zamanı tarafından sağlanan tüm hizmetlerin uygulamanızda kullanılabilmesini sağlar.  
  
 Öte yandan, yayın derlemesi hedef platformları için yerel koda derlenir, dış çalışma zamanları ve kitaplıklarda birçok bağımlılığı kaldırır ve en yüksek performans için kodu yoğun olarak iyileştirir.  
  
 .NET Native kullanılarak derlenen sürüm Derlemeleriyle ilgili hataları ayıkladığınızda:  
  
- Normal .NET hata ayıklama araçlarından farklı olan .NET Native hata ayıklama altyapısını kullanırsınız.  
  
- Yürütülebilir dosyanızın boyutu mümkün olduğunca azalır. .NET Native bir yürütülebilir dosyanın boyutunu azaltmanın bir yolu, çalışma zamanı özel durum iletileri bölümünde daha ayrıntılı bir şekilde ele alınan çalışma zamanı özel durum iletilerini önemli [](#Messages) ölçüde kırpmasıdır.  
  
- Kodunuz yoğun bir şekilde iyileştirildi. Bu, mümkün olan her durumda satır içinde kullanıldığı anlamına gelir. (Intıl, kodu dış yordamlardan çağıran yordama taşıtırlar.)   .NET Native, özel bir çalışma zamanı sağlar ve agresif kullanımı uygularsa hata ayıklarken görüntülenen çağrı yığınını etkiler.  Daha fazla bilgi için bkz. [çalışma zamanı çağrı yığını](#CallStack) bölümü.  
  
> [!NOTE]
> Hata ayıklama ve sürüm derlemelerinin, **.NET Native araç zinciri Ile derle** kutusunu işaretleyerek veya işaretleyerek .NET Native araç zinciriyle derlenip derlenmediğini denetleyebilirsiniz.   Ancak, Windows Mağazası 'nın .NET Native araç zinciri ile uygulamanızın üretim sürümünü her zaman derlendiğine unutmayın.  
  
<a name="Messages"></a>   
## <a name="runtime-exception-messages"></a>Çalışma zamanı özel durum iletileri  
 Uygulama yürütülebilir boyutunu en aza indirmek için .NET Native özel durum iletilerinin tam metnini içermez. Sonuç olarak, sürüm Derlemeleriyle oluşturulan çalışma zamanı özel durumları, özel durum iletilerinin tam metnini görüntülemeyebilir. Bunun yerine, metin bir alt dizeden ve daha fazla bilgi için bir bağlantı ile birlikte yer alabilir. Örneğin, özel durum bilgileri şöyle görünebilir:  
  
```  
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 Tüm özel durum iletisine ihtiyacınız varsa, bunun yerine hata ayıklama derlemesini çalıştırın. Örneğin, yayın derlemeden önceki özel durum bilgileri hata ayıklama derlemesinde aşağıdaki gibi görünebilir:  
  
```  
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>   
## <a name="runtime-call-stack"></a>Çalışma zamanı çağrı yığını  
 Satır içi ve diğer iyileştirmeler nedeniyle, .NET Native araç zinciri tarafından derlenen bir uygulama tarafından görünen çağrı yığını, çalışma zamanı özel durumunun yolunu açıkça belirlemenize yardımcı olabilir.  
  
 Tam yığını almak için bunun yerine hata ayıklama derlemesini çalıştırın.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Windows Evrensel uygulamalarında .NET Native hata ayıklama](https://devblogs.microsoft.com/devops/debugging-net-native-windows-universal-apps/)
- [Başlarken](../../../docs/framework/net-native/getting-started-with-net-native.md)
