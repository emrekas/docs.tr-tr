---
title: Bağıntı Genel Bakış
ms.date: 03/30/2017
ms.assetid: edcc0315-5d26-44d6-a36d-ea554c418e9f
ms.openlocfilehash: 7128ff531bb81fb6de526092513d5525ca138735
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512781"
---
# <a name="correlation-overview"></a>Bağıntı Genel Bakış
Bağıntı birbirine veya uygulama örneği durumu, bir ilk isteğine yanıt veya belirli sipariş kimliği gibi iş akışı hizmeti iletilerini kalıcı bir sipariş işleme iş akışı durumuna ilişkin yönelik mekanizmadır. Bu konu, bağıntı genel bir bakış sağlar. Bu bölümdeki diğer konulara bağıntı her türüne ilişkin ek bilgiler sağlayın.  
  
## <a name="types-of-correlation"></a>Bağıntı türleri  
 Bağıntı protokol tabanlı veya içerik tabanlı olabilir. Protokol tabanlı bağıntılar ileti teslim altyapısı tarafından sağlanan veri iletileri arasındaki eşlemeyi sağlamak için kullanın. Protokolüne dayalı bağıntı kullanarak bağıntılı olan iletiler ilişkili bir nesne bellekte gibi kullanarak bir <xref:System.ServiceModel.Channels.RequestContext>, veya Aktarım Protokolü tarafından sağlanan bir belirteci. İçerik tabanlı bağıntılar birbirlerine uygulama belirtilen verileri kullanarak ilgilidir. İçerik temelli bağıntı bağıntılı iletilerin birbirine iletide, müşteri numarası gibi bazı uygulama tarafından tanımlanan verilerle ilgilidir.  
  
 Bağıntı kullanımda katılan etkinlikleri bir <xref:System.ServiceModel.Activities.CorrelationHandle> Mesajlaşma etkinlikleri birbirine bağlamak için. Örneğin, bir <xref:System.ServiceModel.Activities.Send> hizmet ve bir sonraki çağırmak için kullanılan <xref:System.ServiceModel.Activities.Receive> hizmetinden bir geri al, aynı paylaşmak için kullanılan <xref:System.ServiceModel.Activities.CorrelationHandle>. Bağıntı temel alarak içerik veya protokol tabanlı olup, bu temel modeli kullanılır. Bağıntı tanıtıcı açıkça her bir etkinlik ayarlanabilir veya etkinlikleri içinde bulunabilir bir <xref:System.ServiceModel.Activities.CorrelationScope> etkinlik. Yer alan etkinlikleri bir <xref:System.ServiceModel.Activities.CorrelationScope> sahip yönetilen kendi bağıntı tanıtıcıları <xref:System.ServiceModel.Activities.CorrelationScope> ve gerekli olmayan <xref:System.ServiceModel.Activities.CorrelationHandle> açıkça ayarlamak için. A <xref:System.ServiceModel.Activities.CorrelationScope> kapsamını sağlar <xref:System.ServiceModel.Activities.CorrelationHandle> yönetimi için bir istek-yanıt bağıntısı ve bir ek bağıntı türü. Barındırılan iş akışı Hizmetleri <xref:System.ServiceModel.Activities.WorkflowServiceHost> sahip aynı varsayılan bağıntı Yönetim <xref:System.ServiceModel.Activities.CorrelationScope> etkinlik. Bu varsayılan bağıntı Yönetimi genellikle birçok senaryoda etkinlikler ileti anlamına bir <xref:System.ServiceModel.Activities.CorrelationScope> veya bir iş akışı hizmeti gerektirmez, <xref:System.ServiceModel.Activities.CorrelationHandle> birden çok Mesajlaşma etkinlikleri paralel veya iki gibi bir örtüşme olmadıkça ayarlamak <xref:System.ServiceModel.Activities.Receive> etkinlikleri paralel ya da iki <xref:System.ServiceModel.Activities.Send> iki tarafından izlenen etkinlikler <xref:System.ServiceModel.Activities.Receive> etkinlikler. Bağıntı belirli her türde kapsayan bu bölümdeki konular, varsayılan bağıntı hakkında daha fazla bilgi sağlanmaktadır. Mesajlaşma etkinlikleri hakkında daha fazla bilgi için bkz. [Mesajlaşma etkinlikleri](../../../../docs/framework/wcf/feature-details/messaging-activities.md) ve [nasıl yapılır: Mesajlaşma etkinlikleriyle iş akışı hizmeti oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md).  
  
## <a name="protocol-based-correlation"></a>Protokolüne dayalı bağıntı

Protokolüne dayalı bağıntı birbirine ve uygun örneğini iletilerini ilişkilendirmek için bir aktarım mekanizması kullanır. İstek-yanıt bağıntısı ve içerik temelli bağıntı bazı sistem tarafından sağlanan protokol bağıntılar içerir. İstek-yanıt bağıntısı gibi çift yönlü bir işlem oluşturmak için ileti etkinlikleri tek bir çift ilişkilendirmek için kullanılan bir <xref:System.ServiceModel.Activities.Send> ile eşleştirilmiş bir <xref:System.ServiceModel.Activities.ReceiveReply>, veya bir <xref:System.ServiceModel.Activities.Receive> ile eşleştirilmiş bir <xref:System.ServiceModel.Activities.SendReply>. Visual Studio iş akışı Tasarımcısı, hızlı bir şekilde bu deseni uygulamak için etkinlik şablonları kümesi de sağlar. Bağlam değişimi mekanizması açıklanan bağlam tabanlı bir bağıntı dayanır [.NET bağlam değişimi protokolü belirtimi](https://go.microsoft.com/fwlink/?LinkID=166059). Bir bağlam tabanlı gibi bağlama, içerik temelli bağıntı kullanılacak <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> veya <xref:System.ServiceModel.NetTcpContextBinding> uç noktada kullanılmalıdır.  
  
Protokol bağıntı hakkında daha fazla bilgi için bkz: [dayanıklı çift yönlü](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md) ve [istek-yanıt](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md). Visual Studio iş akışı Tasarımcısı etkinlik şablonları kullanma hakkında daha fazla bilgi için bkz. [Mesajlaşma etkinlikleri](../../../../docs/framework/wcf/feature-details/messaging-activities.md). Örnek kod için bkz: [NetContextExchangeCorrelation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee662963%28v%3dvs.100%29) örnek.  
  
## <a name="content-based-correlation"></a>İçerik temelli bağıntı

İçerik temelli bağıntı bilgi parçası için belirli bir örneğine ilişkilendirmek için iletide kullanır. Protokolüne dayalı bağıntı, ilgili her iletide bu verilerin bulunabileceği açıkça durumuna uygulama yazarı içerik temelli bağıntı gerektirir. İçerik temelli bağıntı kullanan etkinlikleri kullanarak bu ileti verilerini belirtin bir <xref:System.ServiceModel.MessageQuerySet>. İçerik temelli bağıntı, bağlam bağlamaları gibi birini kullanmayın Hizmetleri ile iletişim kurarken yararlıdır <xref:System.ServiceModel.BasicHttpContextBinding>.
  
## <a name="see-also"></a>Ayrıca bkz.

- [NetContextExchangeCorrelation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee662963%28v%3dvs.100%29)
