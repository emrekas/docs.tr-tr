---
title: DataContract Yedeği
ms.date: 03/30/2017
ms.assetid: b0188f3c-00a9-4cf0-a887-a2284c8fb014
ms.openlocfilehash: 525ac356cd00b095e396dc80dbf663646b25b2e2
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70039848"
---
# <a name="datacontract-surrogate"></a>DataContract Yedeği
Bu örnek, bir veri sözleşmesi yedek sınıfı kullanılarak serileştirme, seri durumdan çıkarma, şema dışarı aktarma ve şema içeri aktarma gibi işlemlerin nasıl özelleştirilebileceğini gösterir. Bu örnek, verilerin serileştirildiği ve bir Windows Communication Foundation (WCF) istemci ve hizmeti arasında aktarıldığı bir istemci ve sunucu senaryosunda bir vekil 'in nasıl kullanılacağını gösterir.  
  
> [!NOTE]
> Bu örneğe ilişkin Kurulum yordamı ve derleme yönergeleri bu konunun sonunda bulunur.  
  
 Örnek, aşağıdaki hizmet sözleşmesini kullanır:  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[AllowNonSerializableTypes]  
public interface IPersonnelDataService  
{  
    [OperationContract]  
    void AddEmployee(Employee employee);  
  
    [OperationContract]  
    Employee GetEmployee(string name);  
}  
```  
  
 İşlem `AddEmployee` , kullanıcıların yeni çalışanlar hakkında veri eklemesine izin verir ve işlem `GetEmployee` , ad temelinde çalışanları aramayı destekler.  
  
 Bu işlemler aşağıdaki veri türünü kullanır:  
  
```  
[DataContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
class Employee  
{  
    [DataMember]  
    public DateTime dateHired;  
  
    [DataMember]  
    public Decimal salary;  
  
    [DataMember]  
    public Person person;  
}  
```  
  
 Türünde, Sınıf (Aşağıdaki örnek kodda gösterilen), <xref:System.Runtime.Serialization.DataContractSerializer> geçerli bir veri sözleşmesi sınıfı olmadığından tarafından serileştirilemiyor. `Person` `Employee`  
  
```  
public class Person  
{  
    public string firstName;  
  
    public string lastName;  
  
    public int age;  
  
    public Person() { }  
}  
```  
  
 <xref:System.Runtime.Serialization.DataContractAttribute> Özniteliğini`Person` sınıfına uygulayabilirsiniz, ancak bu her zaman mümkün değildir. Örneğin, `Person` sınıfı, denetiminiz olmayan ayrı bir derlemede tanımlanabilir.  
  
 Bu kısıtlama verildiğinde, `Person` sınıfı seri hale getirmenin bir yolu, öğesini ile <xref:System.Runtime.Serialization.DataContractAttribute> işaretlenen başka bir sınıfla yerine yeni sınıfa, gerekli verilerin üzerine kopyalamasıdır. Amaç, `Person` sınıfın bir DataContract <xref:System.Runtime.Serialization.DataContractSerializer>olarak görünmesini sağlar. Bu, veri olmayan sözleşme sınıflarını serileştirmenin bir yoludur.  
  
 Örnek, `Person` sınıfının adlı `PersonSurrogated`farklı bir sınıfla mantıksal olarak yerini alır.  
  
```  
[DataContract(Name="Person", Namespace = "http://Microsoft.ServiceModel.Samples")]  
public class PersonSurrogated  
{  
    [DataMember]  
    public string FirstName;  
  
    [DataMember]  
    public string LastName;  
  
    [DataMember]  
    public int Age;  
}  
```  
  
 Bu değişikliği başarmak için veri sözleşmesi yedeği kullanılır. Veri anlaşması yedeği, uygulayan <xref:System.Runtime.Serialization.IDataContractSurrogate>bir sınıftır. Bu örnekte, `AllowNonSerializableTypesSurrogate` sınıfı bu arabirimi uygular.  
  
 Arabirim uygulamasında ilk görev, öğesinden `Person` öğesine `PersonSurrogated`bir tür eşlemesi oluşturmak için kullanılır. Bu, hem serileştirme zamanında hem de şema dışa aktarma zamanında kullanılır. Bu eşleme <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29> yöntemi uygulayarak elde edilir.  
  
```  
public Type GetDataContractType(Type type)  
{  
    if (typeof(Person).IsAssignableFrom(type))  
    {  
        return typeof(PersonSurrogated);  
    }  
    return type;  
}  
```  
  
 Yöntemi, aşağıdaki örnek `Person` kodda gösterildiği gibi `PersonSurrogated` serileştirme sırasında bir örneği bir örneğe eşler. <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29>  
  
```  
public object GetObjectToSerialize(object obj, Type targetType)  
{  
    if (obj is Person)  
    {  
        Person person = (Person)obj;  
        PersonSurrogated personSurrogated = new PersonSurrogated();  
        personSurrogated.FirstName = person.firstName;  
        personSurrogated.LastName = person.lastName;  
        personSurrogated.Age = person.age;  
        return personSurrogated;  
    }  
    return obj;  
}  
```  
  
 <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> Yöntemi, aşağıdaki örnek kodda gösterildiği gibi, seri durumdan çıkarma için ters eşlemeyi sağlar.  
  
```  
public object GetDeserializedObject(object obj,   
Type targetType)  
{  
    if (obj is PersonSurrogated)  
    {  
        PersonSurrogated personSurrogated = (PersonSurrogated)obj;  
        Person person = new Person();  
        person.firstName = personSurrogated.FirstName;  
        person.lastName = personSurrogated.LastName;  
        person.age = personSurrogated.Age;  
        return person;  
    }  
    return obj;  
}  
```  
  
 Şema içeri aktarma `PersonSurrogated` sırasında veri sözleşmesini varolan `Person` sınıfla eşlemek için, örneği aşağıdaki örnek kodda gösterildiği gibi <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29> yöntemini uygular.  
  
```  
public Type GetReferencedTypeOnImport(string typeName,   
               string typeNamespace, object customData)  
{  
if (  
typeNamespace.Equals("http://schemas.datacontract.org/2004/07/DCSurrogateSample")  
)  
    {  
         if (typeName.Equals("PersonSurrogated"))  
        {  
             return typeof(Person);  
        }  
     }  
     return null;  
}  
```  
  
 Aşağıdaki örnek kod, <xref:System.Runtime.Serialization.IDataContractSurrogate> arabiriminin uygulamasını tamamlar.  
  
```  
public System.CodeDom.CodeTypeDeclaration ProcessImportedType(  
          System.CodeDom.CodeTypeDeclaration typeDeclaration,   
          System.CodeDom.CodeCompileUnit compileUnit)  
{  
    return typeDeclaration;  
}  
public object GetCustomDataToExport(Type clrType,   
                               Type dataContractType)  
{  
    return null;  
}  
  
public object GetCustomDataToExport(  
System.Reflection.MemberInfo memberInfo, Type dataContractType)  
{  
    return null;  
}  
public void GetKnownCustomDataTypes(  
        KnownTypeCollection customDataTypes)  
{  
    // It does not matter what we do here.  
    throw new NotImplementedException();  
}  
```  
  
 Bu örnekte, yedek, ServiceModel içinde adlı `AllowNonSerializableTypesAttribute`bir öznitelik tarafından etkinleştirilir. Geliştiricilerin, yukarıdaki `IPersonnelDataService` hizmet sözleşmesinde gösterildiği gibi bu özniteliği hizmet sözleşmelerine uygulaması gerekir. Bu öznitelik, `IContractBehavior` `ApplyClientBehavior` ve`ApplyDispatchBehavior` yöntemlerinde işlemleri uygular ve üzerinde yedek ayarlar.  
  
 Bu örnekte öznitelik gerekli değildir-bu örnekteki tanıtım amaçlarıyla kullanılır. Kullanıcılar ayrıca, `IContractBehavior` `IEndpointBehavior` el ile benzer veya `IOperationBehavior` kod kullanarak ya da yapılandırma kullanarak bir yedeği etkinleştirebilir.  
  
 Uygulama `IContractBehavior` , `DataContractSerializerOperationBehavior` kayıtlı olup olmadığını denetleyerek DataContract kullanan işlemlere bakar. Bu durumda, `DataContractSurrogate` özelliği o davranışa ayarlar. Aşağıdaki örnek kod, bunun nasıl yapıldığını göstermektedir. Bu işlem davranışında yedeği ayarlamak, serileştirme ve seri durumdan çıkarma için izin vermez.  
  
```  
public void ApplyClientBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime proxy)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
public void ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatch)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
private static void ApplyDataContractSurrogate(OperationDescription description)  
{  
    DataContractSerializerOperationBehavior dcsOperationBehavior = description.Behaviors.Find<DataContractSerializerOperationBehavior>();  
    if (dcsOperationBehavior != null)  
    {  
        if (dcsOperationBehavior.DataContractSurrogate == null)  
            dcsOperationBehavior.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
    }  
}  
```  
  
 Meta veri oluşturma sırasında kullanılmak üzere yedeği eklemek için ek adımların alınması gerekir. Bunu yapmak `IWsdlExportExtension` için bir mekanizma, bu örneğin gösterdiği şeydir. Başka bir yol da `WsdlExporter` doğrudan değiştirmektir.  
  
 `AllowNonSerializableTypesAttribute` Özniteliği `IWsdlExportExtension` ve uygular`IContractBehavior`. Uzantı ya da `IContractBehavior` `IEndpointBehavior` bu durumda olabilir. Yöntem uygulama, DataContract için şema oluşturma sırasında `XsdDataContractExporter` kullanılan öğesine ekleyerek yedeği sağlar. `IWsdlExportExtension.ExportContract` Aşağıdaki kod parçacığında bunun nasıl yapılacağı gösterilmektedir.  
  
```  
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
{  
    if (exporter == null)  
        throw new ArgumentNullException("exporter");  
  
    object dataContractExporter;  
    XsdDataContractExporter xsdDCExporter;  
    if (!exporter.State.TryGetValue(typeof(XsdDataContractExporter), out dataContractExporter))  
    {  
        xsdDCExporter = new XsdDataContractExporter(exporter.GeneratedXmlSchemas);  
        exporter.State.Add(typeof(XsdDataContractExporter), xsdDCExporter);  
    }  
    else  
    {  
        xsdDCExporter = (XsdDataContractExporter)dataContractExporter;  
    }  
    if (xsdDCExporter.Options == null)  
        xsdDCExporter.Options = new ExportOptions();  
  
    if (xsdDCExporter.Options.DataContractSurrogate == null)  
        xsdDCExporter.Options.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
}  
```  
  
 Örneği çalıştırdığınızda, istemci, ilk çağrının başarılı olup olmadığını denetlemek için bir GetEmployee çağrısı tarafından izlenen AddEmployee öğesini çağırır. GetEmployee işlem isteğinin sonucu istemci konsol penceresinde görüntülenir. GetEmployee işlemi, çalışanı bulma ve "Found" Yazdırma işleminde başarılı olmalıdır.  
  
> [!NOTE]
> Bu örnek, seri hale getirme, seri durumdan çıkarma ve meta veri oluşturma için bir vekil nasıl ekleneceğini gösterir. Meta verilerden kod üretimi için bir yedeği nasıl bir fişe ekleneceğini göstermez. Bir vekil 'in istemci kod üretimini eklemek için nasıl kullanılabileceği hakkında bir örnek görmek için bkz. [özel wsdl yayınlama](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) örneği.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Örneği ayarlamak, derlemek ve çalıştırmak için  
  
1. [Windows Communication Foundation Örnekleri Için tek seferlik Kurulum yordamını](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)gerçekleştirdiğinizden emin olun.  
  
2. Çözümün C# sürümünü derlemek Için [Windows Communication Foundation örnekleri oluşturma](../../../../docs/framework/wcf/samples/building-the-samples.md)konusundaki yönergeleri izleyin.  
  
3. Örneği tek veya bir çapraz makine yapılandırmasında çalıştırmak için [Windows Communication Foundation Örnekleri çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md)bölümündeki yönergeleri izleyin.  
  
> [!IMPORTANT]
> Örnekler makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizini denetleyin.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Bu dizin yoksa, tüm Windows Communication Foundation (WCF) ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri indirmek için [Windows Communication Foundation (WCF) ve Windows Workflow Foundation (WF) örneklerine .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) ' e gidin. Bu örnek, aşağıdaki dizinde bulunur.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DataContract`  
