---
title: <startup> öğesi
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: 022f0efbbb2e6e9a4ac9d3d7ddcc1fb1022cdbee
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169772"
---
# <a name="startup-element"></a>\<Başlangıç > öğesi

Ortak dil çalışma zamanı başlatma bilgileri belirtir.

 \<Yapılandırma > \<başlangıç >

## <a name="syntax"></a>Sözdizimi

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a>Öznitelikler ve öğeler

 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.

### <a name="attributes"></a>Öznitelikler

|Öznitelik|Açıklama|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|İsteğe bağlı öznitelik.<br /><br /> .NET Framework 2.0 çalışma zamanı etkinleştirme ilkesini etkinleştirin veya .NET Framework 4 etkinleştirme ilkesini kullanmak için belirtir.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2RuntimeActivationPolicy özniteliği

|Değer|Açıklama|
|-----------|-----------------|
|`true`|Eski çalışma zamanını etkinleştirme teknikleri bağlamak için seçilen çalışma için .NET Framework 2.0 çalışma zamanı etkinleştirme ilkesini etkinleştir (gibi [CorBindToRuntimeEx işlevi](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) bunun yerine yapılandırma dosyasından seçilen çalışma zamanı bunları CLR Version 2.0 sürümü capping biri. Bu nedenle, CLR 4 veya sonraki bir sürümü yapılandırma dosyasından seçilirse, .NET Framework'ün önceki sürümleriyle oluşturulmuş karışık mod derlemeleri seçilen CLR sürümü ile yüklenir. Bu değer ayarlandığında CLR sürüm 1.1 veya CLR Version 2.0 sürümü ile aynı işleme etkili bir şekilde işlem içi yan yana özelliğini devre dışı bırakma, yükleme engeller.|
|`false`|Eski çalışma zamanını etkinleştirme teknikleri'CLR sürüm 1.1 veya 2.0 işlemine yüklemeye izin ver olan .NET Framework 4 ve sonraki sürümlerinde, varsayılan etkinleştirme ilkesini kullanın. Bu değeri ayarlamak, karma mod derlemeler .NET Framework 4 veya sonraki sürümüyle oluşturulmuş karşılamadıkça .NET Framework 4 veya daha sonra yüklemeyi engeller. Bu varsayılan değerdir.|

### <a name="child-elements"></a>Alt öğeleri

|Öğe|Açıklama|
|-------------|-----------------|
|[\<requiredRuntime >](requiredruntime-element.md)|Uygulama yalnızca sürüm 1.0 ortak dil çalışma zamanının desteklediğini belirtir. Çalışma zamanı sürüm 1.1 veya üzeri ile oluşturulan uygulamaların kullanması gereken  **\<supportedRuntime >** öğesi.|
|[\<supportedRuntime >](supportedruntime-element.md)|Uygulamanın hangi ortak dil çalışma zamanı sürümünü desteklediğini belirtir.|

### <a name="parent-elements"></a>Üst öğeler

|Öğe|Açıklama|
|-------------|-----------------|
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|

## <a name="remarks"></a>Açıklamalar

 **\<SupportedRuntime >** öğesi sürüm 1.1 veya daha sonraki çalışma zamanı sürümü kullanılarak oluşturulan tüm uygulamalar tarafından kullanılması gerekir. Yalnızca sürüm 1.0 çalışma zamanını desteklemek için oluşturulan uygulamalar kullanmalıdır  **\<requiredRuntime >** öğesi.

 Microsoft Internet Explorer'da barındırılan bir uygulama için başlatma kodunun yoksayar  **\<başlangıç >** öğesi ve onun alt öğeleri.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>UseLegacyV2RuntimeActivationPolicy özniteliği

 Bu uygulamanız gibi eski etkinleştirme yollarını kullanıyorsa yararlı bir özniteliktir [CorBindToRuntimeEx işlevi](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), ve daha önceki bir sürümü yerine CLR'nin sürüm 4 etkinleştirmek için bu yollar istediğiniz veya uygulamanız ise ile oluşturulan, .NET Framework 4 ancak .NET Framework'ün önceki bir sürümüyle oluşturulmuş bir karma mod derleme üzerinde bağımlılık vardır. Bu senaryolarda, öznitelik ayarlanmış `true`.

> [!NOTE]
> Özniteliğini `true` CLR sürüm 1.1 veya CLR Version 2.0 sürümü ile aynı işleme, etkili bir şekilde işlem içi yan yana özelliğini devre dışı bırakma yüklenmesini engeller (bkz [COM birlikte çalışma için yan yana yürütme](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).

## <a name="example"></a>Örnek

 Aşağıdaki örnek, bir yapılandırma dosyasında çalışma zamanı sürümü belirtmek gösterilmektedir.

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Başlangıç Ayarları Şeması](index.md)
- [Yapılandırma Dosyası Şeması](../index.md)
- [Nasıl yapılır: Bir uygulamayı .NET Framework 4 veya sonraki sürümler destekleyecek şekilde yapılandırma](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [COM birlikte çalışma için yan yana yürütme](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [İşlem İçi Yan Yana Yürütme](../../../deployment/in-process-side-by-side-execution.md)
