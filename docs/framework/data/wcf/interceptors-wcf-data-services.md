---
title: Dinleyiciler (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: 17926e144fae206d702c2bcb4f88dd2093442ed5
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517908"
---
# <a name="interceptors-wcf-data-services"></a>Dinleyiciler (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] bir uygulamanın işlem için özel mantığı ekleyebilirsiniz, böylece istek iletileri izlemesine olanak sağlar. Gelen iletiler verileri doğrulamak için bu özel mantığı kullanabilirsiniz. Bir sorgu isteğinin kapsamı gibi istek başına bir özel yetkilendirme ilkesi eklemek için kısıtlamanız için de kullanabilirsiniz.  
  
 Durdurma data Service'te özel öznitelikli yöntem tarafından gerçekleştirilir. Bu yöntemleri çağıran [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ileti işleme uygun noktaya. Kesiciler varlık kümesi olarak tanımlanır ve hizmet işlemleri gibi dinleyiciyi yöntemleri İstek parametreleri kabul edemez. Bir HTTP GET isteği işlerken, sorgu dinleyiciyi yöntemleri, dinleyiciyi'nın varlık örneğini ayarlanmış olup olmadığını belirleyen bir lambda ifadesi, sorgu sonuçları döndürülmelidir döndürmesi gerekir. Bu ifade, istenen işlem iyice daraltmak için veri hizmeti tarafından kullanılır. Aşağıda bir örnek sorgu dinleyiciyi tanımıdır.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Daha fazla bilgi için [nasıl yapılır: Veri hizmeti iletilerini ıntercept](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Sorgu olmayan işlemleri işlerken olarak adlandırılan, değişiklik dinleyicileri döndürmelidir `void` (`Nothing` Visual Basic'te). Değişiklik dinleyiciyi yöntemleri, aşağıdaki iki parametreyi kabul etmeniz gerekir:  
  
1. Varlık kümesinin varlık türüyle uyumlu bir tür parametresi. Veri Hizmeti değişiklik dinleyiciyi çağırdığında, bu parametrenin değeri istek tarafından gönderilen varlık bilgilerini ücreti yansıtılır.  
  
2. Türünde bir parametre <xref:System.Data.Services.UpdateOperations>. Bu parametrenin değeri, veri hizmeti değişiklik dinleyiciyi çağırdığında, isteği gerçekleştirmeye çalışan işlemi ücreti yansıtılır.  
  
 Bir değişiklik dinleyiciyi bir örneğin tanımı aşağıda verilmiştir.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Daha fazla bilgi için [nasıl yapılır: Veri hizmeti iletilerini ıntercept](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Aşağıdaki öznitelikler durdurma için desteklenir.  
  
 **[QueryInterceptor (** *EntitySetName* **)]**  
 Yöntemleriyle <xref:System.Data.Services.QueryInterceptorAttribute> uygulanan öznitelik kaynak hedef varlık kümesi için bir HTTP GET isteği alındığında çağrılır. Bu yöntemlerin her zaman biçiminde bir lambda ifadesi döndürmelidir `Expression<Func<T,bool>>`.  
  
 **[ChangeInterceptor (** *EntitySetName* **)]**  
 Yöntemleriyle <xref:System.Data.Services.ChangeInterceptorAttribute> uygulanan öznitelik kaynak hedef varlık kümesi için bir HTTP GET isteği dışındaki HTTP isteği alındığında çağrılır. Bu yöntemlerin her zaman döndürmelidir `void` (`Nothing` Visual Basic'te).  
  
 Daha fazla bilgi için [nasıl yapılır: Veri hizmeti iletilerini ıntercept](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Hizmet İşlemleri](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)
