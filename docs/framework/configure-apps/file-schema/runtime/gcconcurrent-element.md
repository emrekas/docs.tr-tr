---
title: <gcConcurrent> Öğesi
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b2774c32b4ee3e67772f84d599ecc5dbeb6598b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252586"
---
# <a name="gcconcurrent-element"></a>\<gcConcurrent > öğesi

Ortak dil çalışma zamanının ayrı bir iş parçacığında çöp toplama işlemi yapıp yapmadığını belirtir.

[ **\<Yapılandırma >** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<çalışma zamanı >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<gcConcurrent >**  

## <a name="syntax"></a>Sözdizimi

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Öznitelikler ve öğeler

Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.

### <a name="attributes"></a>Öznitelikler

|Öznitelik|Açıklama|
|---------------|-----------------|
|`enabled`|Gerekli öznitelik.<br /><br /> Çalışma zamanının çöp toplamayı eşzamanlı olarak çalıştırmasını belirtir.|

## <a name="enabled-attribute"></a>enabled özniteliği

|Değer|Açıklama|
|-----------|-----------------|
|`false`|Çöp toplamayı eşzamanlı olarak çalıştırmaz.|
|`true`|Çöp toplamayı eşzamanlı olarak çalıştırır. Bu varsayılandır.|

### <a name="child-elements"></a>Alt öğeleri

Yok.

### <a name="parent-elements"></a>Üst öğeler

|Öğe|Açıklama|
|-------------|-----------------|
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|
|`runtime`|Derleme bağlama ve atık toplama hakkında bilgi içerir.|

## <a name="remarks"></a>Açıklamalar

.NET Framework 4 ' ten önce, iş istasyonu atık toplama, farklı bir iş parçacığında arka planda çöp toplamayı gerçekleştiren eşzamanlı çöp toplama işlemini destekliyordu. .NET Framework 4 ' te, eşzamanlı atık toplama, arka plan GC ile değiştirilmiştir ve bu da ayrı bir iş parçacığında arka planda çöp toplama işlemi gerçekleştirir. .NET Framework 4,5 ' den başlayarak, arka plan koleksiyonu sunucu atık koleksiyonunda kullanılabilir hale geldi. `<gcConcurrent>` Öğesi, çalışma zamanının, varsa, eş zamanlı veya arka plan atık toplama işlemi gerçekleştirip gerçekleştirmediğini veya ön planda çöp toplama gerçekleştirip gerçekleştirmediğini denetler.

### <a name="to-disable-background-garbage-collection"></a>Arka plan atık toplamayı devre dışı bırakmak için

> [!WARNING]
> .NET Framework 4 ile başlayarak, eşzamanlı atık toplama arka plan atık toplama işlemi tarafından değiştirilir. *Eşzamanlı* ve *arka plan* terimleri .NET Framework belgelerde birbirinin yerine kullanılır. Arka plan atık toplamayı devre dışı bırakmak için `<gcConcurrent>` , bu makalede anlatıldığı gibi öğesini kullanın.

Varsayılan olarak, çalışma zamanı, gecikme süresi için en iyi duruma getirilmiş olan eşzamanlı veya arka plan çöp toplamayı kullanır. Uygulamanız ağır Kullanıcı etkileşimi içeriyorsa, çöp toplama işlemini gerçekleştirmek için uygulamanın duraklatma süresini en aza indirmek için eşzamanlı çöp toplamayı etkin bırakın. `enabled` Öğesinin özniteliğini olarak`false`ayarlarsanız, çalışma zamanı işleme için optimize edilmiş, eşzamanlı olmayan `<gcConcurrent>` çöp toplamayı kullanır. Aşağıdaki yapılandırma dosyası arka plan atık toplamayı devre dışı bırakır.

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 Makine yapılandırma dosyasında bir `<gcConcurrentSetting>` ayar varsa, tüm .NET Framework uygulamalar için varsayılan değeri tanımlar. Makine yapılandırma dosyası ayarı, uygulama yapılandırma dosyası ayarını geçersiz kılar.

 Eş zamanlı ve arka plan atık toplama hakkında daha fazla bilgi için [çöp toplama temelleri](../../../../standard/garbage-collection/fundamentals.md) makalesinin [eş zamanlı çöp toplama](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) bölümüne bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, eşzamanlı atık toplamayı mümkün bir şekilde sunar:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Çalışma Zamanı Ayarları Şeması](index.md)
- [Yapılandırma Dosyası Şeması](../index.md)
- [Atık Toplamanın Temelleri](../../../../standard/garbage-collection/fundamentals.md)
