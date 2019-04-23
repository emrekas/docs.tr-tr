---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: 12ac8d9a7b0ed584fb1308e56d197a03b1c53e51
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59769352"
---
# <a name="endpointextensions"></a><span data-ttu-id="4e7b7-101">\<endpointExtensions ></span><span class="sxs-lookup"><span data-stu-id="4e7b7-101">\<endpointExtensions></span></span>
<span data-ttu-id="4e7b7-102">Bu bölümde, bir makine uzantıları bölümünde yeni bir standart uç nokta kaydeder veya uygulama yapılandırma dosyası.</span><span class="sxs-lookup"><span data-stu-id="4e7b7-102">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="4e7b7-103">Kullanarak, bu koleksiyona bir standart uç nokta ekleyebilirsiniz `add` anahtar sözcüğü ve ayarı `type` uç nokta türü için bir öğenin özniteliği hem de `name` öznitelik standart bitiş noktası adını.</span><span class="sxs-lookup"><span data-stu-id="4e7b7-103">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="4e7b7-104">Aşağıdaki örnekte `add` öğesi hem de `name` özniteliği için bir standart uç nokta eklemek için `<endpointExtensions>` yapılandırma dosyasının.</span><span class="sxs-lookup"><span data-stu-id="4e7b7-104">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <endpointExtensions>
      <add name="udpDiscoveryEndpoint"
           type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="4e7b7-105">Standart uç nokta kaydedildikten sonra aşağıdaki örnekte gösterildiği gibi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4e7b7-105">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="4e7b7-106">İçinde [ \<uç noktası >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) öğesi `kind` özniteliği belirtir, kayıtlı standart uç nokta türü `<endpointExtensions>` bölümü.</span><span class="sxs-lookup"><span data-stu-id="4e7b7-106">In the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="4e7b7-107">`endpointConfiguration` Özniteliği aynı olacaktır `name` standart uç nokta yapılandırma öğesinin özniteliği `<standardEndpoints>` bölümü.</span><span class="sxs-lookup"><span data-stu-id="4e7b7-107">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Service1">
      <endpoint kind="udpDiscoveryEndpoint"
                endpointConfiguration="udpConfig" />
    </service>
  </services>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
