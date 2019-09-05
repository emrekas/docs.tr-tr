---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: a54f5ce86aee1a5e831c0b10aa1471d4a82f40a5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251799"
---
# <a name="systemidentitymodel"></a>\<system.identityModel>
Uygulamalarda Windows Identity Foundation (WıF) seçeneklerini etkinleştirmek için yapılandırma sağlar.  
  
[ **\<Yapılandırma >** ](../configuration-element.md)\
&nbsp;&nbsp; **\<System. IdentityModel >**  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<IdentityConfiguration >](identityconfiguration.md)|Hizmet düzeyi kimlik ayarlarını belirtir.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`<configuration>`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|  
  
## <a name="remarks"></a>Açıklamalar  
 Windows Identity `<system.identityModel>` Foundation (WIF) kullanmak üzere bir hizmet veya uygulamayı yapılandırmak için yapılandırma dosyasına bir bölüm ekleyin. `<system.identityModel>` Öğesi sınıfı<xref:System.IdentityModel.Configuration.SystemIdentityModelSection> tarafından temsil edilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir yapılandırma dosyasına bir `<system.identityModel>` bölümün nasıl ekleneceğini gösterir. Önce yapılandırma bölümünü ve ad alanı bildirimini `<configSections>` öğesi altına eklemeniz gerekir. Daha sonra bir veya daha `<system.IdentityModel>` fazla kimlik yapılandırması belirtmek için öğesini yapılandırma dosyanıza ekleyebilirsiniz.  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
