---
title: "Windows Communication Foundation'ı Benimsemeyi Bekleme: Gelecekteki Tümleştirmeyi Kolaylaştırma"
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: c6e749c32947a4159d6bfd56c4d30a06f6ef0b7f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316342"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Windows Communication Foundation'ı Benimsemeyi Bekleme: Gelecekteki Tümleştirmeyi Kolaylaştırma
ASP.NET kullanmaya hemen başlayın ve gelecekte WCF kullanarak tahmin, bu konu, yeni ASP.NET Web hizmetlerini de WCF uygulamaları ile birlikte çalışacağından emin olmak için kılavuzluk sağlar.  
  
## <a name="general-recommendations"></a>Genel öneriler  
 ASP.NET 2.0 için yeni hizmetler benimseyin. Bunun yapılması, iyileştirmeler ve geliştirmeler yeni sürümü için erişim sağlar. Ancak, bu da aynı uygulamada ASP.NET 2.0 bileşenleri WCF bileşenleri ile birlikte kullanma olasılığını için izin verir.  
  
## <a name="protocols"></a>Protokolleri  
 Yeni ASP.NET 2.0'ın tesis ws uygunluk doğrulamak için kullanın-ı Basic Profile 1.1:  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 ASP.NET Web Hizmetleri, uygun WS-ı Basic Profile 1.1 bağlama, önceden tanımlanmış WCF kullanarak WCF istemcileri ile birlikte çalışabilen olacağını <xref:System.ServiceModel.BasicHttpBinding>.  
  
## <a name="service-development"></a>Hizmet geliştirme  
 Kullanmaktan kaçının <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> yöntemlere yönlendirilmiş iletiler için öznitelik SOAPAction HTTP üst bilgisi yerine SOAP iletisi body öğesi tam olarak nitelenmiş adını temel alarak. SOAPAction HTTP üst bilgisi, WCF iletileri yönlendirmek için kullanır.  
  
## <a name="data-representation"></a>Veri gösterimi  
 XML'e <xref:System.Xml.Serialization.XmlSerializer> serileştiren bir türü varsayılan olarak anlamı da XML'e aynıdır <xref:System.Runtime.Serialization.DataContractSerializer> ad alanı XML açıkça tanımlanmış için sağlanan bir türü seri hale getirir. ASP.NET Web Hizmetleri ile kullanmak için bir veri türü olasılığına benimsemenin WCF içinde gelecekte tanımlarken aşağıdakileri yapın:  
  
1. XML şeması yerine .NET Framework sınıfları kullanarak türünü tanımlayın.  
  
2. Yalnızca ekleme <xref:System.SerializableAttribute> ve <xref:System.Xml.Serialization.XmlRootAttribute> sınıf türünün ad alanını açıkça tanımlamak için ikinci kullanarak. Yapmak hiçbir ek özniteliklerinden Ekle <xref:System.Xml.Serialization> nasıl XML'e çevrilmesi için .NET Framework sınıf olduğunu denetlemek için ad alanı.  
  
 Bu yaklaşım benimseyerek, daha sonra ek olarak veri sözleşmeleri içine .NET sınıfları oluşturmak erişebileceğinizi <xref:System.Runtime.Serialization.DataContractAttribute> ve <xref:System.Runtime.Serialization.DataMemberAttribute> içine sınıfları aktarım için serileştirilir XML önemli ölçüde boyutlandırabiliriz. İletileri ASP.NET Web Hizmetleri tarafından kullanılan türleri arasında diğer avantajları, WCF uygulamalarında daha iyi performans sağlayan veri sözleşmesi WCF uygulamaları tarafından işlenmek üzere mümkün olacaktır.  
  
## <a name="security"></a>Güvenlik  
 Internet Information Services (IIS) tarafından sağlanan kimlik doğrulama seçenekleri kullanmaktan kaçının. WCF istemcileri onları desteklemez. Bir hizmet korunması gerekir, çünkü bu seçeneklerin daha zengin ve standardı protokollerine dayalıdır WCF tarafından sağlanan seçenekleri kullanın.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Windows Communication Foundation'ı Benimsemeyi Bekleme: Gelecekteki Geçişi Kolaylaştırma](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
