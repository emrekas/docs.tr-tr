---
title: COM Sarmalayıcıları
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b633239be85a66c5bba54132c3732357967eb177
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61643663"
---
# <a name="com-wrappers"></a>COM Sarmalayıcıları
COM, .NET Framework nesne modeli birkaç önemli şekilde farklıdır:  
  
- COM nesnelerinin istemcileri bu nesnelerin ömrünü yönetmek gerekir; Ortak dil çalışma zamanı ortam nesnelerin ömrünü yönetir.  
  
- COM nesnelerinin istemcileri, hizmet bu hizmeti sağlayan bir arabirimi isteyen ve bir arabirim işaretçisi veya geri alma kullanılabilir olup olmadığını bulur. .NET nesnelerinin istemcileri, yansıma kullanarak bir nesnenin işlevlerinin açıklaması aşağıda elde edebilirsiniz.  
  
- NET nesneler, .NET Framework yürütme ortamı tarafından yönetilen bellekte yer alır. Yürütme Ortamı, performans nedenleriyle bellekte nesnelerin değiştirmemiz ve onunla nesneler için tüm başvuruları güncelleştirin. Yönetilmeyen istemciler, bir nesneye bir işaretçi elde aynı konumda kalır nesnesine bağlıdır. Bu istemciler konumu sabit bir nesne başa çıkmak için bir mekanizma vardır.  
  
 Bu farklar aşmak için çalışma zamanı hem yönetilen hem de yönetilmeyen istemcileri düşünün, kendi ortamlarından nesnelerinde çağırdığınızdan emin olmak için sarmalayıcı sınıflar sağlar. Yönetilen istemci bir COM nesnesi üzerinde bir yöntemi çağırdığında, çalışma zamanı oluşturur bir [çalışma zamanı çağrılabilir sarmalayıcı](runtime-callable-wrapper.md) (RCW). RCW, başka şeylerin yanında, yönetilen ve yönetilmeyen başvurusu mekanizmaları arasındaki farklar soyut. Çalışma zamanı ayrıca oluşturur bir [COM çağrılabilir sarmalayıcısı](com-callable-wrapper.md) sorunsuz bir şekilde bir .NET nesnesi üzerinde bir yöntemi çağırmak bir COM istemcisi etkinleştirme işlemi geri almak için (CCW). Aşağıdaki çizimde gösterildiği gibi çağıran kodun açısından çalışma zamanı oluşturur hangi sarmalayıcı sınıfı belirler.  
  
 ![COM sarmalayıcı genel bakış](./media/com-wrappers/bidirectional-com-overview.gif)  
  
 Çoğu durumda standart RCW veya çalışma zamanı tarafından oluşturulan CCW sınır COM ve .NET Framework arasında çapraz aramalar için yeterli hazırlama sağlar. Özel öznitelikler kullanarak, çalışma zamanı temsil eden yönetilen ve yönetilmeyen kod yolu isteğe bağlı olarak ayarlayabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Gelişmiş COM birlikte çalışabilirliği](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))
- [Çalışma Zamanında Çağrılabilir Sarmalayıcı](runtime-callable-wrapper.md)
- [COM Çağrılabilir Sarmalayıcısı](com-callable-wrapper.md)
- [Standart sarmalayıcıları özelleştirme](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))
- [Nasıl yapılır: Çalışma zamanı aranabilir sarmalayıcılarını özelleştirme](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))
