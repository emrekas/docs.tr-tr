---
title: Hizmet Sözleşmeleri Tasarlama
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF]
ms.assetid: 8e89cbb9-ac84-4f0d-85ef-0eb6be0022fd
ms.openlocfilehash: a764b18cc3016610b8a149631b4de89923a7a5b4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040625"
---
# <a name="designing-service-contracts"></a>Hizmet Sözleşmeleri Tasarlama
Bu konuda, hizmet sözleşmelerinin ne olduğu, nasıl tanımlandığı, hangi işlemlerin kullanılabildiği (ve temel alınan ileti değişimlerinin etkileri), hangi veri türlerinin kullanılacağı ve Senaryonuzun gereksinimleri.  
  
## <a name="creating-a-service-contract"></a>Hizmet sözleşmesi oluşturma  
 Hizmetler çok sayıda işlem sunar. Windows Communication Foundation (WCF) uygulamalarında, bir yöntem oluşturup <xref:System.ServiceModel.OperationContractAttribute> özniteliği ile işaretleyerek işlemleri tanımlayın. Ardından, bir hizmet sözleşmesi oluşturmak için, <xref:System.ServiceModel.ServiceContractAttribute> özniteliğiyle işaretlenmiş bir arabirim içinde bildirerek veya aynı özniteliğiyle işaretlenmiş bir sınıfta tanımlayarak işlemlerinizi birlikte gruplandırın. (Temel bir örnek için bkz [. nasıl yapılır: Bir hizmet sözleşmesi](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)tanımlayın.)  
  
 <xref:System.ServiceModel.OperationContractAttribute> Özniteliği olmayan yöntemler hizmet işlemleri değildir ve WCF Hizmetleri tarafından gösterilmez.  
  
 Bu konuda, bir hizmet sözleşmesi tasarlarken aşağıdaki karar noktaları açıklanmaktadır:  
  
- Sınıfların veya arabirimlerin kullanılıp kullanılmayacağını belirtir.  
  
- Exchange 'de kullanmak istediğiniz veri türlerini belirtme.  
  
- Kullanabileceğiniz Exchange desenlerinin türleri.  
  
- Açık güvenlik gereksinimlerini sözleşmenin bir parçası yapıp yapamayacağı.  
  
- İşlem girişleri ve çıkışları için kısıtlamalar.  
  
## <a name="classes-or-interfaces"></a>Sınıflar veya arabirimler  
 Her iki sınıf ve arabirim de bir işlev gruplandırmasını temsil eder ve bu nedenle, her ikisi de bir WCF hizmeti sözleşmesi tanımlamak için kullanılabilir. Ancak, hizmet sözleşmelerini doğrudan modellerse, arabirimleri kullanmanız önerilir. Bir uygulama olmadan, arabirimler belirli imzalara sahip bir yöntem gruplandırması tanımlamaktan daha fazla olmaz. Bir hizmet sözleşmesi arabirimi uygulayın ve bir WCF hizmeti uyguladık.  
  
 Yönetilen arabirimlerin tüm avantajları hizmet sözleşmesi arabirimleri için geçerlidir:  
  
- Hizmet sözleşmesi arabirimleri, herhangi bir sayıda diğer hizmet sözleşmesi arabirimini genişletebilir.  
  
- Tek bir sınıf, bu hizmet sözleşmesi arabirimlerini uygulayarak herhangi bir sayıda hizmet sözleşmesi uygulayabilir.  
  
- Hizmet sözleşmesi aynı olmaya devam ederken, bir hizmet sözleşmesinin uygulanmasını, arabirim uygulamasını değiştirerek değiştirebilirsiniz.  
  
- Eski arabirimi ve yenisini uygulayarak hizmetinizi sürüm sürümüne ekleyebilirsiniz. Eski istemciler özgün sürüme bağlanır, daha yeni istemciler yeni sürüme bağlanabilir.  
  
> [!NOTE]
> Diğer hizmet sözleşmesi arabirimlerinden devralma sırasında, ad veya ad alanı gibi işlem özelliklerini geçersiz kılamazsınız. Bunu yapmayı denerseniz, geçerli hizmet sözleşmesinde yeni bir işlem oluşturursunuz.  
  
 Bir hizmet sözleşmesi oluşturmak için arabirim kullanmanın bir örneği için bkz [. nasıl yapılır: Sözleşme arabirimi](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)ile bir hizmet oluşturun.  
  
 Bununla birlikte, bir hizmet sözleşmesi tanımlamak ve bu sözleşmeyi aynı anda uygulamak için bir sınıfı kullanabilirsiniz. , Ve sırasıyla sınıfına ve sınıf üzerindeki yöntemlere <xref:System.ServiceModel.ServiceContractAttribute> uygulama <xref:System.ServiceModel.OperationContractAttribute> yaparak ve doğrudan, hız ve kolaylık sağlar. Dezavantajları, yönetilen sınıfların birden çok devralmayı desteklememe ve sonuç olarak yalnızca bir hizmet sözleşmesini tek seferde uygulayabilecekleri bir dezavantajlardır. Ayrıca, sınıf veya yöntem imzalarında yapılan herhangi bir değişiklik söz konusu hizmet için genel sözleşmeyi değiştirir ve bu da, değiştirilmemiş istemcilerin hizmetinizi kullanmasını engelleyebilir. Daha fazla bilgi için bkz. [hizmet sözleşmelerini uygulama](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
 Bir hizmet sözleşmesi oluşturmak için bir sınıf kullanan ve aynı anda uygulayan bir örnek için bkz [. nasıl yapılır: Sözleşme sınıfıyla](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)bir hizmet oluşturun.  
  
 Bu noktada, bir arabirim kullanarak ve bir sınıfı kullanarak hizmet sözleşmenizi tanımlama arasındaki farkı anlamalısınız. Bir sonraki adım, bir hizmet ve istemcileri arasında hangi verilerin geri geçirilebileceğini saptarken.  
  
## <a name="parameters-and-return-values"></a>Parametreler ve dönüş değerleri  
 Her işlemin bir dönüş değeri ve parametresi vardır, ancak bunlar da vardır `void`. Ancak, bir yerel yöntemin aksine, bir nesneden diğerine başvuruları geçirebilmeniz için, hizmet işlemleri nesnelere başvuruları geçirmez. Bunun yerine, nesnelerin kopyalarını iletir.  
  
 Bu çok önemlidir çünkü bir parametre veya dönüş değerinde kullanılan her tür seri hale getirilebilir olmalıdır; diğer bir deyişle, bu türdeki bir nesneyi bayt akışına ve bayt akışından bir nesneye dönüştürmek mümkün olmalıdır.  
  
 Temel türler, .NET Framework birçok tür olduğu gibi varsayılan olarak seri hale getirilebilir.  
  
> [!NOTE]
> İşlem imzasında parametre adlarının değeri sözleşmenin bir parçasıdır ve büyük/küçük harfe duyarlıdır. Aynı parametre adını yerel olarak kullanmak ancak yayımlanan meta verilerde adı değiştirmek istiyorsanız, <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>bkz.  
  
#### <a name="data-contracts"></a>Veri Sözleşmeleri  
 Windows Communication Foundation (WCF) uygulamaları gibi hizmet odaklı uygulamalar, hem Microsoft hem de Microsoft dışı platformlarda en yüksek sayıda istemci uygulaması ile birlikte çalışmak üzere tasarlanmıştır. Mümkün olan en iyi birlikte çalışabilirlik için, hizmet sözleşmesinin hizmet işlemlerinizin verilerini açıklayan bölümü <xref:System.Runtime.Serialization.DataContractAttribute> olan <xref:System.Runtime.Serialization.DataMemberAttribute> bir veri sözleşmesi oluşturmak için türlerinizi ve öznitelikleriyle işaretlemeniz önerilir değişimi.  
  
 Veri sözleşmeleri katılım stili sözleşmelerinde: Veri sözleşmesi özniteliğini açıkça uygulamadığınız müddetçe hiçbir tür veya veri üyesi serileştirilmez. Veri sözleşmeleri, yönetilen kodun erişim kapsamıyla ilişkili değildir: Özel veri üyeleri seri hale getirilebilir ve başka bir yere erişilebilmesi için gönderilebilir. (Bir veri sözleşmesinin temel bir örneği için bkz [. nasıl yapılır: Bir sınıf veya yapı](../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)Için temel veri sözleşmesi oluşturun.) WCF, işlemin işlevselliğini etkinleştiren temel SOAP iletilerinin tanımını ve iletilerin gövdesine ve veri türlerinizi serileştirmesini sağlar. Veri türlerinizin seri hale getirilebilir olduğu sürece, işlemlerinizi tasarlarken temeldeki ileti değişim altyapısı hakkında düşünmeniz gerekmez.  
  
 Tipik WCF uygulaması, <xref:System.Runtime.Serialization.DataContractAttribute> işlemler için veri sözleşmeleri oluşturmak üzere ve <xref:System.Runtime.Serialization.DataMemberAttribute> özniteliklerini kullansa da, diğer serileştirme mekanizmalarını kullanabilirsiniz. Standart <xref:System.Runtime.Serialization.ISerializable>, <xref:System.SerializableAttribute> ve mekanizmaları,veritürlerinizinserileştirmesinibiruygulamadandiğerinetaşıyantemelalınanSOAPiletilerineişlemekiçinçalışır.<xref:System.Xml.Serialization.IXmlSerializable> Veri türlerinizin özel destek gerektirmesi durumunda daha fazla serileştirme stratejileri kullanabilirsiniz. WCF uygulamalarında veri türlerini serileştirme seçimleri hakkında daha fazla bilgi için bkz. [hizmet sözleşmeleri içinde veri aktarımı belirtme](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).  
  
#### <a name="mapping-parameters-and-return-values-to-message-exchanges"></a>Parametreleri eşleme ve dönüş değerleri Ileti alışverişlerine  
 Hizmet işlemleri, uygulamanın belirli standart güvenlik, işlem ve oturumla ilgili özelliklerini desteklemesi için gereken verilere ek olarak, uygulama verilerini geri ve geriye doğru bir şekilde veren bir dizi SOAP iletisi tarafından desteklenir. Bu durum, bir hizmet işleminin imzası, veri aktarımını destekleyebilen belirli bir temel *ileti değişim modelini* (MEP) ve bir işlemin gerektirdiği özellikleri belirler. WCF programlama modelinde üç desen belirtebilirsiniz: istek/yanıt, tek yönlü ve çift yönlü ileti desenleri.  
  
##### <a name="requestreply"></a>İstek/yanıt  
 İstek/yanıt deseninin bir istek gönderici (istemci uygulaması), isteğin bağıntılı olduğu bir yanıt aldığı bir yanıt alır. Bu varsayılan MEP 'dir çünkü bir veya daha fazla parametrenin işleme geçirildiği bir işlemi desteklediğinden ve dönüş değeri çağırana geri geçirilir. Örneğin, aşağıdaki C# kod örneği bir dize alan ve bir dize döndüren temel bir hizmet işlemini gösterir.  
  
```csharp  
[OperationContractAttribute]  
string Hello(string greeting);  
```  
  
 Eşdeğer Visual Basic kodu aşağıda verilmiştir.  
  
```vb  
<OperationContractAttribute()>  
Function Hello (ByVal greeting As String) As String  
```  
  
 Bu işlem imzası, temeldeki ileti değişimi formunu belirler. Hiçbir bağıntı yoksa, WCF döndürülen değeri hangi işlemin amaçladığı belirlenemiyor.  
  
 Farklı bir temel alınan ileti deseninin belirtilmediği, hatta ( `void` `Nothing` Visual Basic) döndürülen hizmet işlemlerinin istek/yanıt iletisi değişimlerinin olduğunu unutmayın. İşlem için sonuç, bir istemci işlemi zaman uyumsuz olarak çağırmadığı sürece istemci, normal durumda bu ileti boş olsa bile, döndürülen ileti alınana kadar işlemeyi durduruyor. Aşağıdaki C# kod örneğinde, istemci yanıt olarak boş bir ileti alınana kadar döndürmeyen bir işlem gösterilmektedir.  
  
```csharp  
[OperationContractAttribute]  
void Hello(string greeting);  
```  
  
 Eşdeğer Visual Basic kodu aşağıda verilmiştir.  
  
```vb  
<OperationContractAttribute()>  
Sub Hello (ByVal greeting As String)  
```  
  
 Yukarıdaki örnek, işlemin gerçekleştirmesi uzun sürerse istemci performansını ve yanıt hızını yavaşlatabilir, ancak geri dönseler `void`bile istek/yanıt işlemlerinin avantajları vardır. En belirgin bir tane, yanıt iletisinde SOAP hatalarının döndürülmesinin, iletişim veya işleme durumunda, hizmetle ilgili bir hata koşulunun oluştuğunu belirten bir durumdur. Bir hizmet sözleşmesinde belirtilen SOAP hataları istemci uygulamasına bir <xref:System.ServiceModel.FaultException%601> nesne olarak geçirilir, burada tür parametresi hizmet sözleşmesinde belirtilen türdür. Bu, istemcilerin WCF hizmetlerindeki hata koşullarını kolay bir şekilde bildirmesini sağlar. Özel durumlar, SOAP hataları ve hata işleme hakkında daha fazla bilgi için bkz. [anlaşmalar ve hizmetlerde hataları belirtme ve işleme](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md). İstek/yanıt hizmetini ve istemcisini bir örnek görmek için bkz [. nasıl yapılır: Istek-yanıt Sözleşmesi](../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)oluşturun. İstek-yanıt düzeniyle ilgili sorunlar hakkında daha fazla bilgi için bkz. [istek-yanıt Hizmetleri](../../../docs/framework/wcf/feature-details/request-reply-services.md).  
  
##### <a name="one-way"></a>Tek yönlü  
 Bir WCF hizmet uygulamasının istemcisi işlemin tamamlanmasını bekleyemez ve SOAP hatalarını işlemezse, işlem tek yönlü bir ileti kalıbı belirtebilir. Tek yönlü bir işlem, istemcinin bir işlemi çağırdığı ve WCF iletiyi ağa yazdığında işleme devam eden bir işlemdir. Genellikle bu, giden mesajda gönderilen verilerin son derece büyük olması durumunda istemcinin neredeyse hemen çalışmaya devam ettiğinden (verileri gönderirken bir hata olmadığı anlamına gelir.) Bu tür bir ileti değişimi stili istemciden bir hizmet uygulamasına olay benzeri davranışı destekler.  
  
 Bir iletinin gönderildiği ve hiçbirinin alındığı bir ileti değişimi, dışında bir dönüş değeri `void`belirten bir hizmet işlemini desteklemez; Bu durumda bir <xref:System.InvalidOperationException> özel durum oluşturulur.  
  
 Dönüş iletisi yok, işleme veya iletişimdeki hataları göstermek için hiçbir SOAP hatası döndürülmeyeceği anlamına gelir. (İşlemler tek yönlü işlemler olduğunda hata bilgilerini iletişim kurmak bir çift yönlü ileti değişimi deseninin olması gerekir.)  
  
 Döndüren `void`bir işlem için tek yönlü bir ileti değişimi belirtmek için, aşağıdaki C# kod örneğinde olduğu <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> gibi özelliğini `true`olarak ayarlayın.  
  
```csharp  
[OperationContractAttribute(IsOneWay=true)]  
void Hello(string greeting);  
```  
  
 Eşdeğer Visual Basic kodu aşağıda verilmiştir.  
  
```vb  
<OperationContractAttribute(IsOneWay := True)>  
Sub Hello (ByVal greeting As String)  
```  
  
 Bu yöntem, önceki istek/yanıt örneği ile aynıdır, ancak <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> özelliğinin olarak `true` ayarlanması, yöntem özdeş olsa da, hizmet işleminin dönüş iletisi göndermeyeceği ve istemcilerin hemen bir kez geri döndürdüğü anlamına gelir. giden ileti, kanal katmanına devredilmiştir. Bir örnek için bkz [. nasıl yapılır: Tek yönlü bir sözleşme](../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md)oluşturun. Tek yönlü bir model hakkında daha fazla bilgi için bkz. [tek yönlü hizmetler](../../../docs/framework/wcf/feature-details/one-way-services.md).  
  
##### <a name="duplex"></a>Çift Yönlü  
 Çift yönlü bir model, tek yönlü veya istek/yanıt mesajlaşması gibi, her iki hizmetin ve istemcinin birbirlerine ayrı ayrı ileti gönderebilme özelliği tarafından belirlenir. Bu iki yönlü iletişim biçimi, istemci ile doğrudan iletişim kurması gereken veya olay benzeri davranışlar da dahil olmak üzere ileti değişimi 'nin her tarafında zaman uyumsuz bir deneyim sağlamaya yönelik hizmetler için yararlıdır.  
  
 İstemci ile iletişim kurmak için ek mekanizma nedeniyle, çift yönlü deseni istek/yanıt veya tek yönlü desenlerden biraz daha karmaşıktır.  
  
 Bir çift yönlü sözleşme tasarlamak için, bir geri çağırma anlaşması tasarlaması ve bu geri çağırma sözleşmesinin <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> türünü, hizmet sözleşmenizi işaretleyen <xref:System.ServiceModel.ServiceContractAttribute> özniteliğin özelliğine atamanız gerekir.  
  
 Çift yönlü bir model uygulamak için, istemcisinde çağrılan yöntem bildirimlerini içeren ikinci bir arabirim oluşturmanız gerekir.  
  
 Hizmeti ve bu hizmete erişen bir istemciyi oluşturma örneği için bkz [. nasıl yapılır: Bir çift yönlü sözleşme](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md) oluşturun [ve şunları yapın: Çift yönlü sözleşmeyle](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)hizmetlere erişin. Çalışan bir örnek için bkz. [çift yönlü](../../../docs/framework/wcf/samples/duplex.md). Çift yönlü sözleşmeleri kullanma sorunları hakkında daha fazla bilgi için bkz. [çift yönlü hizmetler](../../../docs/framework/wcf/feature-details/duplex-services.md).  
  
> [!CAUTION]
> Bir hizmet çift yönlü bir ileti aldığında, yanıtın nereye gönderileceğini belirlemede `ReplyTo` bu gelen iletideki öğesine bakar. İletiyi almak için kullanılan kanal güvenli değilse, güvenilmeyen bir istemci `ReplyTo`, hedef makinenin bir hizmet reddi (DOS) için önde gelen kötü amaçlı bir ileti gönderebilir.  
  
##### <a name="out-and-ref-parameters"></a>Out ve ref parametreleri  
 Çoğu durumda, `in` parametreleri (`ByVal` Visual Basic) ve `out` parametrelerini ve `ref` parametrelerini (`ByRef` Visual Basic) kullanabilirsiniz. Hem hem `out` de `ref` parametreleri verilerin bir işlemden döndürüldüğünü belirttiğinden, aşağıdaki gibi bir işlem imzası, işlem imzası dönüşmesine `void`rağmenbiristek/yanıtişleminingerekliolduğunubelirtir.  
  
```csharp  
[ServiceContractAttribute]  
public interface IMyContract  
{  
  [OperationContractAttribute]  
  public void PopulateData(ref CustomDataType data);  
}  
```  
  
 Eşdeğer Visual Basic kodu aşağıda verilmiştir.  
  
```vb  
<ServiceContractAttribute()> _  
Public Interface IMyContract  
  <OperationContractAttribute()> _  
  Public Sub PopulateData(ByRef data As CustomDataType)  
End Interface  
```  
  
 Tek özel durumlar, imzanızın belirli bir yapıya sahip olduğu durumlardır. Örneğin, yalnızca bir işlemi bildirmek için <xref:System.ServiceModel.NetMsmqBinding> kullanılan yöntem geri dönerse `void`istemcilerle iletişim kurmak için bağlamayı kullanabilirsiniz; bir dönüş değeri, `ref`veya `out` parametresi olup olmadığı, çıkış değeri olamaz.  
  
 Ayrıca, veya `ref` parametrelerinin `out` kullanılması, değiştirilen nesneyi geri almak için işlemin temeldeki bir yanıt iletisine sahip olmasını gerektirir. İşlem tek yönlü bir işlem ise, çalışma zamanında bir <xref:System.InvalidOperationException> özel durum oluşturulur.  
  
### <a name="specify-message-protection-level-on-the-contract"></a>Sözleşmede Ileti koruma düzeyini belirtin  
 Sözleşmenizi tasarlarken, sözleşmenizi uygulayan hizmetlerin ileti koruma düzeyine de karar vermelisiniz. Bu yalnızca, Sözleşmenin uç noktasındaki bağlamaya ileti güvenliği uygulanırsa gereklidir. Bağlamanın güvenliği kapalıysa (yani, sistem tarafından sağlanmış bağlama değerini değerine <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType> <xref:System.ServiceModel.SecurityMode.None?displayProperty=nameWithType>ayarlarsa), sözleşmenin ileti koruma düzeyine karar vermeniz gerekmez. Çoğu durumda, ileti düzeyinde güvenlik uygulanmış sistem tarafından sunulan bağlamalar yeterli bir koruma düzeyi sağlar ve her bir işlemin veya her ileti için koruma düzeyini dikkate almanız gerekmez.  
  
 Koruma düzeyi, bir hizmeti destekleyen mesajların (veya ileti bölümlerinin) imzalı, imzalanmış ve şifrelenmiş olduğunu veya imza ya da şifreleme olmadan gönderilip gönderilmeyeceğini belirten bir değerdir. Koruma düzeyi çeşitli kapsamlara ayarlanabilir: Hizmet düzeyinde, belirli bir işlem için, söz konusu işlem içindeki bir ileti veya bir ileti bölümü için. Açık olarak geçersiz kılınmadıkça, bir kapsamda ayarlanan değerler daha küçük kapsamlar için varsayılan değer olur. Bir bağlama yapılandırması, sözleşme için gereken en düşük koruma düzeyini sağlayabilirse, bir özel durum oluşturulur. Anlaşma üzerinde hiçbir koruma düzeyi değeri açıkça ayarlanmamışsa bağlama yapılandırması, bağlamada ileti güvenliği varsa tüm iletiler için koruma düzeyini denetler. Bu varsayılan davranıştır.  
  
> [!IMPORTANT]
> Bir sözleşmenin tam koruma düzeyinden <xref:System.Net.Security.ProtectionLevel.EncryptAndSign?displayProperty=nameWithType> daha düşük bir şekilde farklı bir şekilde bir şekilde ayarlanması gerektiğine karar vermek, daha fazla performans elde etmek için bir ölçüde güvenlik artışı sağlayan bir karardır. Bu durumlarda kararlarınız, işlemlerinizin yanı sıra, değişdikleri verilerin değerini döndürmelidir. Daha fazla bilgi için bkz. [hizmetleri güvenli hale getirme](../../../docs/framework/wcf/securing-services.md).  
  
 Örneğin, aşağıdaki kod örneği sözleşmede ya da <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel%2A> özelliğini ayarlamayın.  
  
```csharp  
[ServiceContract]  
public interface ISampleService  
{  
  [OperationContractAttribute]  
  public string GetString();  
  
  [OperationContractAttribute]  
  public int GetInt();    
}  
```  
  
 Eşdeğer Visual Basic kodu aşağıda verilmiştir.  
  
```vb  
<ServiceContractAttribute()> _  
Public Interface ISampleService  
  
  <OperationContractAttribute()> _  
  Public Function GetString()As String  
  
  <OperationContractAttribute()> _  
  Public Function GetData() As Integer  
  
End Interface  
```  
  
 Bir uç noktada varsayılan `ISampleService` <xref:System.ServiceModel.WSHttpBinding> olan bir uygulamayla etkileşim kurarken (varsayılan <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>olan <xref:System.ServiceModel.SecurityMode.Message>), bu varsayılan koruma düzeyi olduğundan tüm iletiler şifrelenir ve imzalanır. Bununla birlikte, bir `ISampleService` hizmet varsayılan <xref:System.ServiceModel.BasicHttpBinding> olarak kullanıldığında (varsayılan <xref:System.ServiceModel.SecurityMode> <xref:System.ServiceModel.SecurityMode.None>olarak), bu bağlama için güvenlik olmadığı ve koruma düzeyi yok sayılacak (yani, iletiler şifrelenmez veya imzalanmadı). <xref:System.ServiceModel.SecurityMode> Olarak<xref:System.ServiceModel.SecurityMode.Message>değiştirilmişse, bu iletiler şifrelenir ve imzalanır (Bu, şimdi bağlamanın varsayılan koruma düzeyi olacağından).  
  
 Sözleşmeniz için koruma gereksinimlerini açıkça belirtmek veya ayarlamak istiyorsanız, <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> özelliği (veya daha küçük bir kapsamdaki `ProtectionLevel` özelliklerden herhangi biri), hizmet sözleşmeniz için gereken düzeye ayarlayın. Bu durumda, bir açık ayarı kullanmak için bağlama, kullanılan kapsamda en düşük düzeyde bu ayarı desteklemek için gereklidir. Örneğin, aşağıdaki kod örneği <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel%2A> `GetGuid` işlem için açıkça bir değeri belirtir.  
  
```csharp  
[ServiceContract]  
public interface IExplicitProtectionLevelSampleService  
{  
  [OperationContractAttribute]  
  public string GetString();  
  
  [OperationContractAttribute(ProtectionLevel=ProtectionLevel.None)]  
  public int GetInt();    
  [OperationContractAttribute(ProtectionLevel=ProtectionLevel.EncryptAndSign)]  
  public int GetGuid();    
}  
```  
  
 Eşdeğer Visual Basic kodu aşağıda verilmiştir.  
  
```vb  
<ServiceContract()> _   
Public Interface IExplicitProtectionLevelSampleService   
    <OperationContract()> _   
    Public Function GetString() As String   
    End Function   
  
    <OperationContract(ProtectionLevel := ProtectionLevel.None)> _   
    Public Function GetInt() As Integer   
    End Function   
  
    <OperationContractAttribute(ProtectionLevel := ProtectionLevel.EncryptAndSign)> _   
    Public Function GetGuid() As Integer   
    End Function   
  
End Interface  
```  
  
 Bu `IExplicitProtectionLevelSampleService` sözleşmeyi uygulayan ve varsayılan <xref:System.ServiceModel.WSHttpBinding> olan (varsayılan <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>olan <xref:System.ServiceModel.SecurityMode.Message>) bir uç noktaya sahip bir hizmet aşağıdaki davranışa sahiptir:  
  
- `GetString` İşlem iletileri şifrelenir ve imzalanır.  
  
- `GetInt` İşlem iletileri şifrelenmemiş ve işaretsiz (yani düz) metin olarak gönderilir.  
  
- `GetGuid` İşlem<xref:System.Guid?displayProperty=nameWithType> şifrelenmiş ve imzalı bir ileti ile döndürülür.  
  
 Koruma düzeyleri ve bunların nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [koruma düzeyini anlama](../../../docs/framework/wcf/understanding-protection-level.md). Güvenlik hakkında daha fazla bilgi için bkz. [hizmetleri güvenli hale getirme](../../../docs/framework/wcf/securing-services.md).  
  
##### <a name="other-operation-signature-requirements"></a>Diğer Işlem Imzası gereksinimleri  
 Bazı uygulama özellikleri belirli bir işlem imzası türü gerektirir. Örneğin, <xref:System.ServiceModel.NetMsmqBinding> bağlama sürekli Hizmetleri ve istemcileri destekler, bu da bir uygulamanın iletişimin ortasında yeniden başlatabileceği ve herhangi bir ileti olmadan kaldığınız yerden çekilebildiği durumlarda. (Daha fazla bilgi için bkz. [WCF 'de kuyruklar](../../../docs/framework/wcf/feature-details/queues-in-wcf.md).) Ancak, dayanıklı işlemler yalnızca bir `in` parametre almalıdır ve dönüş değeri içermemelidir.  
  
 İşlemler içindeki <xref:System.IO.Stream> türlerin kullanımı başka bir örnektir. Parametresi tüm ileti gövdesini içerdiğinden, bir giriş veya çıkış ( `ref` bir parametre `out` , parametre veya dönüş değeri) türünde <xref:System.IO.Stream>ise, bu, sizin için belirtilen tek giriş veya çıkış olmalıdır. <xref:System.IO.Stream> çalışmasını. Ayrıca, parametre veya dönüş türü <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType>ya da olmalıdır. Akışlar hakkında daha fazla bilgi için bkz. [büyük veri ve akış](../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).  
  
##### <a name="names-namespaces-and-obfuscation"></a>Adlar, ad alanları ve gizleme  
 Sözleşmelerin ve işlemlerin tanımındaki .NET türlerinin adları ve ad alanları, sözleşmeler WSDL 'ye dönüştürüldüğünde ve sözleşme iletileri oluşturulup gönderildiğinde önemlidir. `Name` Bunedenle`Namespace` ,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,, <xref:System.ServiceModel.ServiceContractAttribute> <xref:System.ServiceModel.OperationContractAttribute> <xref:System.Runtime.Serialization.DataContractAttribute>  <xref:System.Runtime.Serialization.DataMemberAttribute>ve diğer sözleşme öznitelikleri.  
  
 Bunun bir sonucu olarak, adlar ve ad alanları açıkça ayarlanmamışsa, derlemede Il gizleme kullanımı, anlaşma türü adlarını ve ad alanlarını değiştirir ve genellikle başarısız olan değiştirilmiş WSDL ve tel değişimleriyle sonuçlanır. Anlaşma adlarını ve ad alanlarını açıkça ayarlamazsanız ancak gizleme kullanmayı planlıyorsanız, sözleşme türü adlarının ve ad alanlarının değiştirilmesini engellemek için <xref:System.Reflection.ObfuscationAttribute> ve <xref:System.Reflection.ObfuscateAssemblyAttribute> özniteliklerini kullanın.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Istek-yanıt sözleşmesi oluşturma](../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)
- [Nasıl yapılır: Tek yönlü bir sözleşme oluşturma](../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md)
- [Nasıl yapılır: Çift yönlü sözleşme oluşturma](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [Hizmet Anlaşmalarında Veri Aktarımını Belirtme](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)
- [Sözleşme ve Hizmetlerde Hataları Belirtme ve İşleme](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
- [Oturumları Kullanma](../../../docs/framework/wcf/using-sessions.md)
- [Zaman Uyumlu ve Zaman Uyumsuz İşlemler](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)
- [Güvenilir Hizmetler](../../../docs/framework/wcf/reliable-services.md)
- [Hizmetler ve İşlemler](../../../docs/framework/wcf/services-and-transactions.md)
