---
title: Türü Sağlayıcısı Güvenliği
description: Tür sağlayıcısı güvenliği hakkında bilgi edinin F#, bir tür sağlayıcısı güven ayarlarını değiştirme dahil olmak üzere.
ms.date: 05/16/2016
ms.openlocfilehash: 26f95ad3950b37a668c497f293b9941ed13a18c7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641846"
---
# <a name="type-provider-security"></a>Türü Sağlayıcısı Güvenliği

Tür sağlayıcıları tarafından başvurulan derlemeleri (DLL'ler) olan, F# dış veri kaynaklarına bağlanmak ve bu tür bilgileri yüzey için kod içeren proje veya betik F# ortam türü. Derleme ve ardından kod yürütmesine genellikle, başvurulan bütünleştirilmiş kod yalnızca çalıştırılır (veya bir betik söz konusu olduğunda, koda gönderme F# etkileşimli). Bununla birlikte, Kod Düzenleyicisi'nde yalnızca gözatarken bir tür sağlayıcısı derleme Visual Studio içinde çalışır. Tür sağlayıcıları Düzenleyicisi, hızlı bilgi araç ipuçları, IntelliSense tamamlamaları, gibi ek bilgileri ekleme ve benzeri çalıştırmak gerekeceğinden, bu gerçekleşir. Sonuç olarak, ek güvenlik konuları mevcuttur türü için sağlayıcı derlemeleri otomatik olarak Visual Studio işlemi içinde çalıştıkları bu yana.

## <a name="security-warning-dialog"></a>Güvenlik Uyarısı iletişim kutusu

Belirli tür sağlayıcısı derleme ilk kez kullanırken, Visual Studio tür sağlayıcısını çalıştırılmak üzere olduğunu uyaran bir güvenlik iletişim kutusu görüntülenir. Tür sağlayıcısını Visual Studio yüklemeden önce size bu belirli sağlayıcısına güveniyorsanız karar verme olanağı sağlar. Tür sağlayıcısını kaynağına güveniyorsanız, ardından "Bu tür sağlayıcısı güvendiğim." seçin Tür sağlayıcısını kaynağına güvenmiyorsanız, ardından "I bu tür sağlayıcısı güvenmeyin." seçin Sağlayıcı güvenen Visual Studio içinde çalıştırın ve IntelliSense sağlar ve yapı özellikleri sağlar. Ancak, kötü amaçlı bir tür sağlayıcısı ise, kodunu çalıştıran makinenize tehlikeye atabilecek.

Güven için iletişim kutusunda seçtiğiniz tür sağlayıcıları başvuran kod projenizi içeren, derleme zamanında derleyici tür sağlayıcısını güvenilmeyen olduğunu belirten bir hata bildirir. Güvenilmeyen türü sağlayıcısında bağımlı olan herhangi bir türü kırmızı dalgalı çizgiler gösterilir. Kod Düzenleyicisi'nde göz atmak güvenlidir.

Visual Studio'da doğrudan güven ayarını değiştirmeye karar verirseniz, aşağıdaki adımları gerçekleştirin.

### <a name="to-change-the-trust-settings-for-type-providers"></a>Tür sağlayıcıları güven ayarlarını değiştirmek için

1. Üzerinde `Tools` menüsünde `Options`, genişletin `F# Tools` düğümü.

2. Seçin `Type Providers`, tür sağlayıcıları listesinden, güvendiğiniz tür sağlayıcıları için onay kutusunu işaretleyin ve güvenmediğiniz olanlar için onay kutusunu temizleyin.

## <a name="see-also"></a>Ayrıca bkz.

- [Tür Sağlayıcıları](index.md)
