---
title: "Windows Communication Foundation'ı Benimsemeyi Bekleme: Gelecekteki Tümleştirmeyi Kolaylaştırma"
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: 2f733f9cc33846913539fee4afdd95efa9224058
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124806"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a><span data-ttu-id="3bafa-102">Windows Communication Foundation'ı Benimsemeyi Bekleme: Gelecekteki Tümleştirmeyi Kolaylaştırma</span><span class="sxs-lookup"><span data-stu-id="3bafa-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>
<span data-ttu-id="3bafa-103">ASP.NET kullanmaya hemen başlayın ve gelecekte WCF kullanarak tahmin, bu konu, yeni ASP.NET Web hizmetlerini de WCF uygulamaları ile birlikte çalışacağından emin olmak için kılavuzluk sağlar.</span><span class="sxs-lookup"><span data-stu-id="3bafa-103">If you use ASP.NET today, and anticipate using WCF in the future, this topic provides guidance to ensure that new ASP.NET Web services will work well together with WCF applications.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="3bafa-104">Genel öneriler</span><span class="sxs-lookup"><span data-stu-id="3bafa-104">General Recommendations</span></span>  
 <span data-ttu-id="3bafa-105">ASP.NET 2.0 için yeni hizmetler benimseyin.</span><span class="sxs-lookup"><span data-stu-id="3bafa-105">Adopt ASP.NET 2.0 for any new services.</span></span> <span data-ttu-id="3bafa-106">Bunun yapılması, iyileştirmeler ve geliştirmeler yeni sürümü için erişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="3bafa-106">Doing so will provide access to the improvements and enhancements of the new version.</span></span> <span data-ttu-id="3bafa-107">Ancak, bu da aynı uygulamada ASP.NET 2.0 bileşenleri WCF bileşenleri ile birlikte kullanma olasılığını için izin verir.</span><span class="sxs-lookup"><span data-stu-id="3bafa-107">However, it will also allow for the possibility of using ASP.NET 2.0 components together with WCF components in the same application.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="3bafa-108">Protokolleri</span><span class="sxs-lookup"><span data-stu-id="3bafa-108">Protocols</span></span>  
 <span data-ttu-id="3bafa-109">Yeni ASP.NET 2.0'ın tesis ws uygunluk doğrulamak için kullanın-ı Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="3bafa-109">Use ASP.NET 2.0’s new facility for validating conformity to the WS-I Basic Profile 1.1:</span></span>  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="3bafa-110">ASP.NET Web Hizmetleri, uygun WS-ı Basic Profile 1.1 bağlama, önceden tanımlanmış WCF kullanarak WCF istemcileri ile birlikte çalışabilen olacağını <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="3bafa-110">ASP.NET Web services that conform to WS-I Basic Profile 1.1 will be interoperable with WCF clients by using WCF predefined binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="3bafa-111">Hizmet geliştirme</span><span class="sxs-lookup"><span data-stu-id="3bafa-111">Service Development</span></span>  
 <span data-ttu-id="3bafa-112">Kullanmaktan kaçının <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> yöntemlere yönlendirilmiş iletiler için öznitelik SOAPAction HTTP üst bilgisi yerine SOAP iletisi body öğesi tam olarak nitelenmiş adını temel alarak.</span><span class="sxs-lookup"><span data-stu-id="3bafa-112">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the SOAPAction HTTP header.</span></span> <span data-ttu-id="3bafa-113">SOAPAction HTTP üst bilgisi, WCF iletileri yönlendirmek için kullanır.</span><span class="sxs-lookup"><span data-stu-id="3bafa-113">WCF uses the SOAPAction HTTP header for routing messages.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="3bafa-114">Veri gösterimi</span><span class="sxs-lookup"><span data-stu-id="3bafa-114">Data Representation</span></span>  
 <span data-ttu-id="3bafa-115">XML'e <xref:System.Xml.Serialization.XmlSerializer> serileştiren bir türü varsayılan olarak anlamı da XML'e aynıdır <xref:System.Runtime.Serialization.DataContractSerializer> ad alanı XML açıkça tanımlanmış için sağlanan bir türü seri hale getirir.</span><span class="sxs-lookup"><span data-stu-id="3bafa-115">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="3bafa-116">ASP.NET Web Hizmetleri ile kullanmak için bir veri türü olasılığına benimsemenin WCF içinde gelecekte tanımlarken aşağıdakileri yapın:</span><span class="sxs-lookup"><span data-stu-id="3bafa-116">When defining a data type for use with ASP.NET Web services in anticipation of adopting WCF in the future, do the following:</span></span>  
  
1.  <span data-ttu-id="3bafa-117">XML şeması yerine .NET Framework sınıfları kullanarak türünü tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="3bafa-117">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
2.  <span data-ttu-id="3bafa-118">Yalnızca ekleme <xref:System.SerializableAttribute> ve <xref:System.Xml.Serialization.XmlRootAttribute> sınıf türünün ad alanını açıkça tanımlamak için ikinci kullanarak.</span><span class="sxs-lookup"><span data-stu-id="3bafa-118">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="3bafa-119">Yapmak hiçbir ek özniteliklerinden Ekle <xref:System.Xml.Serialization> nasıl XML'e çevrilmesi için .NET Framework sınıf olduğunu denetlemek için ad alanı.</span><span class="sxs-lookup"><span data-stu-id="3bafa-119">Do no add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
 <span data-ttu-id="3bafa-120">Bu yaklaşım benimseyerek, daha sonra ek olarak veri sözleşmeleri içine .NET sınıfları oluşturmak erişebileceğinizi <xref:System.Runtime.Serialization.DataContractAttribute> ve <xref:System.Runtime.Serialization.DataMemberAttribute> içine sınıfları aktarım için serileştirilir XML önemli ölçüde boyutlandırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="3bafa-120">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="3bafa-121">İletileri ASP.NET Web Hizmetleri tarafından kullanılan türleri arasında diğer avantajları, WCF uygulamalarında daha iyi performans sağlayan veri sözleşmesi WCF uygulamaları tarafından işlenmek üzere mümkün olacaktır.</span><span class="sxs-lookup"><span data-stu-id="3bafa-121">The types used in messages by ASP.NET Web services will be able to be processed as data contracts by WCF applications, yielding, amongst other benefits, better performance in WCF applications.</span></span>  
  
## <a name="security"></a><span data-ttu-id="3bafa-122">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="3bafa-122">Security</span></span>  
 <span data-ttu-id="3bafa-123">Internet Information Services (IIS) tarafından sağlanan kimlik doğrulama seçenekleri kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="3bafa-123">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="3bafa-124">WCF istemcileri onları desteklemez.</span><span class="sxs-lookup"><span data-stu-id="3bafa-124">WCF clients do not support them.</span></span> <span data-ttu-id="3bafa-125">Bir hizmet korunması gerekir, çünkü bu seçeneklerin daha zengin ve standardı protokollerine dayalıdır WCF tarafından sağlanan seçenekleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="3bafa-125">If a service needs to be secured, use the options provided by WCF, because these options are richer and are based on standard protocols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bafa-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3bafa-126">See also</span></span>

- [<span data-ttu-id="3bafa-127">Windows Communication Foundation'ı Benimsemeyi Bekleme: Gelecekteki Geçişi Kolaylaştırma</span><span class="sxs-lookup"><span data-stu-id="3bafa-127">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
