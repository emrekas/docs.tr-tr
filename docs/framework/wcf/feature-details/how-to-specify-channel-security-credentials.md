---
title: 'Nasıl yapılır: Kanal Güvenliği Kimlik Bilgilerini Belirtme'
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: 761f461c1c0cb24901729a717a41bfb1b599112b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222607"
---
# <a name="how-to-specify-channel-security-credentials"></a><span data-ttu-id="ba9b2-102">Nasıl yapılır: Kanal Güvenliği Kimlik Bilgilerini Belirtme</span><span class="sxs-lookup"><span data-stu-id="ba9b2-102">How to: Specify Channel Security Credentials</span></span>
<span data-ttu-id="ba9b2-103">Windows Communication Foundation (WCF) hizmet bilinen adını COM uygulamaları, WCF hizmetlerini çağırmak sağlar.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-103">The Windows Communication Foundation (WCF) Service Moniker allows COM applications to call WCF services.</span></span> <span data-ttu-id="ba9b2-104">Çoğu WCF hizmetleri, istemci kimlik doğrulaması ve yetkilendirme kimlik bilgilerini belirtmenizi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-104">Most WCF services require the client to specify credentials for authentication and authorization.</span></span> <span data-ttu-id="ba9b2-105">Bir WCF hizmeti bir WCF istemciden çağrılırken, yönetilen kodda ya da bir uygulama yapılandırma dosyasında bu kimlik bilgileri belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-105">When calling a WCF service from a WCF client, you can specify these credentials in managed code or in an application configuration file.</span></span> <span data-ttu-id="ba9b2-106">Bir WCF hizmeti bir COM uygulamasından çağrılırken kullanabileceğiniz <xref:System.ServiceModel.ComIntegration.IChannelCredentials> kimlik bilgilerini belirtmek için arabirim.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-106">When calling a WCF service from a COM application, you can use the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface to specify credentials.</span></span> <span data-ttu-id="ba9b2-107">Bu konuda kullanarak kimlik bilgilerini belirtmek için çeşitli yollar ortaya konacaktır <xref:System.ServiceModel.ComIntegration.IChannelCredentials> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-107">This topic will illustrate various ways to specify credentials using the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface.</span></span>  
  
> [!NOTE]
>  <xref:System.ServiceModel.ComIntegration.IChannelCredentials> <span data-ttu-id="ba9b2-108">IDispatch tabanlı bir arabirim ve Visual Studio ortamında IntelliSense işlevselliği almazsınız.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-108">is an IDispatch-based interface and you will not get IntelliSense functionality in the Visual Studio environment.</span></span>  
  
 <span data-ttu-id="ba9b2-109">Bu makalede tanımlanan WCF hizmetini kullanacak olan [ileti güvenliği örneği](../../../../docs/framework/wcf/samples/message-security-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ba9b2-109">This article will use the WCF service defined in the [Message Security Sample](../../../../docs/framework/wcf/samples/message-security-sample.md).</span></span>  
  
### <a name="to-specify-a-client-certificate"></a><span data-ttu-id="ba9b2-110">Bir istemci sertifikasını belirtmek için</span><span class="sxs-lookup"><span data-stu-id="ba9b2-110">To specify a client certificate</span></span>  
  
1.  <span data-ttu-id="ba9b2-111">Setup.bat dosyasının ileti güvenliği dizininde oluşturun ve gereken test sertifikaları yüklemek için çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-111">Run the Setup.bat file in the Message Security directory to create and install the required test certificates.</span></span>  
  
2.  <span data-ttu-id="ba9b2-112">İleti güvenliği projeyi açın.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-112">Open the Message Security project.</span></span>  
  
3.  <span data-ttu-id="ba9b2-113">Ekleme `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` için `ICalculator` arabirim tanımı.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-113">Add `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` to the `ICalculator` interface definition.</span></span>  
  
4.  <span data-ttu-id="ba9b2-114">Ekleme `bindingNamespace="http://Microsoft.ServiceModel.Samples"` hizmeti için App.config dosyasındaki endpoint etikete.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-114">Add `bindingNamespace="http://Microsoft.ServiceModel.Samples"` to the endpoint tag in the App.config for the service.</span></span>  
  
5.  <span data-ttu-id="ba9b2-115">İleti güvenliği örneği oluşturun ve Service.exe çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-115">Build the Message Security Sample and run Service.exe.</span></span> <span data-ttu-id="ba9b2-116">Internet Explorer'ı kullanın ve hizmetin URI için Gözat (http://localhost:8000/ServiceModelSamples/Service) hizmetinin çalıştığından emin olmak için.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-116">Use Internet Explorer and browse to the service's URI (http://localhost:8000/ServiceModelSamples/Service) to ensure that the service is working.</span></span>  
  
6.  <span data-ttu-id="ba9b2-117">Visual Basic 6.0 açın ve yeni bir standart .exe dosyası oluşturun.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-117">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="ba9b2-118">Forma bir düğme ekleyin ve aşağıdaki kodu için tıklama işleyicisi eklemek için Ekle düğmesine çift tıklayın:</span><span class="sxs-lookup"><span data-stu-id="ba9b2-118">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7.  <span data-ttu-id="ba9b2-119">Visual Basic uygulamasını çalıştırın ve sonuçları doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-119">Run the Visual Basic application and verify the results.</span></span>  
  
     <span data-ttu-id="ba9b2-120">Visual Basic uygulamasını çağırma Ekle (3, 4) öğesinden sonuç içeren bir ileti kutusu görüntüler.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-120">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span> <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> <span data-ttu-id="ba9b2-121">veya <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> yerine de kullanılabilir <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> istemci sertifikasını ayarlamak için:</span><span class="sxs-lookup"><span data-stu-id="ba9b2-121">or <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> can also be used in place of <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> to set the Client Certificate:</span></span>  
  
    ```  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="ba9b2-122">Bu çağrı çalışmak istemci sertifikası istemciyi çalıştıran makinede güvenilir olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-122">For this call to work, the client certificate needs to be trusted on the machine the client is running on.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba9b2-123">Bilinen ad hatalı veya hizmet kullanılamıyor durumunda çağrısı `GetObject` "Geçersiz sözdizimi." belirten bir hata döndürür</span><span class="sxs-lookup"><span data-stu-id="ba9b2-123">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span> <span data-ttu-id="ba9b2-124">Bu hata iletisini alırsanız kullandığınız ad doğru olduğundan ve hizmetin kullanılabilir olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-124">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
### <a name="to-specify-user-name-and-password"></a><span data-ttu-id="ba9b2-125">Kullanıcı adı ve parola belirtmek için</span><span class="sxs-lookup"><span data-stu-id="ba9b2-125">To specify user name and password</span></span>  
  
1.  <span data-ttu-id="ba9b2-126">Kullanılacak hizmet App.config dosyasını değiştirmek `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-126">Modify the Service App.config file to use the `wsHttpBinding`.</span></span> <span data-ttu-id="ba9b2-127">Bu, kullanıcı adı ve parola doğrulaması gereklidir:</span><span class="sxs-lookup"><span data-stu-id="ba9b2-127">This is required for user name and password validation:</span></span>  

2.  <span data-ttu-id="ba9b2-128">Ayarlama `clientCredentialType` için kullanıcı adı:</span><span class="sxs-lookup"><span data-stu-id="ba9b2-128">Set the `clientCredentialType` to UserName:</span></span>  

3.  <span data-ttu-id="ba9b2-129">Visual Basic 6.0 açın ve yeni bir standart .exe dosyası oluşturun.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-129">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="ba9b2-130">Forma bir düğme ekleyin ve aşağıdaki kodu için tıklama işleyicisi eklemek için Ekle düğmesine çift tıklayın:</span><span class="sxs-lookup"><span data-stu-id="ba9b2-130">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4.  <span data-ttu-id="ba9b2-131">Visual Basic uygulamasını çalıştırın ve sonuçları doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-131">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="ba9b2-132">Visual Basic uygulamasını çağırma Ekle (3, 4) öğesinden sonuç içeren bir ileti kutusu görüntüler.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-132">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba9b2-133">Bu hizmet bilinen adı belirtilen bağlama için WSHttpBinding_ICalculator değiştirildi.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-133">The binding specified in the service moniker in this sample has been changed to WSHttpBinding_ICalculator.</span></span> <span data-ttu-id="ba9b2-134">Ayrıca bir geçerli kullanıcı adı ve parola çağrısında sağlamanız gerektiğini unutmayın. <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-134">Also note that you must supply a valid user name and password in the call to <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span></span>  
  
### <a name="to-specify-windows-credentials"></a><span data-ttu-id="ba9b2-135">Windows kimlik bilgilerini belirtmek için</span><span class="sxs-lookup"><span data-stu-id="ba9b2-135">To specify Windows Credentials</span></span>  
  
1.  <span data-ttu-id="ba9b2-136">Ayarlama `clientCredentialType` hizmet App.config dosyasında Windows için:</span><span class="sxs-lookup"><span data-stu-id="ba9b2-136">Set `clientCredentialType` to Windows in the Service App.config file:</span></span>  

2.  <span data-ttu-id="ba9b2-137">Visual Basic 6.0 açın ve yeni bir standart .exe dosyası oluşturun.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-137">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="ba9b2-138">Forma bir düğme ekleyin ve aşağıdaki kodu için tıklama işleyicisi eklemek için Ekle düğmesine çift tıklayın:</span><span class="sxs-lookup"><span data-stu-id="ba9b2-138">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="ba9b2-139">Visual Basic uygulamasını çalıştırın ve sonuçları doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-139">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="ba9b2-140">Visual Basic uygulamasını çağırma Ekle (3, 4) öğesinden sonuç içeren bir ileti kutusu görüntüler.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-140">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba9b2-141">"Etki alanı", "userID" ve "password" geçerli değerlerle değiştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-141">You must replace "domain", "userID", and "password" with valid values.</span></span>  
  
### <a name="to-specify-an-issue-token"></a><span data-ttu-id="ba9b2-142">Bir sorun belirteci belirtmek için</span><span class="sxs-lookup"><span data-stu-id="ba9b2-142">To specify an issue token</span></span>  
  
1.  <span data-ttu-id="ba9b2-143">Sorun belirteçleri yalnızca Birleşik güvenliği kullanan uygulamalar için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-143">Issue tokens are used only for applications using federated security.</span></span> <span data-ttu-id="ba9b2-144">Birleşik güvenliği hakkında daha fazla bilgi için bkz: [Federasyon ve verilen belirteçler](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) ve [Federasyon örneği](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ba9b2-144">For more information about federated security, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) and [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
     <span data-ttu-id="ba9b2-145">Aşağıdaki Visual Basic kod örneği nasıl çağrılacağını gösterir <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> yöntemi:</span><span class="sxs-lookup"><span data-stu-id="ba9b2-145">The following Visual Basic code example illustrates how to call the <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> method:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     <span data-ttu-id="ba9b2-146">Bu yöntem için parametreler hakkında daha fazla bilgi için bkz. <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-146">For more information about the parameters for this method, see <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba9b2-147">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ba9b2-147">See also</span></span>

- [<span data-ttu-id="ba9b2-148">Federasyon</span><span class="sxs-lookup"><span data-stu-id="ba9b2-148">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)
- [<span data-ttu-id="ba9b2-149">Nasıl yapılır: Federe Bir Hizmette Kimlik Bilgilerini Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="ba9b2-149">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="ba9b2-150">Nasıl yapılır: Federe İstemci Oluşturma</span><span class="sxs-lookup"><span data-stu-id="ba9b2-150">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="ba9b2-151">İleti Güvenliği</span><span class="sxs-lookup"><span data-stu-id="ba9b2-151">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="ba9b2-152">Bağlamalar ve Güvenlik</span><span class="sxs-lookup"><span data-stu-id="ba9b2-152">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
