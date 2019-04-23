---
title: Keşif Yönlendirme Hizmeti
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 166f6b9d1055e36f987e6b9a81fe69dc8bd548b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59980570"
---
# <a name="discovery-router-service"></a>Keşif Yönlendirme Hizmeti
Bu örnek, başka bir uç nokta bulma iletileri iletecek şekilde gösterilmektedir.  
  
## <a name="demonstrates"></a>Gösteriler  
 Bulma yönlendirme  
  
## <a name="discussion"></a>Tartışma  
 Bulma yönlendirme, Ara sunucu kullanarak bir hizmet için bir istemci arıyor ve proxy böyle bir hizmet fark etmez, ancak başka bir proxy bildiği bir senaryoda kullanışlıdır. Bu proxy, ikinci Ara sunucuya Bu istemciden bulma paket iletebilir. İkinci proxy, hizmet için konum ve özgün istemciye bir yanıt döndürür.  
  
 Bu örnekte, bir istemci bir bulma yönlendirme bileşenin bir ileti gönderir. Bu ileti, bulma yönlendiricisinde belirli bir uç noktasına gönderilir. Yönlendirici, iletiyi daha sonra bir UDP olarak iletir. çok noktaya yayın bitiş noktası. Araştırma iletisi ve çok noktaya yayın bitiş noktası ve bir UDP çok noktaya yayın üzerinde dinleyen bir hizmeti, bulma yönlendiriciye adresi yanıt gider. Bulma yönlendirici yanıtları toplar ve bunları istemciye geri gönderir.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Ayarlamak için derleme ve örneği çalıştırma  
  
1. Örneği derleyin.  
  
2. DiscoveryRouter yürütülebilir dosyayı çalıştırın.  
  
3. Yürütülebilir hizmet oluşturma dizinden çalıştırın.  
  
4. İstemci yürütülebilir çalıştırın. İstemci hizmeti bulduktan unutmayın.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü. Devam etmeden önce şu (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek, şu dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
