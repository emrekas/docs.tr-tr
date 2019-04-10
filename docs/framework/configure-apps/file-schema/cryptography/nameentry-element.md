---
title: <nameEntry> Öğe
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: 97521ba9073820beeea62f5fc7cab480b5422fb0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225332"
---
# <a name="nameentry-element"></a>\<nameEntry > öğesi
Çok sayıda kolay adlara sahip bir sınıf sağlar ve kolay algoritma adı için bir sınıf adı eşler.  
  
 \<Yapılandırma >  
\<mscorlib >  
\<cryptographySettings >  
\<cryptoNameMapping >  
\<nameEntry >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**name**|Gerekli öznitelik.<br /><br /> Şifreleme sınıfına uygulayan algoritma kolay adı belirtir.|  
|**sınıf**|Gerekli öznitelik.<br /><br /> Değeri belirtir **adı** özniteliğini [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) öğesi.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`configuration`|Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.|  
|`system.web`|ASP.NET yapılandırma bölümü için olan kök öğesini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 **Adı** özniteliği bulunan soyut sınıflar birinin adı olabilir <xref:System.Security.Cryptography> ad alanı. Çağırdığınızda **Oluştur** bir soyut bir şifreleme sınıfına yönteminde, soyut sınıf adı için geçirilir <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> yöntemi. **CreateFromName** tarafından belirtilen türün bir örneğini döndürür **sınıfı** özniteliği. Varsa **adı** kısa bir ad özniteliği olan RSA gibi bu adı çağırırken kullanabilirsiniz **CreateFromName** yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir  **\<nameEntry >** bir şifreleme sınıfına başvurmak için ve çalışma zamanı yapılandırma öğesi. Ardından "RSA" dize iletebileceğiniz <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> yöntemini <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> döndürülecek yöntemi bir `MyCryptoRSAClass` nesne.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Yapılandırma Dosyası Şeması](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Şifreleme Ayarları Şeması](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [Şifreleme Hizmetleri](../../../../../docs/standard/security/cryptographic-services.md)
- [Şifreleme Sınıflarını Yapılandırma](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
