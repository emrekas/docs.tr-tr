---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 1143717882652fc8a03947327b5f1ea89dde7373
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793815"
---
# <a name="servicetokenresolver"></a>\<serviceTokenResolver >
Belirteci işleyicisi koleksiyondaki işleyiciler tarafından kullanılan hizmet belirteci çözümleyiciyi kaydeder. Hizmet belirteç Çözümleyici, gelen belirteçleri ve ileti şifreleme belirteci çözmek için kullanılır.  
  
 \<system.identityModel>  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<serviceTokenResolver >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|türü|Belirteç çözümleyici hizmet türünü belirtir. Her iki <xref:System.IdentityModel.Selectors.SecurityTokenResolver> türü veya, türetilen tür <xref:System.IdentityModel.Selectors.SecurityTokenResolver> sınıfı. Belirtme hakkında daha fazla bilgi için `type` [özel tür başvurularını] özniteliği için bkz. Gerekli.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 None  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Güvenlik topluluğu için yapılandırma, belirteç işleyicileri sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hizmet belirteç Çözümleyici, gelen belirteçleri ve ileti şifreleme belirteci gidermek için kullanılabilir. Gelen belirteçlerin şifresini çözmek için kullanılması gereken anahtarı almak için kullanılır. Belirtmelisiniz `type` özniteliği. Belirtilen türü olabilir <xref:System.IdentityModel.Selectors.SecurityTokenResolver> ya öğesinden türetilen özel bir tür <xref:System.IdentityModel.Selectors.SecurityTokenResolver> sınıfı.  
  
 Bazı belirteç işleyicileri yapılandırmada hizmet belirteç çözümleyici ayarları belirtmenize olanak sağlar. Ayarları tek tek belirteç işleyicileri güvenlik belirteci işleyicisi koleksiyonda belirtilen geçersiz kılar.  
  
> [!NOTE]
>  Belirtme `<serviceTokenResolver>` öğesi alt öğesi olarak [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) öğesi kullanım dışı bırakıldı, ancak yine de geriye dönük uyumluluk için desteklenir. Ayarları `<securityTokenHandlerConfiguration>` öğesini geçersiz kılar üzerinde `<identityConfiguration>` öğesi.  
  
## <a name="example"></a>Örnek  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
