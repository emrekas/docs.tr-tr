---
title: Genel rehber
description: Kapsayıcılı .NET uygulamaları için .NET mikro hizmet mimarisi | Genel rehberlik
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: 6ff6170fd1cdd0c69ecc8729cc8199cceea43ffa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62019717"
---
# <a name="general-guidance"></a>Genel rehber

Bu bölümde, ne zaman .NET Core veya .NET Framework seçin, bir özetini sağlar. Aşağıdaki bölümlerde bu seçenekler hakkında daha fazla bilgi sağlıyoruz.

.NET Core, Linux veya Windows kapsayıcıları ile kapsayıcılı Docker sunucusu uygulamanız için kullanmanız gereken zaman:

- Platformlar arası ihtiyaçları vardır. Örneğin, hem Linux hem de Windows kapsayıcıları kullanmak istiyorsunuz.

- Uygulama mimarinizin üzerinde mikro hizmetler temel alır.

- Kapsayıcıları Hızlı Başlat ve maliyetlerinizi azaltmak için daha iyi yoğunluklu elde etmek için kapsayıcı ya da daha fazla kapsayıcı donanım birim başına küçük ayak izine gerekir.

Kısacası, yeni kapsayıcılı .NET uygulamaları oluşturduğunuzda varsayılan seçenek olarak .NET Core düşünmelisiniz. Kapsayıcıları felsefesi ve çalışma tarzıyla ile gereksinimlerine ve pek çok faydası vardır.

.NET Core kullanmanın ek bir avantaj, aynı makineye içindeki uygulamalar için .NET sürümleri yan yana çalıştırabileceğiniz ' dir. Uygulama gerektiren .NET sürümlerini kapsayıcıları yalıtmak için bu sunucuları veya kapsayıcılar, kullanmayan sanal makineleri için önemli bir avantajdır. (Bunlar temel işletim sistemi ile uyumlu olduğu sürece.)

.NET Framework kapsayıcılı Docker sunucusu uygulamanız için kullanması gereken zaman:

- Uygulamanız şu anda kullandığı .NET Framework ve Windows üzerinde güçlü bağımlılıkları vardır.

- .NET Core tarafından desteklenmeyen bir Windows API'leri kullanmanız gerekir.

- Üçüncü taraf .NET kitaplıkları veya .NET Core için kullanılabilir değil, NuGet paketlerini kullanmanız gerekir.

Docker üzerinde .NET Framework kullanarak dağıtım sorunlarını en aza indirerek, dağıtım deneyimleri geliştirebilir. Bu ["kaldırma ve kaydırma" senaryo](https://aka.ms/liftandshiftwithcontainersebook) ASP.NET WebForms, MVC web uygulamaları veya WCF (Windows Communication Foundation gibi ilk olarak geleneksel .NET Framework ile geliştirilen eski uygulamaları kapsayıcılı hale getirmek için önemlidir ) Hizmetleri.

### <a name="additional-resources"></a>Ek kaynaklar

- **e-kitap: Azure ve Windows kapsayıcıları ile mevcut .NET Framework uygulamalarını modernleştirin**  
    https://aka.ms/liftandshiftwithcontainersebook

- **Örnek uygulamalar: Windows kapsayıcıları kullanarak eski ASP.NET web uygulama modernizasyonu**  
    https://aka.ms/eshopmodernizing

>[!div class="step-by-step"]
>[Önceki](index.md)
>[İleri](net-core-container-scenarios.md)