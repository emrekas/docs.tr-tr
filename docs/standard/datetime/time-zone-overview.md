---
title: Saat dilimine genel bakış
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], about time zones
- transition time [.NET Framework]
- TimeZoneInfo class, about TimeZoneInfo class
- time zones [.NET Framework], creating
- invalid time [.NET Framework]
- fixed rule [.NET Framework]
- ambiguous time [.NET Framework]
- floating rule [.NET Framework]
- daylight saving time [.NET Framework]
- adjustment rule [.NET Framework]
- time zones [.NET Framework], terminology
ms.assetid: c4b7ed01-5e38-4959-a3b6-ef9765d6ccf1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64fce738556fa68c54f5f7d7dcba79fc30d03bbe
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106730"
---
# <a name="time-zone-overview"></a>Saat dilimine genel bakış

<xref:System.TimeZoneInfo> Sınıfı, saat dilimi kullanan uygulamaların oluşturulmasını basitleştirir. <xref:System.TimeZone> Sınıfı, yerel saat dilimi ve Eşgüdümlü Evrensel Saat (UTC) ile çalışmayı destekler. <xref:System.TimeZoneInfo> Sınıfı bu bölgelerin her ikisini de ve kayıt defterinde önceden tanımlanmış bilgilerin bulunduğu herhangi bir saat dilimini destekler. Ayrıca, sistemin hakkında <xref:System.TimeZoneInfo> bilgi içermeyen özel saat dilimlerini tanımlamak için öğesini kullanabilirsiniz.

## <a name="time-zone-essentials"></a>Saat dilimi temelleri

Saat dilimi, aynı saatin kullanıldığı coğrafi bir bölgedir. Genellikle, bitişik saat dilimleri her zaman bir saattir. Dünyanın saat dilimlerinde bulunan zaman, Eşgüdümlü Evrensel Saat (UTC) arasında bir fark olarak ifade edilebilir.

Dünyanın çoğu saat dilimi gün ışığından yararlanma süresini destekler. Gün ışığından yararlanma saati, bahar veya erken yaz 'daki bir saat boyunca ilerleyerek ve geç yaz veya Fall içindeki normal (veya standart) zamana geri dönerek yaz saati süresini en üst düzeye çıkarmaya çalışır. Standart zamandan gelen ve bu değişiklikler ayarlama kuralları olarak bilinir.

Belirli bir saat diliminde gün ışığından yararlanma saatine geçiş yaparak, sabit veya kayan bir ayarlama kuralıyla tanımlanabilir. Sabit ayarlama kuralı, her yıl gün ışığından yararlanma saatine geçiş veya sunucudan geçen belirli bir tarihi ayarlar. Örneğin, gün ışığından yararlanma saatinden her yıl 25 Ekim, bir sabit ayarlama kuralıyla oluşan standart saate geçiş yapılır. Çok daha yaygın olarak, belirli bir haftanın belirli bir gününü gün ışığından yararlanma saatine geçiş için belirli bir ayda belirleyen kayan ayar kuralları vardır. Örneğin, Mart ayının üçüncü Pazar günü gerçekleşen standart zamandan günışığından yararlanma saatine geçiş bir kayan ayarlama kuralına uyar.

Ayarlama kurallarını destekleyen saat dilimleri için, gün ışığından yararlanma saatine yapılan ve bu saate geçiş iki tür anormal kez oluşturulur: geçersiz süreler ve belirsiz zamanlar. Geçersiz bir saat, standart zamandan günışığından yararlanma saatine geçiş tarafından oluşturulan varolmayan bir süredir. Örneğin, bu geçiş belirli bir gün 2:00:00 ' da gerçekleşirse ve saat 3:00, her zaman aralığı 2:00 ile arasında değişir. ve 2:59:99 geçersiz. Belirsiz bir saat, tek bir saat diliminde iki farklı kez eşlenemeyen bir süredir. Günışığından yararlanma saatinden standart saate geçiş tarafından oluşturulur. Örneğin, bu geçiş belirli bir gün 2:00:00 ' da gerçekleşirse ve saat 1:00, her zaman aralığı 1:00 ile arasında değişir. ve 1:59:99 , standart bir saat veya yaz saati olarak yorumlanamaz.

## <a name="time-zone-terminology"></a>Saat dilimi terminolojisi

Aşağıdaki tabloda, Saat dilimleriyle çalışırken ve saat dilimi kullanan uygulamalar geliştirilirken yaygın olarak kullanılan terimler tanımlanmaktadır.

| Terim            | Tanım |
| --------------- | ---------- |
| Ayarlama kuralı | Standart saatten gün ışığından yararlanma saatine ve gün ışığından yararlanma zamanından standart saate geçişin ne zaman gerçekleşeceğini tanımlayan bir kural. Her ayarlama kuralı, kuralın yerinde olduğu zamanı tanımlayan bir başlangıç ve bitiş tarihine sahiptir (örneğin, ayarlama kuralı 1 Ocak 1986, 31 Aralık 2006), Delta (Standart saatin, uygulamanın sonucu olarak değiştiği zaman miktarı). e ayarlama kuralı) ve ayarlama dönemi boyunca geçişlerin gerçekleşeceği belirli bir tarih ve saat hakkında bilgi. Geçişler, sabit bir kural ya da kayan bir kural izleyebilir. |
| Belirsiz saat  | Tek bir saat diliminde iki farklı kez eşlenebilir bir zaman. Saat diliminin gün ışığından yararlanma saatinden standart saate geçiş sırasında olduğu gibi saat içinde saat olarak ayarlandığında meydana gelir. Örneğin, bu geçiş belirli bir gün 2:00:00 ' da gerçekleşirse ve saat 1:00, her zaman aralığı 1:00 ile arasında değişir. ve 1:59:99 , standart bir saat veya yaz saati olarak yorumlanamaz. |
| Sabit kural      | Gün ışığından yararlanma saatine geçiş için belirli bir tarihi ayarlayan bir ayarlama kuralı. Örneğin, gün ışığından yararlanma saatinden her yıl 25 Ekim, bir sabit ayarlama kuralıyla oluşan standart saate geçiş yapılır. |
| Kayan kural   | Belirli bir haftanın belirli bir gününü gün ışığından yararlanma saatine geçiş yapmak için belirli bir ay ayarlayan bir ayarlama kuralı. Örneğin, Mart ayının üçüncü Pazar günü gerçekleşen standart zamandan günışığından yararlanma saatine geçiş bir kayan ayarlama kuralına uyar. |
| Geçersiz zaman    | Standart zamandan gün ışığından yararlanma saatine geçişin yapıtı olan varolmayan bir zaman. Saat dilimi standart saatinden gün ışığından yararlanma saatine geçiş sırasında olduğu gibi saat içinde ileri doğru ayarlandığında meydana gelir. Örneğin, bu geçiş belirli bir gün 2:00:00 ' da gerçekleşirse ve saat 3:00, her zaman aralığı 2:00 ile arasında değişir. ve 2:59:99 geçersiz. |
| Geçiş süresi | Belirli bir saat diliminde gün ışığından yararlanma saatinden standart saate veya bunun tersini değiştirme gibi belirli bir zaman değişikliği hakkında bilgiler. |

## <a name="time-zones-and-the-timezoneinfo-class"></a>Saat dilimleri ve TimeZoneInfo sınıfı

.NET sürümünde bir <xref:System.TimeZoneInfo> nesne bir saat dilimini temsil eder. Sınıfı <xref:System.TimeZoneInfo> <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> , nesne<xref:System.TimeZoneInfo.AdjustmentRule> dizisi döndüren bir yöntemi içerir. Bu dizinin her bir öğesi, belirli bir zaman aralığı için gün ışığından yararlanma saatine geçiş hakkında bilgi sağlar. (Yaz saati kaydetme süresini desteklemeyen saat dilimleri için, yöntem boş bir dizi döndürür.) Her <xref:System.TimeZoneInfo.AdjustmentRule> nesne bir ve <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> , gün ışığından yararlanma saatine yapılan geçişin belirli tarih ve saatini tanımlayan bir özelliğine sahiptir. Özelliği <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> , geçişin sabit veya kayan olduğunu gösterir.

.NET, Windows işletim sistemi tarafından sunulan ve kayıt defterinde depolanan saat dilimi bilgilerini kullanır. Dünya saat dilimlerinin sayısı nedeniyle, mevcut saat dilimlerinin hepsi kayıt defterinde gösterilmeyecektir. Ayrıca, kayıt defteri dinamik bir yapı olduğundan, önceden tanımlanmış saat dilimleri buna eklenebilir veya gruptan kaldırılabilir. Son olarak, kayıt defteri geçmiş saat dilimi verilerini içermez. Örneğin, Windows XP 'de kayıt defteri yalnızca tek bir saat dilimi ayarlamaları kümesiyle ilgili veriler içerir. Windows Vista dinamik saat dilimi verilerini destekler, bu da tek bir saat diliminin belirli yıl aralıklarında uygulanan birden çok ayarlama kuralına sahip olabileceği anlamına gelir. Ancak, Windows Vista kayıt defterinde tanımlanan ve gün ışığından yararlanma saatinin desteklediği çoğu bölge yalnızca bir veya iki öntanımlı ayarlama kuralına sahiptir.

Kayıt defterindeki <xref:System.TimeZoneInfo> sınıfının bağımlılığı, saat dilimi kullanan bir uygulamanın, kayıt defterinde belirli bir saat diliminin tanımlandığından emin olabileceği anlamına gelir. Sonuç olarak, belirli bir saat dilimini (yerel saat dilimi veya UTC 'yi temsil eden saat dilimi dışında) örneğini oluşturma girişimi özel durum işlemeyi kullanmalıdır. Ayrıca, gerekli <xref:System.TimeZoneInfo> bir nesne kayıt defterinden oluşturulamadıysanız uygulamanın devam etmesine izin vermek için bazı yöntemler sağlamalıdır.

Gerekli bir saat diliminin yokluğunu işlemek için, <xref:System.TimeZoneInfo> sınıfı, kayıt defterinde bulunmayan özel saat dilimlerini oluşturmak için kullanabileceğiniz bir <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> yöntemini içerir. Özel saat dilimi oluşturma hakkında ayrıntılı bilgi için bkz [. nasıl yapılır: Ayarlama kuralları](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) olmadan saat dilimleri oluşturun ve [şunları yapın: Ayarlama kuralları](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)ile saat dilimleri oluşturun. Ayrıca, yeni oluşturulan bir saat dilimini <xref:System.TimeZoneInfo.ToSerializedString%2A> bir dizeye dönüştürmek ve bir veri deposuna (örneğin, bir veritabanı, bir metin dosyası, kayıt defteri veya uygulama kaynağı) kaydetmek için yöntemini kullanabilirsiniz. Daha sonra bu dizeyi bir <xref:System.TimeZoneInfo.FromSerializedString%2A> <xref:System.TimeZoneInfo> nesneye geri dönüştürmek için yöntemini kullanabilirsiniz. Ayrıntılar için bkz [. nasıl yapılır: Zaman dilimlerini gömülü bir kaynağa](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) kaydedin ve [şunları yapın: Katıştırılmış bir kaynaktan](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)saat dilimlerini geri yükleyin.

Her saat dilimi UTC 'den temel bir uzaklığa göre ve mevcut ayarlama kurallarını yansıtan UTC 'den bir uzaklığa göre, bir saat dilimindeki bir zaman, başka bir saat dilimindeki zamana kolayca dönüştürülebilir. Bu amaçla <xref:System.TimeZoneInfo> , nesnesi aşağıdakiler dahil olmak üzere çeşitli dönüştürme yöntemleri içerir:

- <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>, UTC 'yi belirlenen saat dilimindeki zamana dönüştürür.

- <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, belirlenen saat dilimindeki saati UTC 'ye dönüştürür.

- <xref:System.TimeZoneInfo.ConvertTime%2A>, belirli bir saat dilimindeki saati, başka bir belirlenen saat dilimindeki zamana dönüştürür.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, belirli bir saat dilimindeki saati başka bir belirlenen <xref:System.TimeZoneInfo> saat diliminde saate dönüştürmek için parametre olarak saat dilimi tanımlayıcıları (nesneler yerine) kullanır.

Saatleri saat dilimleri arasında dönüştürme hakkında daha fazla bilgi için bkz. [saat dilimleri arasında süreleri dönüştürme](../../../docs/standard/datetime/converting-between-time-zones.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Tarihler, saatler ve saat dilimleri](../../../docs/standard/datetime/index.md)
