---
title: C# Diline ve.NET Framework'e Giriş
description: C# ve .NET ilişkin temel bilgileri öğrenin. C# dili ve .NET ekosisteminin bir bakış edinin.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, about C# language
- Visual C#, about
ms.assetid: 0a2dff4e-cd84-42ff-8141-e89889b24081
ms.openlocfilehash: bd2efcd28a8349ef07873adb5eaa69784e61d482
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65585946"
---
# <a name="introduction-to-the-c-language-and-the-net-framework"></a>C# Diline ve.NET Framework'e Giriş

C#.NET Framework üzerinde çalışan güvenli ve sağlam uygulamalar oluşturmalarını sağlayan bir şık ve tür kullanımı uyumlu nesne yönelimli dildir. Windows istemci uygulamaları, XML Web Hizmetleri, dağıtılmış bileşenler, istemci-sunucu uygulamaları, veritabanı uygulamaları ve çok daha fazlasını oluşturmak için C# kullanabilirsiniz. Görsel C# üzerinde uygulama geliştirmeyi kolaylaştırmak için Gelişmiş kod düzenleyici, uygun kullanıcı arabirimi tasarımcıları, tümleşik hata ayıklayıcı ve birçok diğer aracı sağlar C# dili ve .NET Framework.  
  
> [!NOTE]
> Visual C# belgeleri, temel programlama kavramlarını bir anlayışa sahip olduğunuzu varsayar. Tam bir acemiyseniz Web'de kullanılabilir olan keşfedin Visual C# Express, isteyebilirsiniz. Ayrıca kitaplardan ve Web kaynaklar hakkında pratik programlama becerilerini öğrenmek için C# yararlanabilirsiniz.  
  
## <a name="c-language"></a>C# Dili

 C# sözdizimi son derece etkileyicidir ve ayrıca basit ve öğrenilmesi kolaydır. C# küme ayracı sözdizimi, C, C++ veya Java ile tanıdık herkes için anında tanınabilir olacaktır. Bu dillerden herhangi birini bilen geliştiriciler genellikle üretken C# ' ta çok kısa bir süre içinde çalışmaya başlayabilir olanağına sahip olursunuz. C# sözdizimi, birçok c++ karmaşıklığını basitleştirir ve boş değer atanabilir türler, numaralandırmalar, temsilciler, lambda ifadeleri ve doğrudan bellek erişimi olan Java'da bulunmayan gibi güçlü özellikler sağlar. C# genel yöntemleri ve artan tür güvenliği ve performans ve koleksiyon sınıflarının Uygulayıcılara istemci kodu sayesinde kullanımı kolay olan özel yineleme davranışlarını tanımlamasına olanak tanıyan yineleyiciler sağlayan ve türleri destekler. [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] kesin türü belirtilmiş bir birinci sınıf dil yapısı sorgu ifadeleri olun.  
  
 Bir nesne yönelimli dil olarak C# kapsülleme, devralma ve çok biçimlilik kavramlarını destekler. Tüm değişkenler ve yöntemler de dahil olmak üzere, `Main` yöntemi, uygulamanın giriş noktası sınıf tanımlarına dahildir. Bir sınıf doğrudan bir üst sınıftan devralabilir, ancak herhangi bir sayıda arabirim uygulayabilir. Ana sınıfta sanal yöntemleri geçersiz kılan yöntemler gerektirir `override` yanlışlıkla yeniden tanımlanmasını önlemek için bir yol olarak anahtar sözcüğü. C# ' gibi basit bir sınıf bir yapı olduğunu; Bu arabirimleri gerçekleştiren ama devralmayı desteklemeyen bir yığın ayırma türüdür.  
  
 Bu temel nesne yönelimli ilkelere ek olarak, C# aşağıdakiler de dahil olmak üzere çok yenilikli dil yapısı üzerinden yazılım bileşeni geliştirmeyi kolaylaştırır:  
  
- Çağıran kapsüllenmiş yöntem imzaları *Temsilciler*, tür kullanımı uyumlu olay bildirimlerini etkinleştirin.  
  
- Özel üye değişkenleri için erişimci görevi gören özellikler.  
  
- Çalışma zamanında türler hakkında bildirime dayalı meta veriler sağlayan öznitelikler.  
  
- Inline XML belgeleri yorumları.  
  
- [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] çeşitli veri kaynakları yerleşik sorgu yetenekleri sağlar.  
  
 COM nesneleri veya yerel Win32 DLL'leri gibi başka bir Windows yazılımıyla etkileşim kurmak varsa, bunu yapabilirsiniz C# "Interop" olarak adlandırılan bir işlem aracılığıyla. Birlikte çalışma, neredeyse her şeyi bir yerel C++ uygulamalarının yapmak C# programları sağlar. C# dahi işaretçileri ve "güvenli olmayan" kod kavramını doğrudan bellek erişimi son derece kritik olduğu durumlarda destekler.  
  
 C# derleme işlem basittir C ve C++ karşılaştırıldığında ve Java olduğundan daha esnektir. Hiçbir ayrı üstbilgi dosyası ve yöntemler ve türleri, belirli bir sırada bildirilmesi gereken gereksinimi vardır. Bir C# kaynak dosyası sınıflar, yapılar, arabirimler ve olaylar herhangi bir sayıda tanımlayabilir.  
  
 Ek C# kaynakları şunlardır:  
  
- Bölüm 1 iyi genel bir giriş için bir dil için bkz [C# dil belirtimi](../../csharp/language-reference/language-specification/index.md).  
  
- C# dilinin belirli yönleri hakkında ayrıntılı bilgi için bkz. [C# başvurusu](../../csharp/language-reference/index.md).  
  
- Hakkında daha fazla bilgi için [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], bkz: [LINQ (dil ile tümleşik sorgu)](../programming-guide/concepts/linq/index.md).  

## <a name="net-framework-platform-architecture"></a>.NET framework Platform mimarisi

 C#.NET Framework, ortak dil çalışma zamanı (CLR) ve birleşik bir sınıf kitaplıkları kümesinin adlı bir sanal yürütme sistemi içeren Windows ayrılmaz bir bileşeni programları çalıştırın. CLR ticari Microsoft tarafından ortak dil altyapısı (CLI), yürütme ve diller ve kitaplıkların birlikte sorunsuz çalıştığı geliştirme ortamları oluşturmak için temel olan uluslararası bir standart uygulamasıdır.  
  
 C# dilinde yazılan kaynak kodu CLI belirtimine uyan bir ara dil (IL) derlenir. IL kodu ve bit eşlemler ve dizeler gibi kaynaklar genellikle .exe veya .dll uzantılı derleme adında çalıştırılabilir bir dosyada diskte depolanır. Bir derleme, derlemenin türleri, sürümü, kültürü ve güvenlik gereksinimleri hakkında bilgi sağlayan bir bildirim içerir.  
  
 C# programı yürütüldüğünde derleme bildirimdeki bilgilere göre çeşitli eylemlerde bulunabilecek olan CLR'ye içine yüklenir. Ardından, güvenlik gereksinimleri karşılanırsa, CLR IL kodunu yerel makine yönergelerine dönüştürmek için tam zamanında (JIT) derleme gerçekleştirir. CLR ayrıca diğer hizmetleri ilgili otomatik çöp toplama, özel durum işleme ve kaynak yönetimi sağlar. CLR tarafından yürütülen kod bazen "yönetilen kod" ", belirli bir sistemi hedefleyen yerel makine dilinde derlenmiş yönetilmeyen kodun" aksine adlandırılır. Aşağıdaki diyagram, C# kaynak kodu dosyaları, .NET Framework sınıf kitaplıkları, derlemeler ve CLR derleme zamanı ve çalışma zamanı ilişkilerini gösterir.  
  
 ![C&#35; kaynak kodu için makine yürütme](./media/introduction-to-the-csharp-language-and-the-net-framework/net-architecture-relationships.png)  
  
 Dil birlikte çalışabilirliği, .NET Framework'ün önemli bir özelliktir. C# derleyicisi tarafından üretilen IL kodu ortak tür belirtimi (CTS) uygun olduğundan, C# kaynağından oluşturulan IL kodu Visual Basic, Visual C++ ya da 20'den fazla diğer CTS-uyumlu dilin herhangi birini .NET sürümlerinden oluşturulan kod ile etkileşim kurabilir. Tek bir derleme farklı .NET dillerinde yazılmış birçok modülü içerebilir ve yalnızca bunlar aynı dilde yazılmışlar gibi türleri birbirlerine başvurabilir.  
  
 Çalıştırma zamanı hizmetlerine ek olarak, .NET Framework ayrıca sağlayan çok çeşitli kullanışlı işlevsellik her şey için dosya giriş ve çıkış dize düzenlemesi XML ad alanları olarak düzenlenmiş 4000'den fazla sınıfları oluşan kapsamlı bir kitaplık içerir. , Windows Forms denetimlerine ayrıştırılıyor. Tipik C# uygulama .NET Framework sınıf kitaplığı kapsamlı bir şekilde ortak "tesisatı" işlerini ele almak için kullanır.  
  
 .NET Framework hakkında daha fazla bilgi için bkz. [Microsoft .NET Framework'ün genel bakış](../../framework/get-started/overview.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C#](../../csharp/index.md)
- [Visual C# ve Visual Basic'e Başlarken](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
