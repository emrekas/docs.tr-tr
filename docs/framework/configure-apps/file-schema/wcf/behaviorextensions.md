---
title: <behaviorExtensions>
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: 81ce9bb0e55fe4570f8a21187d9df80ea22393fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191425"
---
# <a name="behaviorextensions"></a>\<behaviorExtensions >
Davranış uzantıları, kullanıcı tanımlı davranış öğelerini oluşturmak kullanıcının etkinleştirir. Bu öğeleri, standart Windows Communication Foundation (WCF) davranışı öğeleri ile birlikte kullanılabilir. `behaviorExtensions` Bölümü öğe yapılandırmasında kullanılabilir olacağı şekilde tanımlar. Normal davranış uzantısı örneği aşağıda verilmiştir.  
  
```xml  
<system.serviceModel>
  <extensions>
    <behaviorExtensions>
      <add name="myBehavior"
           type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </behaviorExtensions>
  </extensions>
</system.serviceModel>
```  
  
 Yapılandırma yeteneklerini öğesine eklemek için yazma ve yapılandırma öğesi kaydetmeniz gerekir. Bunun hakkında daha fazla bilgi için bkz. <xref:System.Configuration> belgeleri.  
  
 Öğesi ve kendi yapılandırma türü tanımlandıktan sonra uzantısı, aşağıdaki örnekte gösterildiği gibi kullanılabilir.  
  
```xml  
<behaviors>
  <behavior configurationName="testChannelBehavior">
    <myBehavior />
    <channelSecurity cacheCookies="false"
                     detectReplays="false"
                     maxCachedNonces="9"
                     maxClockSkew="00:00:03"
                     maxCookieCachingTime="00:07:24"
                     replayWindow="00:07:22.2190000" />
  </behavior>
</behaviors>
```  
  
## <a name="security"></a>Güvenlik  
 Türlerinde kaydederken tam olarak nitelenmiş derleme adları kullanmanız önemle tavsiye edilir `machine.config` ve `app.config` dosyaları. Türü benzersiz olarak tanımlı değilse, CLR türü Yükleyicisi için belirtilen sırayla aşağıdaki konumlarda arar:  
  
 Derleme türü bilinen yükleyici yapılandırma bilgilerini ve uygulama temel dizinini kullanarak geçerli derleme yapılandırma dosyanın yeniden yönlendirme konumları, GAC arar. Derleme bilinmiyorsa, geçerli derleme, mscorlib ve tarafından döndürülen konum yükleyici arar `TypeResolve` olay işleyicisi. Bu CLR arama sırası gibi tür iletme mekanizması ve AppDomain.TypeResolve olay kancaları ile değiştirilebilir.  
  
 Bir saldırgan, CLR arama sırası yararlanma ve yetkisiz bir kod yürütün. (Güçlü) tam olarak nitelenmiş adlar benzersiz olarak kullanarak, bir tür tanımlar ve sisteminizin güvenliği daha da artırır.  
  
 Daha fazla bilgi için [çalışma zamanı derlemeleri nasıl konumlandırır](https://go.microsoft.com/fwlink/?LinkId=95336) ve <xref:System.AppDomain.TypeResolve>.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>
- [Çalışma Zamanını Davranışlarla Yapılandırma ve Genişletme](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
