---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: 3102ae8d8c28be43883eeaff6c4f829b355384a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701430"
---
# <a name="servicehost"></a>\@ServiceHost
Barındırılan hizmet konak hizmeti ile üretmek için kullanılan Üreteç ve erişmek veya .svc dosyasında sağlanan barındırma Kodu derlemek için gereken diğer programlama özelliklerini ilişkilendirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a>Öznitelikler  
  
#### <a name="service"></a>Hizmet  
 Barındırılan hizmet CLR türü adı. Bu, bir veya daha fazla hizmet kişileri uygulayan bir tür tam bir adı olmalıdır.  
  
#### <a name="factory"></a>Fabrika  
 Hizmet ana bilgisayarı örneği oluşturmak için kullanılan hizmet barındırma ortamı fabrikası CLR türü adı. Bu öznitelik isteğe bağlıdır. Belirtilmemişse, varsayılan <xref:System.ServiceModel.Activation.ServiceHostFactory> kullanılan örneğini döndüren <xref:System.ServiceModel.ServiceHost>.  
  
#### <a name="debug"></a>Hata ayıklama  
 Windows Communication Foundation (WCF) hizmet hata ayıklama sembolleriyle derlenmiş olup olmadığını gösterir. `true` WCF hizmet hata ayıklama sembolleriyle derlenmiş Aksi takdirde, `false`.  
  
#### <a name="language"></a>Dil  
 Dosya (.svc) içindeki tüm satır içi kod derlenirken kullanılan dili belirtir. Değerlerin herhangi temsil edebilir. C#, VB ve C#, Visual Basic .NET ve JScript .NET için sırasıyla başvuran JS dahil olmak üzere ağ tarafından desteklenen dil. Bu öznitelik isteğe bağlıdır.  
  
#### <a name="codebehind"></a>CodeBehind  
 XML Web hizmeti XML Web hizmeti uygulayan sınıfı aynı dosyada bulunmadığı ve edilmemiş bir bütünleştirilmiş kod içine derlenmiş ve \Bin dizinine olduğunda uygulayan kaynak dosyasını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 <xref:System.ServiceModel.ServiceHost> Hizmeti barındırmak için kullanılan bir Windows Communication Foundation (WCF) programlama modeli içinde genişletilebilirlik noktasıdır. Fabrika düzeni örneği oluşturmak için kullanılan <xref:System.ServiceModel.ServiceHost> , büyük olasılıkla barındırma ortamı doğrudan örneğini oluşturmalıdır değil polimorfik bir tür olduğundan.  
  
 Varsayılan uygulama kullanan <xref:System.ServiceModel.Activation.ServiceHostFactory> bir örneğini oluşturmak için <xref:System.ServiceModel.ServiceHost>. Ancak, Fabrika uygulamanızda CLR tür adını belirterek kendi Fabrika (bir türetilmiş ana döndürür) sağlayabilirsiniz [ \@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) yönergesi.  
  
 Kendi özel hizmet barındırma ortamı fabrikası yerine varsayılan fabrika kullanmak için yalnızca tür adı sağlayın [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) yönergesi aşağıdaki gibi:  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 Fabrika uygulamaları olabildiğince hafif tutun. Özel mantığı çok sayıda varsa, kod içinde yerine ana Fabrika içinde bu mantığı koyarsanız daha yeniden kullanılabilir.  
  
 Örneğin, için AJAX etkinleştirilmiş uç noktayı etkinleştirme `MyService`, belirtin <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> değerini `Factory` varsayılan yerine bir öznitelik <xref:System.ServiceModel.Activation.ServiceHostFactory>, [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) yönerge olarak Aşağıdaki örnekte gösterilir.  
  
## <a name="example"></a>Örnek  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Özel Hizmet Konağı](../../../../../docs/framework/wcf/samples/custom-service-host.md)
