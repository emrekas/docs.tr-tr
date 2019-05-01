---
title: İstemci tarafı doğrulaması (sunum katmanlarında doğrulama)
description: Kapsayıcılı .NET uygulamaları için .NET mikro hizmet mimarisi | İstemci tarafı doğrulama temel kavramlarını keşfedin.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/08/2018
ms.openlocfilehash: ddf53456f9356817d28cd0bfa75df3296fb5d722
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020068"
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a>İstemci tarafı doğrulaması (sunum katmanlarında doğrulama)

Etki alanı modeli gerçekte kaynağıdır ve sonuç olarak etki alanı model düzeyinde doğrulama olmalıdır bile hem etki alanı model düzeyi (sunucu tarafı) hem de kullanıcı Arabirimi (istemci tarafı) doğrulama hala işlenebilir.

İstemci tarafı doğrulama, kullanıcılar için harika bir kolaylığıdır. Gidiş dönüş bekleniyor aksi açabiliyorduk zaman doğrulama hataları döndürebilir sunucuya kaydeder. İş dünyasında bile birkaç kez her gün yüzlerce çarpılan saniyelerin kesirlerini ekler miktarda zaman harcama ve sıkıntıya. Basit ve anında doğrulama kullanıcıların giriş ve çıkış daha iyi kalite üreten ve daha verimli çalışmanıza olanak tanır.

Yalnızca görünüm modeli ve etki alanı modeli farklı olduğundan, görünüm model doğrulama ve etki alanı model doğrulama benzer ancak farklı bir amaca hizmet. İlgili ise bu durumda kod yeniden kullanımını bağlantısından de gelebilir ve kurumsal uygulamaları, sunucu tarafı KURU ilkesini izleyin üzere daha istemci tarafı için eşleştiği değil daha önemlidir (yoksa yineleyin kendiniz İlkesi) KURU hakkında göz önünde bulundurun.

Bile istemci tarafında doğrulama kullanırken her zaman komutlarınızı doğruladığınızda veya sunucu API'leri olası bir saldırı vektörü olduğundan sunucu kodunda Dto'lar giriş. Genellikle, ikisini de uygulamak UX açısından, bir istemci uygulaması varsa, proaktif ve geçersiz bilgi girmek için kullanıcıya izin en iyi olduğundan, en iyi sonuç olur.

Bu nedenle, istemci tarafı kod, genellikle Viewmodel'lar doğrulayın. Ayrıca istemci doğrulama hizmetlere göndermeden önce Dto'lar veya komutları çıktı.

İstemci tarafı doğrulama uygulanması, oluşturduğunuz ne tür bir istemci uygulaması bağlıdır. Xamarin ile mobil uygulama kodlanmış veya .NET, JavaScript veya TypeScript, kodlanmış bu doğrulama SPA web uygulamasıyla kodda çoğunu bir MVC web uygulaması Web verilerle doğrulamakta olduğunuz, farklı olacaktır ve C#.

## <a name="additional-resources"></a>Ek kaynaklar

### <a name="validation-in-xamarin-mobile-apps"></a>Xamarin mobil uygulamalarında doğrulama

- **Metin doğrulamak giriş ve hatalarını gösterme** \
  [https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

- **Doğrulama geri çağırma** \
  <https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/>

### <a name="validation-in-aspnet-core-apps"></a>ASP.NET Core uygulamaları doğrulama

- **Rick Anderson. Doğrulama ekleme** \
  <https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a>SPA doğrulama Web uygulamaları (Angular 2, TypeScript, JavaScript)

- **Ado Kukic. Angular 2 Form doğrulama** \
  <https://scotch.io/tutorials/angular-2-form-validation>

- **Form doğrulaması** \
  <https://angular.io/guide/form-validation>

- **Doğrulama.** Meltem belgeleri. \
  <https://breeze.github.io/doc-js/validation.html>

Özet olarak, doğrulama ilgili en önemli kavramları şunlardır:

- Varlıklar ve toplamalar kendi tutarlılığın ve "her zaman geçerli". Toplama kökleri aynı toplama içinde birden çok varlık tutarlılığı sorumludur.

- Bir varlık geçersiz bir durumda girmeniz gerektiğini düşünüyorsanız, farklı nesne modelini kullanarak göz önünde bulundurun — Örneğin, son etki alanı varlığı oluşturana kadar geçici bir DTO'ni kullanarak.

- Bir toplama gibi birçok ilgili nesneleri oluşturmanız gerekir ve bunların tümünü oluşturulduktan sonra yalnızca geçerli olduğu Fabrika deseni kullanmayı düşünün.

- Uygulama proaktif olarak olabileceğinden çalışmalarının çoğu istemci tarafı yedekli doğrulama sahip, uygundur.

>[!div class="step-by-step"]
>[Önceki](domain-model-layer-validations.md)
>[İleri](domain-events-design-implementation.md)
