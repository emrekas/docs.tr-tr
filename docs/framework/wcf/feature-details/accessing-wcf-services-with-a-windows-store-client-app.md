---
title: WCF Hizmetlerine Windows Mağazası İstemci Uygulaması ile Erişme
ms.date: 03/30/2017
ms.assetid: e2002ef4-5dee-4a54-9d87-03b33d35fc52
ms.openlocfilehash: 95a717f139983be8291c2d156d8dd1626a43372a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613668"
---
# <a name="accessing-wcf-services-with-a-windows-store-client-app"></a><span data-ttu-id="33ca3-102">WCF Hizmetlerine Windows Mağazası İstemci Uygulaması ile Erişme</span><span class="sxs-lookup"><span data-stu-id="33ca3-102">Accessing WCF Services with a Windows Store Client App</span></span>
<span data-ttu-id="33ca3-103">Windows 8, Windows Store uygulamaları adı verilen bir uygulama yeni bir tür tanıtır.</span><span class="sxs-lookup"><span data-stu-id="33ca3-103">Windows 8 introduces a new type of application called Windows Store applications.</span></span> <span data-ttu-id="33ca3-104">Bu uygulamaları dokunmatik ekran arabirimi geçici bir çözüm olarak tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="33ca3-104">These applications are designed around a touch screen interface.</span></span> <span data-ttu-id="33ca3-105">.NET framework 4.5, WCF hizmetlerini çağırmak Windows Store uygulamaları etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-105">.NET Framework 4.5 enables Windows Store applications to call WCF services.</span></span>  
  
## <a name="wcf-support-in-windows-store-applications"></a><span data-ttu-id="33ca3-106">Windows Store uygulamalarında WCF desteği</span><span class="sxs-lookup"><span data-stu-id="33ca3-106">WCF Support in Windows Store Applications</span></span>  
 <span data-ttu-id="33ca3-107">WCF işlevlerinin bir alt kümesini bir Windows Store uygulaması içinde bulunan, daha fazla ayrıntı için aşağıdaki bölümlere bakın.</span><span class="sxs-lookup"><span data-stu-id="33ca3-107">A subset of WCF functionality is available from within a Windows Store application, see the following sections for more details.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33ca3-108">WCF tarafından kullanıma sunulan yerine WinRT dağıtım API'leri kullanın.</span><span class="sxs-lookup"><span data-stu-id="33ca3-108">Use the WinRT syndication APIs instead of those exposed by WCF.</span></span> <span data-ttu-id="33ca3-109">Daha fazla bilgi edinmek, [WinRT dağıtım API](https://go.microsoft.com/fwlink/?LinkId=236265)</span><span class="sxs-lookup"><span data-stu-id="33ca3-109">For more information see, [WinRT Syndication API](https://go.microsoft.com/fwlink/?LinkId=236265)</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="33ca3-110">Bir Windows çalışma zamanı bileşeni için bir web hizmeti başvurusu eklemek için hizmet Başvurusu Ekle kullanımı desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="33ca3-110">Using Add Service Reference to add a web service reference to a Windows Runtime Component isn’t supported.</span></span>  
  
### <a name="supported-bindings"></a><span data-ttu-id="33ca3-111">Desteklenen bağlamaları</span><span class="sxs-lookup"><span data-stu-id="33ca3-111">Supported Bindings</span></span>  
 <span data-ttu-id="33ca3-112">Aşağıdaki WCF bağlamaları, Windows Store uygulamalarında desteklenir:</span><span class="sxs-lookup"><span data-stu-id="33ca3-112">The following WCF bindings are supported in Windows Store Applications:</span></span>  
  
1.  <xref:System.ServiceModel.BasicHttpBinding>  
  
2.  <xref:System.ServiceModel.NetTcpBinding>  
  
3.  <xref:System.ServiceModel.NetHttpBinding>  
  
4.  <xref:System.ServiceModel.Channels.CustomBinding>
  
 <span data-ttu-id="33ca3-113">Aşağıdaki bağlama öğeleri Windows Store uygulamalarında desteklenir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-113">The following binding elements are supported in Windows Store Applications</span></span>  
  
1.  <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
2.  <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
3.  <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
4.  <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
5.  <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
6.  <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
7.  <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
8.  <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
9. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="33ca3-114">Hem metin ve ikili kodlamaları desteklenmektedir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-114">Both Text and Binary encodings are supported.</span></span> <span data-ttu-id="33ca3-115">Tüm WCF aktarma modları desteklenir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-115">All WCF transfer modes are supported.</span></span> <span data-ttu-id="33ca3-116">Daha fazla bilgi edinmek, [ileti aktarma akışı](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md).</span><span class="sxs-lookup"><span data-stu-id="33ca3-116">For more information see, [Streaming Message Transfer](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md).</span></span>  
  
### <a name="add-service-reference"></a><span data-ttu-id="33ca3-117">Hizmet Başvurusu Ekle</span><span class="sxs-lookup"><span data-stu-id="33ca3-117">Add Service Reference</span></span>  
 <span data-ttu-id="33ca3-118">Bir WCF hizmeti bir Windows Store uygulamasından çağırmak için Visual Studio 2012'in hizmet Başvurusu Ekle özelliğini kullanın.</span><span class="sxs-lookup"><span data-stu-id="33ca3-118">To call a WCF service from a Windows Store application, use the Add Service Reference feature of Visual Studio 2012.</span></span> <span data-ttu-id="33ca3-119">Hizmet bir Windows Store uygulaması içinde işiniz bittiğinde Başvurusu Ekle'nın bazı değişiklikler fark edeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="33ca3-119">You will notice a few changes in the functionality of Add Service Reference when done within a Windows Store application.</span></span> <span data-ttu-id="33ca3-120">İlk yapılandırma dosyası yoksa oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="33ca3-120">First no configuration file is generated.</span></span> <span data-ttu-id="33ca3-121">Kodda yapılandırılmalıdır için yapılandırma dosyaları, Windows Store uygulamaları kullanmayın.</span><span class="sxs-lookup"><span data-stu-id="33ca3-121">Windows Store applications do not use configuration files, so they must be configured in code.</span></span> <span data-ttu-id="33ca3-122">Bu yapılandırma kodu hizmet Başvurusu Ekle tarafından oluşturulan References.cs dosyasında bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-122">This configuration code can be found in the References.cs file generated by Add Service Reference.</span></span> <span data-ttu-id="33ca3-123">Bu dosyayı görmek için Çözüm Gezgini'nde "Tüm dosyaları göster" seçtiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="33ca3-123">To see this file, make sure to select "Show All Files" in the solution explorer.</span></span> <span data-ttu-id="33ca3-124">Dosya hizmet başvuruları ve ardından Proje içinde Reference.svcmap düğümleri altında bulunur.</span><span class="sxs-lookup"><span data-stu-id="33ca3-124">The file will be located under the Service References and then Reference.svcmap nodes within the project.</span></span> <span data-ttu-id="33ca3-125">WCF hizmetleri Windows Store uygulaması içinde oluşturulan tüm işlemler zaman uyumsuz görev tabanlı zaman uyumsuz desen kullanma olacaktır.</span><span class="sxs-lookup"><span data-stu-id="33ca3-125">All operations generated for WCF services within a Windows Store application will be asynchronous using the Task-based asynchronous pattern.</span></span> <span data-ttu-id="33ca3-126">Daha fazla bilgi için [görev tabanlı zaman uyumsuz desen](https://msdn.microsoft.com/magazine/ff959203.aspx).</span><span class="sxs-lookup"><span data-stu-id="33ca3-126">For more information, see [Task-based Asynchronous Pattern](https://msdn.microsoft.com/magazine/ff959203.aspx).</span></span>  
  
 <span data-ttu-id="33ca3-127">Yapılandırma artık kod içinde oluşturulmuş olduğu için hizmet başvurusunu her güncelleştirildiğinde Reference.cs dosyasında yapılan değişikliklerin üzerine yazılır.</span><span class="sxs-lookup"><span data-stu-id="33ca3-127">Because configuration is now generated in code, any changes made in the Reference.cs file would be overwritten every time the service reference is updated.</span></span> <span data-ttu-id="33ca3-128">Bu durumu ortadan kaldırmak için istemci proxy sınıfınızda uygulayabileceğiniz kısmi bir yöntemin içinde yapılandırma kod oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="33ca3-128">To remedy this situation the configuration code is generated within a partial method, which you can implement in your client proxy class.</span></span> <span data-ttu-id="33ca3-129">Kısmi yöntem şu şekilde bildirilir:</span><span class="sxs-lookup"><span data-stu-id="33ca3-129">The partial method is declared as follows:</span></span>  
  
```csharp  
static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,  
            System.ServiceModel.Description.ClientCredentials clientCredentials);  
```  
  
 <span data-ttu-id="33ca3-130">Ardından, bu kısmi metodu uygulayın ve bağlama veya uç nokta istemci proxy Sınıfınız içinde aşağıdaki gibi değiştirin:</span><span class="sxs-lookup"><span data-stu-id="33ca3-130">You can then implement this partial method and change the binding or endpoint in your client proxy class as follows:</span></span>  
  
```csharp  
public partial class Service1Client : System.ServiceModel.ClientBase<MetroWcfClient.ServiceRefMultiEndpt.IService1>, MetroWcfClient.ServiceRefMultiEndpt.IService1  
    {   
        static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,   
            System.ServiceModel.Description.ClientCredentials clientCredentials)  
        {  
            if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
            }  
            else if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService11.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
                clientCredentials.UserName.UserName = "username1";  
                clientCredentials.UserName.Password = "password";  
            }  
            else if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.NetTcpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.Name = "MyTcpBinding";  
                serviceEndpoint.Address = new System.ServiceModel.EndpointAddress("net.tcp://localhost/tcp");  
            }  
        }  
    }  
```  
  
### <a name="serialization"></a><span data-ttu-id="33ca3-131">Serileştirme</span><span class="sxs-lookup"><span data-stu-id="33ca3-131">Serialization</span></span>  
 <span data-ttu-id="33ca3-132">Aşağıdaki seri hale getiricileri genişletme, Windows Store uygulamalarında desteklenir:</span><span class="sxs-lookup"><span data-stu-id="33ca3-132">The following serializers are supported in Windows Store applications:</span></span>  
  
1.  <span data-ttu-id="33ca3-133">DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="33ca3-133">DataContractSerializer</span></span>  
  
2.  <span data-ttu-id="33ca3-134">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="33ca3-134">DataContractJsonSerializer</span></span>  
  
3.  <span data-ttu-id="33ca3-135">XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="33ca3-135">XmlSerializer</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="33ca3-136">XmlDictionaryWriter.Write(DateTime) şimdi bir DateTime nesnesini bir dize olarak yazar.</span><span class="sxs-lookup"><span data-stu-id="33ca3-136">XmlDictionaryWriter.Write(DateTime) now writes the DateTime object as a string.</span></span>  
  
### <a name="security"></a><span data-ttu-id="33ca3-137">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="33ca3-137">Security</span></span>  

<span data-ttu-id="33ca3-138">Aşağıdaki güvenlik modu Windows Store uygulamalarında desteklenir:</span><span class="sxs-lookup"><span data-stu-id="33ca3-138">The following security modes are supported in Windows Store applications:</span></span>
  
1. <xref:System.ServiceModel.SecurityMode.None>  
  
2. <xref:System.ServiceModel.SecurityMode.Transport>  
  
3. <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>
  
4. <xref:System.ServiceModel.SecurityMode.Message>
  
<span data-ttu-id="33ca3-139">Aşağıdaki istemci kimlik bilgisi türlerinin Windows Store uygulamalarında desteklenir:</span><span class="sxs-lookup"><span data-stu-id="33ca3-139">The following client credential types are supported in Windows Store applications:</span></span>
  
1.  <span data-ttu-id="33ca3-140">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="33ca3-140">None</span></span>  
  
2.  <span data-ttu-id="33ca3-141">Temel</span><span class="sxs-lookup"><span data-stu-id="33ca3-141">Basic</span></span>  
  
3.  <span data-ttu-id="33ca3-142">Özet</span><span class="sxs-lookup"><span data-stu-id="33ca3-142">Digest</span></span>  
  
4.  <span data-ttu-id="33ca3-143">Anlaşma</span><span class="sxs-lookup"><span data-stu-id="33ca3-143">Negotiate</span></span>  
  
5.  <span data-ttu-id="33ca3-144">NTLM</span><span class="sxs-lookup"><span data-stu-id="33ca3-144">NTLM</span></span>  
  
6.  <span data-ttu-id="33ca3-145">Windows</span><span class="sxs-lookup"><span data-stu-id="33ca3-145">Windows</span></span>  
  
7.  <span data-ttu-id="33ca3-146">Kullanıcı adı (ileti güvenliği)</span><span class="sxs-lookup"><span data-stu-id="33ca3-146">Username (Message Security)</span></span>  
  
8.  <span data-ttu-id="33ca3-147">Windows (aktarım güvenliği)</span><span class="sxs-lookup"><span data-stu-id="33ca3-147">Windows (Transport Security)</span></span>  
  
 <span data-ttu-id="33ca3-148">Erişim ve varsayılan Windows kimlik bilgilerini göndermek Windows Store uygulamaları için sırada Package.appmanifest dosyası içinde bu işlevi etkinleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-148">In order for Windows Store applications to access and send default Windows credentials, you must enable this functionality within the Package.appmanifest file.</span></span> <span data-ttu-id="33ca3-149">Bu dosyayı açmak, özellikleri sekmesini seçin ve "Varsayılan Windows kimlik bilgileri" seçin.</span><span class="sxs-lookup"><span data-stu-id="33ca3-149">Open this file and select the Capabilities tab and select "Default Windows Credentials".</span></span> <span data-ttu-id="33ca3-150">Bu, uygulama etki alanı kimlik bilgileri gerektiren intranet kaynaklarına bağlanmanıza imkan sağlar.</span><span class="sxs-lookup"><span data-stu-id="33ca3-150">This allows the application to connect to intranet resources that require domain credentials.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33ca3-151">Çapraz makine çağrıları yapmak Windows Store uygulamaları için sırayla "Ev/iş ağı" adlı başka bir özelliği etkinleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-151">In order for Windows Store applications to make cross machine calls you must enable another capability called "Home/Work Networking".</span></span> <span data-ttu-id="33ca3-152">Bu ayar, Özellikler sekmesi altındaki Package.appmanifest dosyasındaki desteklenir. Ev/iş ağı onay kutusunu işaretleyin.</span><span class="sxs-lookup"><span data-stu-id="33ca3-152">This setting is also in the Package.appmanifest file under the Capabilities tab. Select the Home/Work Networking checkbox.</span></span> <span data-ttu-id="33ca3-153">Bu, kullanıcının ağlara gelen ve giden erişimi, ev ve iş yerleri gibi güvenilen uygulamanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="33ca3-153">This gives your application inbound and outbound access to the networks of the user’s trusted places like home and work.</span></span> <span data-ttu-id="33ca3-154">Önemli gelen bağlantı noktalarının her zaman engellenir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-154">Inbound critical ports are always blocked.</span></span> <span data-ttu-id="33ca3-155">Internet'te hizmetlerine erişmek için aynı zamanda Internet (istemci) özelliği etkinleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-155">For accessing services on the internet you must also enable Internet (Client) capability.</span></span>  
  
### <a name="misc"></a><span data-ttu-id="33ca3-156">Çeşitli</span><span class="sxs-lookup"><span data-stu-id="33ca3-156">Misc</span></span>  
 <span data-ttu-id="33ca3-157">Aşağıdaki sınıflar kullanımı, Windows Store uygulamaları için desteklenir:</span><span class="sxs-lookup"><span data-stu-id="33ca3-157">The use of the following classes is supported for Windows Store Applications:</span></span>  
  
1.  <xref:System.ServiceModel.ChannelFactory>  
  
2.  <xref:System.ServiceModel.DuplexChannelFactory%601>
  
3.  <xref:System.ServiceModel.CallbackBehaviorAttribute>  
  
### <a name="defining-service-contracts"></a><span data-ttu-id="33ca3-158">Hizmet sözleşmelerini tanımlama</span><span class="sxs-lookup"><span data-stu-id="33ca3-158">Defining Service Contracts</span></span>  
 <span data-ttu-id="33ca3-159">Yalnızca görev tabanlı zaman uyumsuz deseni kullanılarak zaman uyumsuz hizmet işlemleri tanımlama öneririz.</span><span class="sxs-lookup"><span data-stu-id="33ca3-159">We recommend only defining asynchronous service operations using the task-based async pattern.</span></span> <span data-ttu-id="33ca3-160">Bu, Windows Store uygulamalarını bir hizmet işlemi çağrılırken yanıt verebilir durumda kalmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="33ca3-160">This ensures Windows Store applications remain responsive while calling a service operation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="33ca3-161">Eşzamanlı bir işlem tanımlarsanız, hiçbir özel durum sırasında yalnızca zaman uyumsuz işlemleri tanımlamak için önemle tavsiye edilir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-161">While no exception will be thrown if you define a synchronous operation, it is strongly recommended to only define asynchronous operations.</span></span>  
  
### <a name="calling-wcf-services-from-windows-store-applications"></a><span data-ttu-id="33ca3-162">WCF hizmetleri Windows Store uygulamalarından çağırma</span><span class="sxs-lookup"><span data-stu-id="33ca3-162">Calling WCF Services from Windows Store Applications</span></span>  
 <span data-ttu-id="33ca3-163">Daha önce belirtildiği gibi tüm yapılandırma oluşturulan proxy sınıfı GetBindingForEndpoint yönteminde kodda yapılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="33ca3-163">As mentioned before all configuration must be done in code in the GetBindingForEndpoint method in the generated proxy class.</span></span> <span data-ttu-id="33ca3-164">Bir hizmet işlemi çağrılırken, aşağıdaki kod parçacığında gösterildiği gibi tüm görev tabanlı zaman uyumsuz yöntem çağırma aynı gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="33ca3-164">Calling a service operation is done the same as calling any task-based asynchronous method as shown in the following code snippet.</span></span>  
  
```csharp  
void async SomeMethod()  
{  
    ServiceClient proxy = new ServiceClient();  
    Task<T> results = await proxy.CallAsync(param1, param2);  
    T result = results.Result;  
    if (result.Success)  
    {  
       // Do something with result  
    }  
}  
```  
  
 <span data-ttu-id="33ca3-165">Async anahtar sözcüğü zaman uyumsuz yöntemini çağıran, zaman uyumsuz çağrı ve await anahtar sözcüğü yapmadan yöntemi kullanımına dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="33ca3-165">Notice the use of the async keyword on the method making the asynchronous call and the await keyword when calling the asynchronous method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ca3-166">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="33ca3-166">See also</span></span>
- [<span data-ttu-id="33ca3-167">WCF'de Windows Store Apps blogu</span><span class="sxs-lookup"><span data-stu-id="33ca3-167">WCF in Windows Store Apps Blog</span></span>](https://blogs.msdn.com/b/piyushjo/archive/2011/09/22/wcf-in-win8-metro-styled-apps-absolutely-supported.aspx)
- [<span data-ttu-id="33ca3-168">WCF Windows Store istemcileri ve güvenlik</span><span class="sxs-lookup"><span data-stu-id="33ca3-168">WCF Windows Store Clients and Security</span></span>](https://blogs.msdn.com/b/piyushjo/archive/2011/10/11/calling-a-wcf-service-from-a-metro-application-adding-security.aspx)
- [<span data-ttu-id="33ca3-169">Windows Store uygulamaları ve çapraz makine çağrıları</span><span class="sxs-lookup"><span data-stu-id="33ca3-169">Windows Store Apps and Cross Machine Calls</span></span>](https://blogs.msdn.com/b/piyushjo/archive/2011/10/22/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario.aspx)
- [<span data-ttu-id="33ca3-170">Azure'da Windows Store uygulamasında dağıtılan bir WCF Hizmeti çağırma</span><span class="sxs-lookup"><span data-stu-id="33ca3-170">Calling a WCF Service Deployed in Azure from a Windows Store App</span></span>](https://blogs.msdn.com/b/piyushjo/archive/2011/10/22/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario.aspx)
- [<span data-ttu-id="33ca3-171">WCF Güvenliğini Programlama</span><span class="sxs-lookup"><span data-stu-id="33ca3-171">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
- [<span data-ttu-id="33ca3-172">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="33ca3-172">Bindings</span></span>](../../../../docs/framework/wcf/bindings.md)
