---
title: UriTemplate Tablosu Dağıtıcı Örneği
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: ff697a205ce47960275b51153d415af717f81222
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156019"
---
# <a name="uritemplate-table-dispatcher-sample"></a>UriTemplate Tablosu Dağıtıcı Örneği
<xref:System.UriTemplateTable> Sınıfı bir dizi birlikte çalışmak için bir sözlük benzeri ilişkilendirilebilir tablo yapısı sağlar <xref:System.UriTemplate> örnekleri. Bu örnek, bir temel dispatching altyapısı kullanılarak oluşturulan gösterir `UriTemplateTable`, genel bir kullanım senaryosu `UriTemplateTable` sınıfı.  
  
 Bu örnek aşağıdaki kavramlar gösterir `UriTemplateTable` sınıfı:  
  
-   Temsilcileri ile ilişkilendirme `UriTemplates` içinde bir `UriTemplateTable`.  
  
-   Kullanarak <xref:System.UriTemplateTable.MatchSingle%2A> belirli bir URI için doğru işleyici temsilcisini almak için.  
  
-   İsteği işlemek için işleyici temsilcisini çağrılıyor.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Ayarlamak için derleme ve örneği çalıştırma  
  
1.  Çözüm C# veya Visual Basic .NET sürümünü oluşturmak için yönergeleri izleyin. [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Tek veya çapraz makine yapılandırmasında örneği çalıştırmak için yönergeleri izleyin. [Windows Communication Foundation örneklerini çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü. Devam etmeden önce şu (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek, şu dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a>Ayrıca bkz.

- [UriTemplate Tablosu](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
