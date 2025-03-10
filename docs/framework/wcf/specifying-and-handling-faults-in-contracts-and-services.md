---
title: Sözleşme ve Hizmetlerde Hataları Belirtme ve İşleme
ms.date: 03/30/2017
helpviewer_keywords:
- handling faults [WCF]
ms.assetid: a9696563-d404-4905-942d-1e0834c26dea
ms.openlocfilehash: de12097f018e17b11a2beac663e0b0c51c7a2a17
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038395"
---
# <a name="specifying-and-handling-faults-in-contracts-and-services"></a>Sözleşme ve Hizmetlerde Hataları Belirtme ve İşleme

Windows Communication Foundation (WCF) uygulamaları yönetilen özel durum nesnelerini SOAP hata nesnelerine ve SOAP hata nesnelerine yönetilen özel durum nesnelerine eşleyerek hata durumlarını işler. Bu bölümdeki konularda, hata koşullarını özel SOAP hataları olarak ortaya çıkarmak, hizmet uygulamasının bir parçası olarak bu hataların döndürülmesi ve istemcilerin bu hataları nasıl yakalayabileceği açıklanmaktadır.

## <a name="error-handling-overview"></a>Hata Işleme genel bakış

Tüm yönetilen uygulamalarda, işleme hataları nesneler tarafından <xref:System.Exception> temsil edilir. WCF uygulamaları gibi SOAP tabanlı uygulamalarda, hizmet yöntemleri SOAP hata iletilerini kullanarak hata bilgilerini işlemeye iletişim kurar. SOAP hataları, bir hizmet işleminin meta verilerinde bulunan ileti türleridir ve bu nedenle, istemcilerinin işlemlerini daha sağlam veya etkileşimli hale getirmek için kullanabileceği bir hata sözleşmesi oluşturur. Buna ek olarak, SOAP hataları XML biçiminde istemcilere ifade edildiğinden, herhangi bir SOAP platformunda istemcilerin kullanabileceği, WCF uygulamanızın erişimini artıran, yüksek oranda çalışabilen bir tür sistemidir.

WCF uygulamaları her iki tür de hata sistemi altında çalıştığından, istemciye gönderilen tüm yönetilen özel durum bilgileri hizmette SOAP hatalarına, gönderilen ve SOAP arızalarından WCF istemcilerinde hata özel durumlarına dönüştürülmelidir. Çift yönlü istemciler söz konusu olduğunda, istemci sözleşmeleri bir hizmete SOAP hataları da gönderebilir. Her iki durumda da, varsayılan hizmet özel durum davranışlarını kullanabilir veya özel durumların hata iletileriyle eşlenip eşlenmediğini açıkça kontrol edebilirsiniz.

İki tür SOAP hatası gönderilebilir: *bildirimi yapılmış* ve *bildirilmemiş*. Tanımlanan SOAP hataları, bir işlemin özel bir SOAP hata türünü <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> belirten bir özniteliğe sahip olduğu olanlardır. *Bildirilmemiş* Bir işlem için sözleşmede SOAP hataları belirtilmemiş.

Bir istemcinin normal bir işlem sırasında almayı beklediği tüm soap hatalarını belirtmek <xref:System.ServiceModel.FaultContractAttribute> için özniteliğini kullanarak, hizmet işlemlerinin hatalarını bildirmesi önemle tavsiye edilir. Ayrıca, bir SOAP hatasına geri dönebilmeniz önerilir ve bilgilerin açığa çıkmasını en aza indirmek için bir istemcinin bilmesi gereken bilgiler.

Genellikle, hizmetler (ve çift yönlü istemciler) hata işlemesini uygulamalarla başarıyla bütünleştirmek için aşağıdaki adımları alır:

- Özel SOAP hatalarıyla özel durum koşullarını eşleyin.

- İstemciler ve hizmetler SOAP hatalarını özel durum olarak gönderir ve alır.

Ayrıca, WCF istemcileri ve Hizmetleri hata ayıklama amacıyla bildirilmemiş SOAP hatalarını kullanabilir ve varsayılan hata davranışını genişletebilir. Aşağıdaki bölümlerde bu görevler ve kavramlar ele alınmaktadır.

## <a name="map-exceptions-to-soap-faults"></a>Özel durumları SOAP hatalarıyla eşleme

Hata koşullarını işleyen bir işlem oluşturmanın ilk adımı, bir istemci uygulamasının hatalar hakkında bilgilendirilmesi gereken koşullara göre belirlenir. Bazı işlemlerin işlevlerine özgü hata koşulları vardır. Örneğin, bir `PurchaseOrder` işlem, artık satın alma siparişi başlatmalarına izin verilmeyen müşterilere belirli bilgiler döndürebilir. Bir `Calculator` hizmet gibi diğer durumlarda, bir hizmetin tamamına ilişkin tüm hata `MathFault` koşullarını daha genel bir soap hatası tanımlayabilir. Hizmetinizin istemci hata koşulları tanımlandıktan sonra, özel bir SOAP hatası oluşturulabilir ve işlem, karşılık gelen hata koşulu ortaya çıkarsa bu SOAP hatası döndürülebilinir.

Hizmetinizi veya istemcinizi geliştirmeye yönelik bu adım hakkında daha fazla bilgi için bkz. [hataları tanımlama ve belirtme](../../../docs/framework/wcf/defining-and-specifying-faults.md).

## <a name="clients-and-services-handle-soap-faults-as-exceptions"></a>İstemciler ve hizmetler SOAP hatalarını özel durum olarak Işler

İşlem hata koşullarını tanımlama, özel SOAP hataları tanımlama ve bu işlemleri bu hataları döndürürken işaretlemek, WCF uygulamalarında başarılı hata işlemenin ilk adımlarıdır. Sonraki adım, bu hataların gönderilmesini ve alınmasını doğru bir şekilde uygulamaktır. Genellikle hizmetler, istemci uygulamalarına hata koşulları hakkında bilgi vermek için hatalar gönderir, ancak çift yönlü istemciler ayrıca hizmetlere SOAP hataları gönderebilir.

Daha fazla bilgi için bkz. [hata gönderme ve alma](../../../docs/framework/wcf/sending-and-receiving-faults.md).

## <a name="undeclared-soap-faults-and-debugging"></a>Bildirilmemiş SOAP hataları ve hata ayıklama

Tanımlanan SOAP hataları sağlam, birlikte çalışabilen, dağıtılmış uygulamalar oluşturmak için son derece kullanışlıdır. Ancak bazı durumlarda, bir hizmet (veya çift yönlü istemci), bu işlem için Web Hizmetleri Açıklama Dili (WSDL) içinde belirtilmeyen bir bildirilmemiş SOAP hatası göndermek için yararlıdır. Örneğin, bir hizmet geliştirirken, istemciye bilgi göndermek amacıyla hata ayıklama amacıyla yararlı olduğu beklenmeyen durumlar meydana gelebilir. Ayrıca, WCF istemcilerinin iç hizmet işlemi <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> özel durumları hakkında <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> bilgi almasına `true` izin vermek için özelliğini veya özelliğini olarak ayarlayabilirsiniz. Her ikisi de tek tek hata gönderme ve hata ayıklama davranışı özelliklerini ayarlama, [hataları gönderme ve alma](../../../docs/framework/wcf/sending-and-receiving-faults.md)konularında açıklanmaktadır.

> [!IMPORTANT]
> Yönetilen özel durumlar iç uygulama bilgilerini kullanıma sunabileceğinden, <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> veya <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> için `true` ayarı, WCF istemcilerinin kişisel olarak da dahil olmak üzere iç hizmet işlemi özel durumları hakkında bilgi almasına izin verebilir tanımlanabilir veya diğer hassas bilgiler.
>
> Bu nedenle, <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> veya <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> için `true` ayarı, yalnızca bir hizmet uygulamasında geçici olarak hata ayıklamanın bir yolu olarak önerilir. Ayrıca, işlenmemiş yönetilen özel durumları bu şekilde döndüren bir yöntem için WSDL, türü <xref:System.ServiceModel.FaultException%601> <xref:System.ServiceModel.ExceptionDetail>için anlaşma içermez. İstemciler, hata ayıklama bilgilerini düzgün bir şekilde almak için bilinmeyen bir soap hatası (WCF <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> istemcilerine geri döndürülen) olasılığını beklememelidir.

## <a name="customizing-error-handling-with-ierrorhandler"></a>IErrorHandler ile hata Işlemeyi özelleştirme

Bir uygulama düzeyi özel durum olduğunda veya yanıt iletisi döndürülmeden sonra bazı özel işlemler gerçekleştirirken, yanıt iletisini istemciye özelleştirmek için özel gereksinimleriniz varsa, <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType> arabirimini uygulayın.

## <a name="fault-serialization-issues"></a>Hata serileştirme sorunları

Bir hata sözleşmesinin serisi kaldırılırken, WCF öncelikle SOAP iletisindeki hata sözleşmesi adını hata sözleşmesi türüyle eşleştirmeye çalışır. Tam bir eşleşme bulamazsa, uygun hata sözleşmeleri listesinde, uyumlu bir tür için alfabetik sırada arama yapılır. İki hata sözleşmesi uyumlu türlerdir (biri diğerinin bir alt sınıfıdır, örneğin) hata serileştirilmek için yanlış tür kullanılabilir. Bu yalnızca hata sözleşmesi bir ad, ad alanı ve eylem belirtmediğinde oluşur. Bu sorunun oluşmasını önlemek için, ad, ad alanı ve eylem özniteliklerini belirterek hata sözleşmelerini her zaman tam olarak nitelendirin. Ayrıca, paylaşılan bir taban sınıftan türetilmiş bir dizi ilişkili hata sözleşmesi tanımladıysanız, ile `[DataMember(IsRequired=true)]`yeni üyeleri işaretlediğinizden emin olun. Bu `IsRequired` öznitelik hakkında daha fazla bilgi için <xref:System.Runtime.Serialization.DataMemberAttribute>bkz. Bu, bir temel sınıfın uyumlu bir tür olmasını engeller ve hatanın seri durumdan doğru türetilmiş türe bırakılmasını zorlar.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.ServiceModel.FaultException>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.FaultException>
- <xref:System.Xml.Serialization.XmlSerializer>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.CommunicationException>
- <xref:System.ServiceModel.FaultContractAttribute.Action%2A>
- <xref:System.ServiceModel.FaultException.Code%2A>
- <xref:System.ServiceModel.FaultException.Reason%2A>
- <xref:System.ServiceModel.FaultCode.SubCode%2A>
- <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>
- [Hataları Tanımlama ve Belirtme](../../../docs/framework/wcf/defining-and-specifying-faults.md)
