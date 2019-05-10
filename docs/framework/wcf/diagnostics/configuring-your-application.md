---
title: Uygulamanızı Yapılandırma
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 9a1365bb567c552fb087e67a10e48fe0bc2da873
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64652028"
---
# <a name="configuring-your-application"></a>Uygulamanızı Yapılandırma
Windows Communication Foundation (WCF), .NET yapılandırma sistemini kullanır ve Hizmetleri her iki makine ve uygulama kapsamda yapılandırmanıza olanak tanır.  
  
 WCF tarafından tanımlanan yapılandırma ayarları bulunur `<system.serviceModel>` bölüm grubu. Bir WCF hizmetini yapılandırma hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
- [Hizmetleri Yapılandırma](../../../../docs/framework/wcf/configuring-services.md)  
  
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Uygulama tanımlı yapılandırma ayarları içinde tanımlanmıştır `<appSettings>` bölüm grubu. Uygulama ayarlarında, .NET yapılandırma dosyaları hakkında daha fazla bilgi için bkz. [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Yapılandırma Düzenleyicisi'ni kullanarak  
 WCF [Yapılandırma Aracı (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) Yöneticiler ve geliştiriciler oluşturmak ve bir grafik kullanıcı arabirimi kullanarak WCF hizmetleri için yapılandırma ayarlarını değiştirmek izin verir. Bu araç ile XML yapılandırma dosyalarını doğrudan düzenleyerek olmadan WCF bağlamaları, davranışları, hizmetleri ve tanılama ayarlarını yönetebilirsiniz.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Visual Studio'da yapılandırma dosyalarını düzenleme  
 Visual Studio'da bir WCF Hizmeti projesinin yapılandırma dosyasını düzenlemek için sağ tıklayın, **Çözüm Gezgini** ve **WCF yapılandırmasını Düzenle** bağlam menüsü öğesi. Böylece [Yapılandırma Aracı (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Sağ tıklayarak Visual Studio'da WCF Web hizmeti projesi yapılandırma dosyasını düzenliyorsanız, **Çözüm Gezgini**, dikkat **WCF yapılandırmasını Düzenle** bağlam menüsü öğesi eksik. Geçici çözüm bu sorunu tıklayın **Araçları** menüsünde ve **WCF Hizmeti Yapılandırma Düzenleyicisi**. Bundan sonra bir yapılandırma dosyasına sağ tıklayın ve kullanmak **WCF yapılandırmasını Düzenle** bağlam menüsü öğesi.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Yapılandırma Düzenleme Aracı (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Hizmetleri Yapılandırma](../../../../docs/framework/wcf/configuring-services.md)
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
