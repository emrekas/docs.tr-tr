---
title: <system.serviceModel.activation>
ms.date: 03/30/2017
ms.assetid: c0cae85f-56cb-4030-8807-6f96edff8d2d
ms.openlocfilehash: b29f7173b4d75ec9adff37449d3d56266f01a03c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771965"
---
# <a name="systemservicemodelactivation"></a><span data-ttu-id="6c1d9-102">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="6c1d9-102">\<system.serviceModel.activation></span></span>
<span data-ttu-id="6c1d9-103">Bu yapılandırma bölümü SMSvcHost.exe aracı için yapılandırma ayarlarını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="6c1d9-103">This configuration section represents the configuration settings for the SMSvcHost.exe tool.</span></span> <span data-ttu-id="6c1d9-104">Yapılandırma öğeleri erişimi dosyasında yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c1d9-104">The configuration elements can be configured in the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="6c1d9-105">Özellikle yapılandırılması gereken tüm makine genelindeki ayarları içerir.</span><span class="sxs-lookup"><span data-stu-id="6c1d9-105">Specifically, it includes all machine-wide settings that must be configured.</span></span>  
  
## <a name="sample-configuration-file"></a><span data-ttu-id="6c1d9-106">Örnek yapılandırma dosyası</span><span class="sxs-lookup"><span data-stu-id="6c1d9-106">Sample Configuration File</span></span>  
 <span data-ttu-id="6c1d9-107">SMSvcHost.exe dinleyici işlemi tarafından kullanılan bir örnek yapılandırma dosyası (erişimi) verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="6c1d9-107">The following is a sample configuration file (SMSvcHost.exe.config), which is used by the listener process SMSvcHost.exe.</span></span>  
  
```xml  
<configuration>
  <runtime>
    <gcConcurrent enabled="false" />
  </runtime>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="10"
             maxPendingAccepts="2"
             maxPendingConnections="100"
             receiveTimeout="00:00:10"
             teredoEnabled="false">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
    <net.pipe maxConnectionsPendingDispatch="100"
              maxPendingAccepts="2"
              receiveTimeout="00:00:10">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
    <diagnostics performanceCountersEnabled="true" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="6c1d9-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6c1d9-108">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration>
