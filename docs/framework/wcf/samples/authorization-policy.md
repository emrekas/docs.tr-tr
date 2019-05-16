---
title: Yetkilendirme İlkesi
ms.date: 03/30/2017
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
ms.openlocfilehash: f148af25f85731c4ff15727b328f3f905356fe6e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637463"
---
# <a name="authorization-policy"></a><span data-ttu-id="1425d-102">Yetkilendirme İlkesi</span><span class="sxs-lookup"><span data-stu-id="1425d-102">Authorization Policy</span></span>

<span data-ttu-id="1425d-103">Bu örnek bir özel talep yetkilendirme ilkesi ve bir ilişkili özel hizmet Yetkilendirme Yöneticisi'ni uygulamak nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="1425d-103">This sample demonstrates how to implement a custom claim authorization policy and an associated custom service authorization manager.</span></span> <span data-ttu-id="1425d-104">Hizmet işlemlerine ve erişim denetimleri önce talep tabanlı erişim denetimlerini hizmet yapar verdiğinde çağıran belirli hakları kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="1425d-104">This is useful when the service makes claim-based access checks to service operations and prior to the access checks, grants the caller certain rights.</span></span> <span data-ttu-id="1425d-105">Bu örnek, talepleri ve bunun yanı sıra işlemi sonlandırılmış talepler kümesi karşı bir erişim denetimi yapmak için ekleme işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="1425d-105">This sample shows both the process of adding claims as well as the process for doing an access check against the finalized set of claims.</span></span> <span data-ttu-id="1425d-106">Tüm uygulama iletileri istemci ve sunucu arasında imzalanmış ve şifrelenmiş.</span><span class="sxs-lookup"><span data-stu-id="1425d-106">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="1425d-107">Varsayılan olarak `wsHttpBinding` bağlama, bir kullanıcı adı ve parola istemci tarafından sağlanan kullanılan oturum açmak için geçerli bir Windows NT hesap.</span><span class="sxs-lookup"><span data-stu-id="1425d-107">By default with the `wsHttpBinding` binding, a username and password supplied by the client are used to logon to a valid Windows NT account.</span></span> <span data-ttu-id="1425d-108">Bu örnek nasıl özel bir gösterir <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> istemcinin kimliğini doğrulamak için.</span><span class="sxs-lookup"><span data-stu-id="1425d-108">This sample demonstrates how to utilize a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to authenticate the client.</span></span> <span data-ttu-id="1425d-109">Ayrıca bu örnek, bir X.509 sertifikası kullanarak hizmet kimlik doğrulaması istemci gösterir.</span><span class="sxs-lookup"><span data-stu-id="1425d-109">In addition this sample shows the client authenticating to the service using an X.509 certificate.</span></span> <span data-ttu-id="1425d-110">Bu örnek uygulanışı gösterilmektedir <xref:System.IdentityModel.Policy.IAuthorizationPolicy> ve <xref:System.ServiceModel.ServiceAuthorizationManager>, bunlar arasında belirli kullanıcılar için hizmetin belirli yöntemler için erişim verin.</span><span class="sxs-lookup"><span data-stu-id="1425d-110">This sample shows an implementation of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and <xref:System.ServiceModel.ServiceAuthorizationManager>, which between them grant access to specific methods of the service for specific users.</span></span> <span data-ttu-id="1425d-111">Bu örnek dayanır [ileti güvenliği kullanıcı adı](../../../../docs/framework/wcf/samples/message-security-user-name.md), ama öncesinde bir talep dönüştürmeyi gerçekleştirmek nasıl gösterir <xref:System.ServiceModel.ServiceAuthorizationManager> çağrılan.</span><span class="sxs-lookup"><span data-stu-id="1425d-111">This sample is based on the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md), but demonstrates how to perform a claim transformation prior to the <xref:System.ServiceModel.ServiceAuthorizationManager> being called.</span></span>

> [!NOTE]
> <span data-ttu-id="1425d-112">Bu örnek için Kurulum yordamı ve derleme yönergelerini, bu konunun sonunda yer alır.</span><span class="sxs-lookup"><span data-stu-id="1425d-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="1425d-113">Özet olarak, bu örnek gösterir nasıl:</span><span class="sxs-lookup"><span data-stu-id="1425d-113">In summary, this sample demonstrates how:</span></span>

- <span data-ttu-id="1425d-114">İstemci, bir kullanıcı adı parola kullanılarak doğrulanabilir.</span><span class="sxs-lookup"><span data-stu-id="1425d-114">The client can be authenticated using a user name-password.</span></span>

- <span data-ttu-id="1425d-115">İstemci, bir X.509 sertifikası kullanılarak doğrulanabilir.</span><span class="sxs-lookup"><span data-stu-id="1425d-115">The client can be authenticated using an X.509 certificate.</span></span>

- <span data-ttu-id="1425d-116">Sunucu karşı özel bir istemci kimlik doğrulama `UsernamePassword` Doğrulayıcı.</span><span class="sxs-lookup"><span data-stu-id="1425d-116">The server validates the client credentials against a custom `UsernamePassword` validator.</span></span>

- <span data-ttu-id="1425d-117">Sunucu sunucusunun X.509 sertifikasını kullanarak kimlik doğrulaması yapılır.</span><span class="sxs-lookup"><span data-stu-id="1425d-117">The server is authenticated using the server's X.509 certificate.</span></span>

- <span data-ttu-id="1425d-118">Sunucu kullanabilir <xref:System.ServiceModel.ServiceAuthorizationManager> erişimi denetlemek için bazı yöntemler hizmetinde.</span><span class="sxs-lookup"><span data-stu-id="1425d-118">The server can use <xref:System.ServiceModel.ServiceAuthorizationManager> to control access to certain methods in the service.</span></span>

- <span data-ttu-id="1425d-119">Nasıl uygulanacağı <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="1425d-119">How to implement <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>

<span data-ttu-id="1425d-120">Hizmet, App.config yapılandırma dosyası kullanılarak tanımlanmış hizmet ile iletişim kurmak için iki uç noktalarını kullanıma sunar. Her uç nokta, adres, bağlama ve bir sözleşme oluşur.</span><span class="sxs-lookup"><span data-stu-id="1425d-120">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="1425d-121">Standart ile yapılandırılmış bir bağlama `wsHttpBinding` bağlama kullanan WS-güvenlik ve istemci kimlik doğrulama kullanıcı adı.</span><span class="sxs-lookup"><span data-stu-id="1425d-121">One binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client username authentication.</span></span> <span data-ttu-id="1425d-122">Bir standart yapılandırılmış diğer bağlama `wsHttpBinding` bağlaması, WS-güvenlik ve istemci sertifikası kimlik doğrulaması kullanır.</span><span class="sxs-lookup"><span data-stu-id="1425d-122">The other binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client certificate authentication.</span></span> <span data-ttu-id="1425d-123">[ \<Davranışı >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) hizmet kimlik doğrulaması için kullanılacak olan kullanıcı kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="1425d-123">The [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="1425d-124">Sunucu sertifikası için aynı değeri içermelidir `SubjectName` özelliği olarak `findValue` özniteliğini [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="1425d-124">The server certificate must contain the same value for the `SubjectName` property as the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <!-- configure base address provided by host -->
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>
        </baseAddresses>
      </host>
      <!-- use base address provided by host, provide two endpoints -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <endpoint address="certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding2"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
    <message clientCredentialType="UserName" />
        </security>
      </binding>
      <!-- X509 certificate binding -->
      <binding name="Binding2">
        <security mode="Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior" >
        <serviceDebug includeExceptionDetailInFaults ="true" />
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.
          -->
          <clientCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
          <!--
          The serviceAuthorization behavior allows one to specify custom authorization policies.
          -->
          <authorizationPolicies>
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />
          </authorizationPolicies>
        </serviceAuthorization>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

<span data-ttu-id="1425d-125">İstemci uç nokta yapılandırması her bir yapılandırma adı, hizmet uç noktası, bağlama ve sözleşme için mutlak bir adres oluşur.</span><span class="sxs-lookup"><span data-stu-id="1425d-125">Each client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="1425d-126">Bağlama istemci belirtildiği gibi uygun güvenlik moduyla bu durumda yapılandırılan [ \<Güvenlik >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) ve `clientCredentialType` belirtilmiş [ \<ileti >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1425d-126">The client binding is configured with the appropriate security mode as specified in this case in the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) and `clientCredentialType` as specified in the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span></span>

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
            address="http://localhost:8001/servicemodelsamples/service/username"
    binding="wsHttpBinding"
    bindingConfiguration="Binding1"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" >
      </endpoint>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
                        address="http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
            bindingConfiguration="Binding2"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
        <!-- X509 certificate binding -->
        <binding name="Binding2">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
    </wsHttpBinding>
    </bindings>

    <behaviors>
      <behavior name="ClientCertificateBehavior">
        <clientCredentials>
          <serviceCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust
            means that if the certificate
            is in the user's Trusted People store, then it will be
            trusted without performing a
            validation of the certificate's issuer chain. This setting
            is used here for convenience so that the
            sample can be run without having to have certificates
            issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust.
            The security implications of this
            setting should be carefully considered before using
            PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode = "PeerOrChainTrust" />
          </serviceCertificate>
        </clientCredentials>
      </behavior>
    </behaviors>

  </system.serviceModel>
```

<span data-ttu-id="1425d-127">Kullanıcı adı tabanlı uç noktası için istemci uygulaması, kullanıcı adını ve parolayı ayarlar.</span><span class="sxs-lookup"><span data-stu-id="1425d-127">For the user name-based endpoint, the client implementation sets the user name and password to use.</span></span>

```csharp
// Create a client with Username endpoint configuration
CalculatorClient client1 = new CalculatorClient("Username");

client1.ClientCredentials.UserName.UserName = "test1";
client1.ClientCredentials.UserName.Password = "1tset";

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client1.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client1.Close();
```

<span data-ttu-id="1425d-128">Sertifika tabanlı uç noktası için kullanılacak istemci sertifikası istemci uygulaması ayarlar.</span><span class="sxs-lookup"><span data-stu-id="1425d-128">For the certificate-based endpoint, the client implementation sets the client certificate to use.</span></span>

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client2 = new CalculatorClient("Certificate");

client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client2.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client2.Close();
```

<span data-ttu-id="1425d-129">Bu örnek bir özel kullanan <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> kullanıcı adları ve parolaları doğrulamak için.</span><span class="sxs-lookup"><span data-stu-id="1425d-129">This sample uses a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to validate user names and passwords.</span></span> <span data-ttu-id="1425d-130">Örnek uygulayan `MyCustomUserNamePasswordValidator`, türetilmiş <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="1425d-130">The sample implements `MyCustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="1425d-131">Belgelere bakın <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="1425d-131">See the documentation about <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="1425d-132">İle tümleştirme tanıtmak amacıyla <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, bu özel Doğrulayıcı sağlayıcısı örnek uygulayan <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> burada belirtilen kullanıcı adıyla eşleşen parola aşağıdaki kodda gösterildiği gibi kullanıcı adı/parola çiftlerini kabul etmek için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1425d-132">For the purposes of demonstrating the integration with the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, this custom validator sample implements the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method to accept user name/password pairs where the user name matches the password as shown in the following code.</span></span>

```csharp
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator
{
  // This method validates users. It allows in two users,
  // test1 and test2 with passwords 1tset and 2tset respectively.
  // This code is for illustration purposes only and
  // MUST NOT be used in a production environment because it
  // is NOT secure.
  public override void Validate(string userName, string password)
  {
    if (null == userName || null == password)
    {
      throw new ArgumentNullException();
    }

    if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
    {
      throw new SecurityTokenException("Unknown Username or Password");
    }
  }
}
```

<span data-ttu-id="1425d-133">Doğrulayıcı hizmeti kodunda uygulandıktan sonra hizmet ana bilgisayarı kullanmak için Doğrulayıcı örneği hakkında bilgilendirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="1425d-133">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="1425d-134">Bu yapılır aşağıdaki kodu kullanarak:</span><span class="sxs-lookup"><span data-stu-id="1425d-134">This is done using the following code:</span></span>

```csharp
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();
```

<span data-ttu-id="1425d-135">Ya da aynı şeyi yapılandırmasında yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="1425d-135">Or you can do the same thing in configuration:</span></span>

```xml
<behavior ...>
    <serviceCredentials>
      <!--
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
      -->
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
    ...
    </serviceCredentials>
</behavior>
```

<span data-ttu-id="1425d-136">Windows Communication Foundation (WCF) erişim denetimi gerçekleştirmek için zengin talep tabanlı modeli sağlar.</span><span class="sxs-lookup"><span data-stu-id="1425d-136">Windows Communication Foundation (WCF) provides a rich claims-based model for performing access checks.</span></span> <span data-ttu-id="1425d-137"><xref:System.ServiceModel.ServiceAuthorizationManager> Nesne erişim denetimi gerçekleştirmek ve istemci ile ilişkili talep hizmet yöntemi erişimi gereksinimleri karşılayıp olup olmadığını belirlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1425d-137">The <xref:System.ServiceModel.ServiceAuthorizationManager> object is used to perform the access check and determine whether the claims associated with the client satisfy the requirements necessary to access the service method.</span></span>

<span data-ttu-id="1425d-138">Gösterim amaçları doğrultusunda, bu örnek uygulanışı gösterilmektedir. <xref:System.ServiceModel.ServiceAuthorizationManager> uygulayan <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> talep türü tabanlı yöntemler bir kullanıcının erişmesine izin vermek için yöntemini `http://example.com/claims/allowedoperation` değeri olan işlem eylemi URI'si çağrılacak izin verilir.</span><span class="sxs-lookup"><span data-stu-id="1425d-138">For the purposes of demonstration, this sample shows an implementation of <xref:System.ServiceModel.ServiceAuthorizationManager> that implements the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method to allow a user's access to methods based on claims of type `http://example.com/claims/allowedoperation` whose value is the Action URI of the operation that is allowed to be called.</span></span>

```csharp
public class MyServiceAuthorizationManager : ServiceAuthorizationManager
{
  protected override bool CheckAccessCore(OperationContext operationContext)
  {
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;
    Console.WriteLine("action: {0}", action);
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)
    {
      if ( cs.Issuer == ClaimSet.System )
      {
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))
        {
          Console.WriteLine("resource: {0}", c.Resource.ToString());
          if (action == c.Resource.ToString())
            return true;
        }
      }
    }
    return false;
  }
}
```

<span data-ttu-id="1425d-139">Özel <xref:System.ServiceModel.ServiceAuthorizationManager> olduğu uygulanan, hizmet ana bilgisayarı hakkında bilgilendirilmesi gereken <xref:System.ServiceModel.ServiceAuthorizationManager> kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="1425d-139">Once the custom <xref:System.ServiceModel.ServiceAuthorizationManager> is implemented, the service host must be informed about the <xref:System.ServiceModel.ServiceAuthorizationManager> to use.</span></span> <span data-ttu-id="1425d-140">Bu, aşağıdaki kodda gösterildiği gibi gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="1425d-140">This is done as shown in the following code.</span></span>

```xml
<behavior ...>
    ...
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
        ...
    </serviceAuthorization>
</behavior>
```

<span data-ttu-id="1425d-141">Birincil <xref:System.IdentityModel.Policy.IAuthorizationPolicy> uygulamak için yöntem <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1425d-141">The primary <xref:System.IdentityModel.Policy.IAuthorizationPolicy> method to implement is the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method.</span></span>

```csharp
public class MyAuthorizationPolicy : IAuthorizationPolicy
{
    string id;

    public MyAuthorizationPolicy()
    {
    id =  Guid.NewGuid().ToString();
    }

    public bool Evaluate(EvaluationContext evaluationContext,
                                            ref object state)
    {
        bool bRet = false;
        CustomAuthState customstate = null;

        if (state == null)
        {
            customstate = new CustomAuthState();
            state = customstate;
        }
        else
            customstate = (CustomAuthState)state;
        Console.WriteLine("In Evaluate");
        if (!customstate.ClaimsAdded)
        {
           IList<Claim> claims = new List<Claim>();

           foreach (ClaimSet cs in evaluationContext.ClaimSets)
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,
                                         Rights.PossessProperty))
                  foreach (string s in
                        GetAllowedOpList(c.Resource.ToString()))
                  {
                       claims.Add(new
               Claim("http://example.com/claims/allowedoperation",
                                    s, Rights.PossessProperty));
                            Console.WriteLine("Claim added {0}", s);
                      }
                   evaluationContext.AddClaimSet(this,
                           new DefaultClaimSet(this.Issuer,claims));
                   customstate.ClaimsAdded = true;
                   bRet = true;
                }
         else
         {
              bRet = true;
         }
         return bRet;
     }
...
}
```

<span data-ttu-id="1425d-142">Önceki kodun gösterdiği nasıl <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> yöntemi yeni talep işleme etkiler ve belirli bir talep ekler eklendiğinizi denetler.</span><span class="sxs-lookup"><span data-stu-id="1425d-142">The previous code shows how the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method checks that no new claims have been added that affect the processing and adds specific claims.</span></span> <span data-ttu-id="1425d-143">İzin verilen bir talep elde edilen `GetAllowedOpList` belirli bir kullanıcının gerçekleştirmesine izin işlemleri listesini döndürmek için uygulanan yöntem.</span><span class="sxs-lookup"><span data-stu-id="1425d-143">The claims that are allowed are obtained from the `GetAllowedOpList` method, which is implemented to return a specific list of operations that the user is allowed to perform.</span></span> <span data-ttu-id="1425d-144">Yetkilendirme İlkesi, belirli bir işlemi erişmek için talep ekler.</span><span class="sxs-lookup"><span data-stu-id="1425d-144">The authorization policy adds claims for accessing the particular operation.</span></span> <span data-ttu-id="1425d-145">Bu daha sonra tarafından kullanılan <xref:System.ServiceModel.ServiceAuthorizationManager> erişim denetimi kararları gerçekleştirilecek.</span><span class="sxs-lookup"><span data-stu-id="1425d-145">This is later used by the <xref:System.ServiceModel.ServiceAuthorizationManager> to perform access check decisions.</span></span>

<span data-ttu-id="1425d-146">Özel <xref:System.IdentityModel.Policy.IAuthorizationPolicy> , hizmet ana bilgisayarı Yetkilendirme İlkeleri hakkında bilgilendirilmesi kullanmak için uygulanır.</span><span class="sxs-lookup"><span data-stu-id="1425d-146">Once the custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> is implemented, the service host must be informed about the authorization policies to use.</span></span>

```xml
<serviceAuthorization ...>
       <authorizationPolicies>
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />
       </authorizationPolicies>
</serviceAuthorization>
```

<span data-ttu-id="1425d-147">Örneği çalıştırdığınızda, işlem isteklerini ve yanıtlarını istemci konsol penceresinde görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="1425d-147">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="1425d-148">İstemci başarıyla ekleme, çıkarma ve birden çok yöntem çağrıları ve bölme yöntem çağrılmaya çalışılırken "Erişim engellendi" iletisi alır.</span><span class="sxs-lookup"><span data-stu-id="1425d-148">The client successfully calls the Add, Subtract and Multiple methods and gets an "Access is denied" message when trying to call the Divide method.</span></span> <span data-ttu-id="1425d-149">İstemci bilgisayarı için istemci penceresinde ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="1425d-149">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="1425d-150">Kurulum toplu iş dosyası</span><span class="sxs-lookup"><span data-stu-id="1425d-150">Setup Batch File</span></span>

<span data-ttu-id="1425d-151">Bu örnekle dahil Setup.bat toplu iş dosyası ile ilgili sertifika sunucusu sertifika tabanlı güvenlik gerektiren şirket içinde barındırılan bir uygulamayı çalıştırmak için sunucu yapılandırmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="1425d-151">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span>

<span data-ttu-id="1425d-152">Aşağıda, böylece uygun yapılandırmasında çalıştırılacak değiştirilebilir toplu iş dosyaları farklı bölümlerini kısa bir genel bakış sağlar:</span><span class="sxs-lookup"><span data-stu-id="1425d-152">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="1425d-153">Sunucu sertifikası oluşturuluyor.</span><span class="sxs-lookup"><span data-stu-id="1425d-153">Creating the server certificate.</span></span>

    <span data-ttu-id="1425d-154">Setup.bat toplu iş dosyasından aşağıdaki satırları kullanılacak sunucu sertifikası oluşturun.</span><span class="sxs-lookup"><span data-stu-id="1425d-154">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="1425d-155">% Sunucu_adı % değişkeni, sunucu adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="1425d-155">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="1425d-156">Kendi sunucu adını belirtmek için bu değişkeni değiştirin.</span><span class="sxs-lookup"><span data-stu-id="1425d-156">Change this variable to specify your own server name.</span></span> <span data-ttu-id="1425d-157">Localhost varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="1425d-157">The default value is localhost.</span></span>

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="1425d-158">Sunucu sertifikasını istemcinin güvenilen sertifika depolama alanına yükleniyor.</span><span class="sxs-lookup"><span data-stu-id="1425d-158">Installing the server certificate into client's trusted certificate store.</span></span>

    <span data-ttu-id="1425d-159">İstemci güvenilir kişiler uygulamasına Setup.bat toplu dosya kopyalama sunucu sertifikasının aşağıdaki satırları depolayın.</span><span class="sxs-lookup"><span data-stu-id="1425d-159">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="1425d-160">Makecert.exe tarafından oluşturulan sertifikaları örtük olarak istemci sistemi tarafından güvenilir değildir çünkü bu adım gereklidir.</span><span class="sxs-lookup"><span data-stu-id="1425d-160">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="1425d-161">Bir istemci güvenilen kök sertifikayı kök erişim izni verilmiş bir sertifika zaten varsa — örneğin, Microsoft tarafından verilen sertifika — sunucu sertifikasında istemci sertifika deposunun doldurulması, bu adım gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="1425d-161">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="1425d-162">İstemci sertifikası oluşturuluyor.</span><span class="sxs-lookup"><span data-stu-id="1425d-162">Creating the client certificate.</span></span>

    <span data-ttu-id="1425d-163">Setup.bat toplu iş dosyasından aşağıdaki satırları kullanılacak istemci sertifikası oluşturun.</span><span class="sxs-lookup"><span data-stu-id="1425d-163">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="1425d-164">% USER_NAME % değişkeni, sunucu adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="1425d-164">The %USER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="1425d-165">Bu ad olduğundan, bu değer "test1" için ayarlanır `IAuthorizationPolicy` arar.</span><span class="sxs-lookup"><span data-stu-id="1425d-165">This value is set to "test1" because this is the name the `IAuthorizationPolicy` looks for.</span></span> <span data-ttu-id="1425d-166">USER_NAME % değerini değiştirirseniz, karşılık gelen değer değiştirmelisiniz `IAuthorizationPolicy.Evaluate` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1425d-166">If you change the value of %USER_NAME% you must change the corresponding value in the `IAuthorizationPolicy.Evaluate` method.</span></span>

    <span data-ttu-id="1425d-167">Sertifika CurrentUser depolama konumu altında (Kişisel) My deposunda depolanır.</span><span class="sxs-lookup"><span data-stu-id="1425d-167">The certificate is stored in My (Personal) store under the CurrentUser store location.</span></span>

    ```
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="1425d-168">İstemci sertifikası sunucusunun güvenilen sertifika depolama alanına yükleme.</span><span class="sxs-lookup"><span data-stu-id="1425d-168">Installing the client certificate into server's trusted certificate store.</span></span>

    <span data-ttu-id="1425d-169">Setup.bat toplu iş dosyasında aşağıdaki satırları istemci sertifikası güvenilir Kişiler deposuna kopyalar.</span><span class="sxs-lookup"><span data-stu-id="1425d-169">The following lines in the Setup.bat batch file copy the client certificate into the trusted people store.</span></span> <span data-ttu-id="1425d-170">Makecert.exe tarafından oluşturulan sertifikaları sunucu sistem tarafından örtük olarak güvenilmeyen olduğundan bu adım gereklidir.</span><span class="sxs-lookup"><span data-stu-id="1425d-170">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the server system.</span></span> <span data-ttu-id="1425d-171">Bir güvenilen kök sertifikayı kök erişim izni verilmiş bir sertifika zaten varsa — örneğin, Microsoft tarafından verilen sertifika — istemci sertifikası ile sunucu sertifika deposuna yerleştirmek, bu adım gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="1425d-171">If you already have a certificate that is rooted in a trusted root certificate—for example, a Microsoft issued certificate—this step of populating the server certificate store with the client certificate is not required.</span></span>

    ```
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="1425d-172">Ayarlama ve örneği oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="1425d-172">To set up and build the sample</span></span>

1. <span data-ttu-id="1425d-173">Çözümü derlemek için yönergeleri izleyin. [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1425d-173">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

2. <span data-ttu-id="1425d-174">Tek veya çoklu bilgisayar yapılandırmasında örneği çalıştırmak için aşağıdaki yönergeleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="1425d-174">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="1425d-175">Bu örnek için yapılandırmayı yeniden üretmek için Svcutil.exe kullanma, istemci kodu eşleştirilecek istemci yapılandırmasında uç noktası adını değiştirmek emin olun.</span><span class="sxs-lookup"><span data-stu-id="1425d-175">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="1425d-176">Örneği aynı bilgisayarda çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="1425d-176">To run the sample on the same computer</span></span>

1. <span data-ttu-id="1425d-177">Geliştirici komut istemi için Visual Studio'yu yönetici ayrıcalıklarıyla açıp çalıştırın *Setup.bat* örnek yükleme klasöründen.</span><span class="sxs-lookup"><span data-stu-id="1425d-177">Open Developer Command Prompt for Visual Studio with administrator privileges and run *Setup.bat* from the sample install folder.</span></span> <span data-ttu-id="1425d-178">Bu örneği çalıştırmak için gerekli olan tüm sertifikaları yükler.</span><span class="sxs-lookup"><span data-stu-id="1425d-178">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1425d-179">Setup.bat toplu iş dosyası, Visual Studio için geliştirici komut isteminden çalıştırılması için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="1425d-179">The Setup.bat batch file is designed to be run from Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="1425d-180">Visual Studio tarafından gereken yürütülebilir dosyaları içeren dizine işaret için geliştirici komut istemi içinde PATH ortam değişkenini ayarlama *Setup.bat* betiği.</span><span class="sxs-lookup"><span data-stu-id="1425d-180">The PATH environment variable set within Developer Command Prompt for Visual Studio points to the directory that contains executables required by the *Setup.bat* script.</span></span>

1. <span data-ttu-id="1425d-181">Gelen Service.exe başlatma *service\bin*.</span><span class="sxs-lookup"><span data-stu-id="1425d-181">Launch Service.exe from *service\bin*.</span></span>

1. <span data-ttu-id="1425d-182">Gelen Client.exe başlatma *\client\bin*.</span><span class="sxs-lookup"><span data-stu-id="1425d-182">Launch Client.exe from *\client\bin*.</span></span> <span data-ttu-id="1425d-183">İstemci etkinliği istemci konsol uygulamasında görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="1425d-183">Client activity is displayed on the client console application.</span></span>

<span data-ttu-id="1425d-184">İstemci ve hizmet iletişim kurabildiğini bilmiyorsanız bkz [WCF örnekleri için sorun giderme ipuçları](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="1425d-184">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="1425d-185">Bilgisayarlar arasında örneği çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="1425d-185">To run the sample across computers</span></span>

1. <span data-ttu-id="1425d-186">Hizmet bilgisayarda bir dizin oluşturun.</span><span class="sxs-lookup"><span data-stu-id="1425d-186">Create a directory on the service computer.</span></span>

2. <span data-ttu-id="1425d-187">Hizmet programı dosyaların kopyalanacağı *\service\bin* hizmeti bilgisayarında dizinine.</span><span class="sxs-lookup"><span data-stu-id="1425d-187">Copy the service program files from *\service\bin* to the directory on the service computer.</span></span> <span data-ttu-id="1425d-188">Ayrıca hizmet bilgisayara Setup.bat, Cleanup.bat GetComputerName.vbs ve ImportClientCert.bat dosyaları kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="1425d-188">Also copy the Setup.bat, Cleanup.bat, GetComputerName.vbs and ImportClientCert.bat files to the service computer.</span></span>

3. <span data-ttu-id="1425d-189">İstemci ikili dosyaları için istemci bilgisayarda bir dizin oluşturun.</span><span class="sxs-lookup"><span data-stu-id="1425d-189">Create a directory on the client computer for the client binaries.</span></span>

4. <span data-ttu-id="1425d-190">İstemci program dosyaları istemci bilgisayarda istemci dizinine kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="1425d-190">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="1425d-191">Aynı zamanda istemciye Setup.bat Cleanup.bat ve ImportServiceCert.bat dosyaları kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="1425d-191">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>

5. <span data-ttu-id="1425d-192">Sunucu üzerinde çalışan `setup.bat service` , yönetici ayrıcalıklarıyla açılan bir Visual Studio için geliştirici komut istemi.</span><span class="sxs-lookup"><span data-stu-id="1425d-192">On the server, run `setup.bat service` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="1425d-193">Çalışan `setup.bat` ile `service` bağımsız değişkeni bilgisayarın tam etki alanı adı ile bir hizmet sertifikası oluşturur ve hizmet sertifikası adlı bir dosyaya dışarı aktarır *Service.cer*.</span><span class="sxs-lookup"><span data-stu-id="1425d-193">Running `setup.bat` with the `service` argument creates a service certificate with the fully qualified domain name of the computer, and exports the service certificate to a file named *Service.cer*.</span></span>

6. <span data-ttu-id="1425d-194">Düzen *Service.exe.config* yeni sertifika adını yansıtacak şekilde (içinde `findValue` özniteliğini [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) tam etki alanı adıyla aynı olduğu bilgisayarı.</span><span class="sxs-lookup"><span data-stu-id="1425d-194">Edit *Service.exe.config* to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully qualified domain name of the computer.</span></span> <span data-ttu-id="1425d-195">Ayrıca değiştirmek **computername** içinde \<hizmet > /\<baseAddresses > localhost öğesine hizmet bilgisayarınızın tam adı.</span><span class="sxs-lookup"><span data-stu-id="1425d-195">Also change the **computername** in the \<service>/\<baseAddresses> element from localhost to the fully qualified name of your service computer.</span></span>

7. <span data-ttu-id="1425d-196">Kopyalama *Service.cer* hizmet dizininden istemci bilgisayarda dosya istemci dizine.</span><span class="sxs-lookup"><span data-stu-id="1425d-196">Copy the *Service.cer* file from the service directory to the client directory on the client computer.</span></span>

8. <span data-ttu-id="1425d-197">Bir istemcide çalışmasına `setup.bat client` , yönetici ayrıcalıklarıyla açılan bir Visual Studio için geliştirici komut istemi.</span><span class="sxs-lookup"><span data-stu-id="1425d-197">On the client, run `setup.bat client` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="1425d-198">Çalışan `setup.bat` ile `client` bağımsız değişkeni oluşturur adlı bir istemci sertifikası **test1** ve istemci sertifikasını adlı bir dosyaya dışarı aktarır *Client.cer*.</span><span class="sxs-lookup"><span data-stu-id="1425d-198">Running `setup.bat` with the `client` argument creates a client certificate named **test1** and exports the client certificate to a file named *Client.cer*.</span></span>

9. <span data-ttu-id="1425d-199">İçinde *Client.exe.config* dosyasını istemci bilgisayarda, hizmetinizin yeni adresiyle eşleşecek şekilde uç nokta adresi değiştirin.</span><span class="sxs-lookup"><span data-stu-id="1425d-199">In the *Client.exe.config* file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="1425d-200">Değiştirerek bunu **localhost** sunucusunun tam etki alanı adı ile.</span><span class="sxs-lookup"><span data-stu-id="1425d-200">Do this by replacing **localhost** with the fully qualified domain name of the server.</span></span>

10. <span data-ttu-id="1425d-201">Client.cer dosyayı istemci dizin sunucusundaki hizmet dizinine kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="1425d-201">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>

11. <span data-ttu-id="1425d-202">Bir istemcide çalışmasına *ImportServiceCert.bat* , yönetici ayrıcalıklarıyla açılan bir Visual Studio için geliştirici komut istemi.</span><span class="sxs-lookup"><span data-stu-id="1425d-202">On the client, run *ImportServiceCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="1425d-203">Bu hizmet sertifikası Service.cer dosyasına alır **CurrentUser - TrustedPeople** depolayın.</span><span class="sxs-lookup"><span data-stu-id="1425d-203">This imports the service certificate from the Service.cer file into the **CurrentUser - TrustedPeople** store.</span></span>

12. <span data-ttu-id="1425d-204">Sunucu üzerinde çalışan *ImportClientCert.bat* , yönetici ayrıcalıklarıyla açılan bir Visual Studio için geliştirici komut istemi.</span><span class="sxs-lookup"><span data-stu-id="1425d-204">On the server, run *ImportClientCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="1425d-205">Bu istemci sertifikasını Client.cer dosyasına alır **LocalMachine - TrustedPeople** depolayın.</span><span class="sxs-lookup"><span data-stu-id="1425d-205">This imports the client certificate from the Client.cer file into the **LocalMachine - TrustedPeople** store.</span></span>

13. <span data-ttu-id="1425d-206">Sunucu bilgisayarında, komut istemi penceresinden Service.exe başlatın.</span><span class="sxs-lookup"><span data-stu-id="1425d-206">On the server computer, launch Service.exe from the command prompt window.</span></span>

14. <span data-ttu-id="1425d-207">İstemci bilgisayarda bir komut istemi penceresinden Client.exe başlatın.</span><span class="sxs-lookup"><span data-stu-id="1425d-207">On the client computer, launch Client.exe from a command prompt window.</span></span>

    <span data-ttu-id="1425d-208">İstemci ve hizmet iletişim kurabildiğini bilmiyorsanız bkz [WCF örnekleri için sorun giderme ipuçları](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="1425d-208">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="clean-up-after-the-sample"></a><span data-ttu-id="1425d-209">Sonra örnek temizleme</span><span class="sxs-lookup"><span data-stu-id="1425d-209">Clean up after the sample</span></span>

<span data-ttu-id="1425d-210">Sonra örnek temizlemek için çalıştırma *Cleanup.bat* örnek çalıştırmayı tamamladığınızda samples klasöründe.</span><span class="sxs-lookup"><span data-stu-id="1425d-210">To clean up after the sample, run *Cleanup.bat* in the samples folder when you have finished running the sample.</span></span> <span data-ttu-id="1425d-211">Bu, sunucu ve istemci sertifikaları sertifika deposundan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="1425d-211">This removes the server and client certificates from the certificate store.</span></span>

> [!NOTE]
> <span data-ttu-id="1425d-212">Bu betik, bu örnek, bilgisayarlar arasında çalıştırırken bir istemcide hizmet sertifikaları kaldırmaz.</span><span class="sxs-lookup"><span data-stu-id="1425d-212">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="1425d-213">Bu bilgisayarlar arasında sertifikalar kullanmak, içinde CurrentUser - yüklü hizmet sertifikalarını temizlendiğinden emin WCF örnekleri çalıştırırsanız TrustedPeople depolayın.</span><span class="sxs-lookup"><span data-stu-id="1425d-213">If you have run WCF samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="1425d-214">Bunu yapmak için aşağıdaki komutu kullanın: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Örneğin: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="1425d-214">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
