---
title: <applicationPool> Öğesi (Web Ayarları)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 786f667bcba7959ac485b4abe667239b05059c45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941453"
---
# <a name="applicationpool-element-web-settings"></a>\<applicationPool > öğesi (Web ayarları)
Bir ASP.NET uygulaması IIS 7,0 veya sonraki bir sürümde tümleşik modda çalışırken, işlem genelinde davranışı yönetmek için ASP.NET tarafından kullanılan yapılandırma ayarlarını belirtir.  
  
> [!IMPORTANT]
> Bu öğe ve özellik yalnızca ASP.NET uygulamanız IIS 7,0 veya sonraki sürümlerde barındırılıyorsa çalışmayı destekler.  
  
 \<Yapılandırma >  
\<System. Web > öğesi (Web ayarları)  
\<applicationPool > öğesi (Web ayarları)  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|CPU başına kaç tane eş zamanlı istek ASP.NET izin verdiğini belirtir.|  
|`maxConcurrentThreadsPerCPU`|Her CPU için bir uygulama havuzu için kaç tane eş zamanlı iş parçacığının çalıştığını belirtir. Bu, isteklere hizmeti sağlamak için CPU başına kullanılabilecek yönetilen iş parçacıklarının sayısını sınırlayabilmeniz için ASP.NET eşzamanlılık denetiminin alternatif bir yolunu sağlar. Varsayılan olarak, bu ayar 0 ' dır, yani CLR iş parçacığı havuzu oluşturulabilen iş parçacığı sayısını da sınırladığından, bu ayar, ASP.NET CPU başına oluşturulabilen iş parçacığı sayısını sınırlamaz.|  
|`requestQueueLimit`|Tek bir işlemde ASP.NET için sıraya alınabilen en fazla istek sayısını belirtir. İki veya daha fazla ASP.NET uygulaması tek bir uygulama havuzunda çalıştığında, uygulama havuzundaki herhangi bir uygulamaya yapılan toplam istek kümesi bu ayara tabidir.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<System. Web >](system-web-element-web-settings.md)|ASP.NET 'in bir konak uygulamasıyla nasıl etkileşime girdiği hakkında bilgi içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 IIS 7,0 veya sonraki bir sürümü tümleşik modda çalıştırdığınızda, bu öğe birleşimi, uygulamanın bir IIS uygulama havuzunda barındırıldığı zaman iş parçacıklarını ve sıra isteklerini nasıl yönettiğini ASP.NET yapılandırmanıza olanak tanır. IIS 6 veya IIS 7,0 'yi Klasik modda veya ISAPI modunda çalıştırırsanız, bu ayarlar yok sayılır.  
  
 `applicationPool` Ayarlar .NET Framework belirli bir sürümünde çalışan tüm uygulama havuzları için geçerlidir. Ayarlar, ASPNET. config dosyasında bulunur. .NET Framework 2,0 ve 4,0 sürümleri için bu dosyanın bir sürümü vardır. (.NET Framework sürümleri ve 3,5 3,0 sürümleri, ASPNET. config dosyasını sürüm 2,0 ile paylaşır.)  
  
> [!IMPORTANT]
> Üzerinde [!INCLUDE[win7](../../../../../includes/win7-md.md)]IIS 7,0 çalıştırırsanız, her uygulama havuzu için ayrı bir Aspnet. config dosyası yapılandırabilirsiniz. Bu, her uygulama havuzu için iş parçacıklarının performansını uyarlamanızı sağlar.  
  
 `maxConcurrentRequestsPerCPU` Bu ayar için, "5000 .NET Framework" varsayılan ayarı, ASP.NET tarafından denetlenen istek azaltmasını etkin bir şekilde devre dışı bırakır, ancak CPU başına 5000 veya daha fazla istek olmadığı müddetçe. Varsayılan ayar, CLR iş parçacığı havuzuna CPU başına otomatik olarak yönetilecek şekilde değişir. Zaman uyumsuz istek işlemenin çok fazla kullanımını veya ağ g/ç 'de engellenen çok uzun süreli istekleri olan uygulamalar, .NET Framework 4 ' te artan varsayılan sınırdan faydalanır. Sıfıra `maxConcurrentRequestsPerCPU` ayarlandığında, ASP.net isteklerini işlemek için yönetilen iş parçacıklarının kullanımını devre dışı bırakır. Bir uygulama bir IIS uygulama havuzunda çalıştığında, istekler IIS g/ç iş parçacığında kalır ve bu nedenle eşzamanlılık IIS iş parçacığı ayarları tarafından kısıtlanır.  
  
 Ayar, ASP.NET uygulamaları için Web. config `requestQueueLimit` dosyalarında ayarlanan processModel öğesinin özniteliğiyle aynı şekilde çalışıyor. [](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) `requestQueueLimit` Ancak, `requestQueueLimit` Aspnet. config dosyasındaki ayarı bir Web. config dosyasındaki `requestQueueLimit` ayarı geçersiz kılar. Diğer bir deyişle, her iki öznitelik de ayarlanırsa (varsayılan olarak, bu true ise), `requestQueueLimit` Aspnet. config dosyasındaki ayarı önceliklidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, aşağıdaki durumlarda Aspnet. config dosyasında ASP.NET işlem genelindeki davranışın nasıl yapılandırılacağı gösterilmektedir:  
  
- Uygulama bir IIS 7,0 uygulama havuzunda barındırılır.  
  
- IIS 7,0, tümleşik modda çalışıyor.  
  
- Uygulama .NET Framework 3,5 SP1 veya sonraki bir sürümünü kullanıyor.  
  
 Örnekteki değerler varsayılan değerlerdir.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|||  
|-|-|  
|Ad Alanı||  
|Şema adı||  
|Doğrulama dosyası||  
|Boş olabilir||  
  
## <a name="see-also"></a>Ayrıca bkz.

- [\<System. Web > öğesi (Web ayarları)](system-web-element-web-settings.md)
