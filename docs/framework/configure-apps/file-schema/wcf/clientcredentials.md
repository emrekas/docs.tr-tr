---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: c3e756f49b7054d6553eb6c3f1850f0fbce14943
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926125"
---
# <a name="clientcredentials"></a><span data-ttu-id="869d5-101">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="869d5-101">\<clientCredentials></span></span>
<span data-ttu-id="869d5-102">Bir hizmette istemcinin kimliğini doğrulamak için kullanılan kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="869d5-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="869d5-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="869d5-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="869d5-104">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="869d5-104">\<behaviors></span></span>  
<span data-ttu-id="869d5-105">\<Endpointdavranışlar ></span><span class="sxs-lookup"><span data-stu-id="869d5-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="869d5-106">\<davranış ></span><span class="sxs-lookup"><span data-stu-id="869d5-106">\<behavior></span></span>  
<span data-ttu-id="869d5-107">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="869d5-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="869d5-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="869d5-108">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="869d5-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="869d5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="869d5-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="869d5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="869d5-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="869d5-111">Attributes</span></span>  
  
|<span data-ttu-id="869d5-112">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="869d5-112">Attribute</span></span>|<span data-ttu-id="869d5-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="869d5-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="869d5-114">Etkileşimli bir kullanıcının çalışma zamanında istemci kimlik bilgilerini seçmeye dahil edilip edilmeyeceğini belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="869d5-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="869d5-115">Varsayılan değer `true` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="869d5-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="869d5-116">Bu yapılandırma öğesinin türünü belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="869d5-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="869d5-117">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="869d5-117">Child Elements</span></span>  
  
|<span data-ttu-id="869d5-118">Öğe</span><span class="sxs-lookup"><span data-stu-id="869d5-118">Element</span></span>|<span data-ttu-id="869d5-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="869d5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="869d5-120">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="869d5-120">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="869d5-121">Hizmetin istemcinin kimliğini doğrulamak için kullanılan sertifikayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="869d5-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="869d5-122">Bu öğe türündedir <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="869d5-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="869d5-123">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="869d5-123">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="869d5-124">İstemci kimliğini hizmette doğrulamak için kullanılan bir Özet belirtir.</span><span class="sxs-lookup"><span data-stu-id="869d5-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="869d5-125">Bu öğe türündedir <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="869d5-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="869d5-126">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="869d5-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="869d5-127">İstemcinin kimliğini bir güvenli belirteç hizmeti 'ne (STS) doğrulamak için kullanılan özel bir belirteç türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="869d5-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="869d5-128">Bu öğe türündedir <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="869d5-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="869d5-129">\<eş ></span><span class="sxs-lookup"><span data-stu-id="869d5-129">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="869d5-130">Geçerli bir eş kimlik bilgisi belirtir.</span><span class="sxs-lookup"><span data-stu-id="869d5-130">Specifies a current peer credential.</span></span> <span data-ttu-id="869d5-131">Bu öğe türündedir <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="869d5-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="869d5-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="869d5-132">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="869d5-133">İstemciye hizmetin kimliğini doğrulamak için kullanılan sertifikayı belirtir ve sertifika seçeneklerini ayarlamak için bir yapı sağlar.</span><span class="sxs-lookup"><span data-stu-id="869d5-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="869d5-134">Bu sertifika, hizmetten istemciye bant dışı verilmelidir.</span><span class="sxs-lookup"><span data-stu-id="869d5-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="869d5-135">Bu öğe türündedir <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="869d5-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="869d5-136">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="869d5-136">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="869d5-137">Windows kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="869d5-137">Specifies a Windows credential.</span></span> <span data-ttu-id="869d5-138">Varsayılan değer, geçerli iş parçacığının kimlik bilgileridir.</span><span class="sxs-lookup"><span data-stu-id="869d5-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="869d5-139">Bu öğe türündedir <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="869d5-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="869d5-140">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="869d5-140">Parent Elements</span></span>  
  
|<span data-ttu-id="869d5-141">Öğe</span><span class="sxs-lookup"><span data-stu-id="869d5-141">Element</span></span>|<span data-ttu-id="869d5-142">Açıklama</span><span class="sxs-lookup"><span data-stu-id="869d5-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="869d5-143">\<davranış ></span><span class="sxs-lookup"><span data-stu-id="869d5-143">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="869d5-144">Bir uç nokta davranışı belirtir.</span><span class="sxs-lookup"><span data-stu-id="869d5-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="869d5-145">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="869d5-145">Remarks</span></span>  
 <span data-ttu-id="869d5-146">İstemci kimlik bilgileri, karşılıklı kimlik doğrulamanın gerekli olduğu durumlarda istemcinin kimliğini doğrulamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="869d5-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="869d5-147">Bu yapılandırma bölümü, istemcinin hizmet sertifikası ile iletileri güvenli hale getirmek zorunda olduğu senaryolara yönelik hizmet sertifikalarını belirtmek için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="869d5-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="869d5-148">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="869d5-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="869d5-149">Güvenlik Davranışları</span><span class="sxs-lookup"><span data-stu-id="869d5-149">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="869d5-150">İstemcileri Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="869d5-150">Securing Clients</span></span>](../../../wcf/securing-clients.md)
