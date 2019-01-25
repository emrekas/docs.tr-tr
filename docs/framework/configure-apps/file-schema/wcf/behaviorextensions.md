---
title: '&lt;behaviorExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: 6698da198c4e1798af4a63e72e1d7ef9e09a5d92
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599029"
---
# <a name="ltbehaviorextensionsgt"></a><span data-ttu-id="1e4e1-102">&lt;behaviorExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="1e4e1-102">&lt;behaviorExtensions&gt;</span></span>
<span data-ttu-id="1e4e1-103">Davranış uzantıları, kullanıcı tanımlı davranış öğelerini oluşturmak kullanıcının etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-103">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="1e4e1-104">Bu öğeleri, standart Windows Communication Foundation (WCF) davranışı öğeleri ile birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-104">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="1e4e1-105">`behaviorExtensions` Bölümü öğe yapılandırmasında kullanılabilir olacağı şekilde tanımlar.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-105">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="1e4e1-106">Normal davranış uzantısı örneği aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-106">Here is an example of a typical behavior extension.</span></span>  
  
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
  
 <span data-ttu-id="1e4e1-107">Yapılandırma yeteneklerini öğesine eklemek için yazma ve yapılandırma öğesi kaydetmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-107">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="1e4e1-108">Bunun hakkında daha fazla bilgi için bkz. <xref:System.Configuration> belgeleri.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="1e4e1-109">Öğesi ve kendi yapılandırma türü tanımlandıktan sonra uzantısı, aşağıdaki örnekte gösterildiği gibi kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-109">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
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
  
## <a name="security"></a><span data-ttu-id="1e4e1-110">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="1e4e1-110">Security</span></span>  
 <span data-ttu-id="1e4e1-111">Türlerinde kaydederken tam olarak nitelenmiş derleme adları kullanmanız önemle tavsiye edilir `machine.config` ve `app.config` dosyaları.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-111">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="1e4e1-112">Türü benzersiz olarak tanımlı değilse, CLR türü Yükleyicisi için belirtilen sırayla aşağıdaki konumlarda arar:</span><span class="sxs-lookup"><span data-stu-id="1e4e1-112">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="1e4e1-113">Derleme türü bilinen yükleyici yapılandırma bilgilerini ve uygulama temel dizinini kullanarak geçerli derleme yapılandırma dosyanın yeniden yönlendirme konumları, GAC arar.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-113">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="1e4e1-114">Derleme bilinmiyorsa, geçerli derleme, mscorlib ve tarafından döndürülen konum yükleyici arar `TypeResolve` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-114">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="1e4e1-115">Bu CLR arama sırası gibi tür iletme mekanizması ve AppDomain.TypeResolve olay kancaları ile değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-115">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="1e4e1-116">Bir saldırgan, CLR arama sırası yararlanma ve yetkisiz bir kod yürütün.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-116">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="1e4e1-117">(Güçlü) tam olarak nitelenmiş adlar benzersiz olarak kullanarak, bir tür tanımlar ve sisteminizin güvenliği daha da artırır.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-117">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="1e4e1-118">Daha fazla bilgi için [çalışma zamanı derlemeleri nasıl konumlandırır](https://go.microsoft.com/fwlink/?LinkId=95336) ve <xref:System.AppDomain.TypeResolve>.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-118">For more information, see [How the Runtime Locates Assemblies](https://go.microsoft.com/fwlink/?LinkId=95336) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e4e1-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1e4e1-119">See also</span></span>
- <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>
- [<span data-ttu-id="1e4e1-120">Çalışma Zamanını Davranışlarla Yapılandırma ve Genişletme</span><span class="sxs-lookup"><span data-stu-id="1e4e1-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
