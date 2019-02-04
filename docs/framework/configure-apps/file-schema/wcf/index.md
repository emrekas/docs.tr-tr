---
title: WCF Yapılandırma Şeması
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: ae9e660ee5c4163487e953077df8782955f90ef5
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675367"
---
# <a name="wcf-configuration-schema"></a>WCF Yapılandırma Şeması
Windows Communication Foundation (WCF) yapılandırma öğeleri WCF hizmet ve istemci uygulamaları yapılandırmanıza olanak sağlar. Kullanabileceğiniz [Yapılandırma Aracı (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) oluşturup istemciler ve hizmetler için yapılandırma dosyalarını değiştirin. Yapılandırma dosyaları XML olarak biçimlendirilir olduğundan, bir metin düzenleyicisi kullanarak bunları el ile düzenlemek istiyorsanız, XML'e alışık olmanız gerekir. Aksi takdirde içine sorunları unfound XML öğesi etiketi veya öznitelik gibi çalışabilir. Bunun nedeni, XML öğesi etiketleri ve öznitelikleri duyarlıdır.  
  
 WCF yapılandırma sistemi dayanır <xref:System.Configuration> ad alanı. Bu nedenle, tarafından sağlanan tüm standart özellikler kullanabilirsiniz <xref:System.Configuration> kilitleme, şifreleme ve uygulamanız ve yapılandırmasına güvenliğini artırmak için birleştirme yapılandırması gibi bir ad alanı. Bu kavramlarla ilgili daha fazla bilgi için aşağıdaki konulara bakın.  
  
 [Şifreleme yapılandırma bilgileri](https://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [Kilitleme yapılandırma ayarları](https://go.microsoft.com/fwlink/?LinkId=95338)  
  
 Bu bölümde, her bir yapılandırma öğesinin tüm olası değerlerini ve diğer WCF yapılandırma öğeleri ile nasıl etkileşim kurduğunu açıklar. Aşağıdaki harita WCF yapılandırma şeması gösterilmektedir.  
  
 ![WCF yapılandırma şeması](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")  
  
> [!CAUTION]
>  WCF yapılandırma bölümlerini, uygulama yapılandırma dosyalarında (app.config) ile uygun erişim denetim listeleri (tüm olası güvenlik tehditlerini önlemek için ACL) korur.  Örneğin, yalnızca uygun kişilerle erişme veya uygulama bağlamaları veya hizmet modeli bölümü yapılandırma dosyasının bir hizmet için güvenlik ayarlarını değiştirme emin olmanız gerekir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 Açıklayan `ServiceModel` öğesi.  
  
 [\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 SMSvcHost.exe aracı yapılandırır.  
  
 [\<System.Runtime.Serialization >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 Seri hale getiricileri genişletme gibi kullanırken seçenekleri ayarlamak için üst düzey öğe <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Windows Communication Foundation uygulamaları için yapılandırma](../../../wcf/configuring-services.md)  
 WCF hizmetleri ve istemcilerin nasıl yapılandırılacağını açıklar.
