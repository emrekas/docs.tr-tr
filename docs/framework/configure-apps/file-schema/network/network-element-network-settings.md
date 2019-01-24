---
title: '&lt;Ağ&gt; öğesi (ağ ayarları)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: 7270cee07bea50aa50dc191ac957132e2794c0bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599271"
---
# <a name="ltnetworkgt-element-network-settings"></a><span data-ttu-id="ce0dc-102">&lt;Ağ&gt; öğesi (ağ ayarları)</span><span class="sxs-lookup"><span data-stu-id="ce0dc-102">&lt;network&gt; Element (Network Settings)</span></span>
<span data-ttu-id="ce0dc-103">Harici bir Basit Posta Aktarım Protokolü (SMTP) sunucusu ağ seçeneklerini yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="ce0dc-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="ce0dc-104">\<configuration></span></span>  
<span data-ttu-id="ce0dc-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ce0dc-105">\<system.net></span></span>  
<span data-ttu-id="ce0dc-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="ce0dc-106">\<mailSettings></span></span>  
<span data-ttu-id="ce0dc-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="ce0dc-107">\<smtp></span></span>  
<span data-ttu-id="ce0dc-108">\<Ağ ></span><span class="sxs-lookup"><span data-stu-id="ce0dc-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce0dc-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ce0dc-109">Syntax</span></span>  
  
```xml  
<network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce0dc-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="ce0dc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ce0dc-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce0dc-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="ce0dc-112">Attributes</span></span>  
  
|<span data-ttu-id="ce0dc-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="ce0dc-113">Attribute</span></span>|<span data-ttu-id="ce0dc-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ce0dc-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="ce0dc-115">İlk SMTP protokolünü istekte SMTP posta sunucusuna bağlanmak için kullanılacak istemci etki alanı adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="ce0dc-116">Varsayılan değer isteği yerel bilgisayar localhost adıdır.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="ce0dc-117">SMTP işlemleri için SMTP posta sunucusuna erişmek için varsayılan kullanıcı kimlik bilgilerinin kullanılıp kullanılmayacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="ce0dc-118">Varsayılan değer `false` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="ce0dc-119">Bir SMTP posta sunucusuna erişmek için SSL kullanılıp kullanılmayacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="ce0dc-120">Varsayılan değer `false` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="ce0dc-121">SMTP işlemleri için kullanılacak SMTP posta sunucusu konak adı belirtir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="ce0dc-122">Bu öznitelik varsayılan değeri yok.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="ce0dc-123">SMTP posta sunucusuna kimlik doğrulaması için kullanılacak parolayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="ce0dc-124">Bu öznitelik varsayılan değeri yok.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="ce0dc-125">SMTP posta sunucusuna bağlanmak için kullanılacak bağlantı noktası numarasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="ce0dc-126">Varsayılan değer 25'tir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="ce0dc-127">SMTP işlemleri için genişletilmiş koruma kullanarak kimlik doğrulaması için kullanılacak hizmet sağlayıcı adı (SPN) belirtir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="ce0dc-128">Bu öznitelik varsayılan değeri yok.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="ce0dc-129">SMTP posta sunucusuna kimlik doğrulaması için kullanılacak kullanıcı adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="ce0dc-130">Bu öznitelik varsayılan değeri yok.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce0dc-131">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="ce0dc-131">Child Elements</span></span>  
 <span data-ttu-id="ce0dc-132">Yok.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce0dc-133">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="ce0dc-133">Parent Elements</span></span>  
  
|<span data-ttu-id="ce0dc-134">Öğe</span><span class="sxs-lookup"><span data-stu-id="ce0dc-134">Element</span></span>|<span data-ttu-id="ce0dc-135">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ce0dc-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce0dc-136">\<SMTP > öğesi (ağ ayarları)</span><span class="sxs-lookup"><span data-stu-id="ce0dc-136">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="ce0dc-137">Basit Posta Aktarım Protokolü (SMTP) posta gönderme seçeneklerini yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce0dc-138">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ce0dc-138">Remarks</span></span>  
 <span data-ttu-id="ce0dc-139">Bazı SMTP sunucuları, kendiniz kullanmadan önce sunucuya kimlik doğrulaması gerektirir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="ce0dc-140">İsterseniz, konaktaki varsayılan ağ kimlik bilgilerini kullanarak kimlik doğrulaması ayarlayın `defaultCredentials` özniteliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="ce0dc-141"><xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> Özelliği, geçerli değerini almak için kullanılabilir `defaultCredentials` geçerli yapılandırma dosyalarından özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="ce0dc-142">Temel kimlik doğrulaması (bir kullanıcı adı ve parola) kendiniz SMTP sunucusuna kimlik doğrulaması için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="ce0dc-143">Bu seçeneği kullanmak için geçerli bir kullanıcı adı ve belirtilen SMTP sunucusu için parola belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce0dc-144">Temel kimlik doğrulaması `userName` ve `password` sunucuya şifrelenmemiş değerleri.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="ce0dc-145">Herkes ağ trafiğini izleme, kimlik bilgilerinizi görüntüleyin ve sunucuya bağlanmak için bunları kullanın.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="ce0dc-146">Kerberos ya da NT LAN Manager (NTLM) gibi daha güvenli bir kimlik doğrulama mekanizması kullanmayı düşünmeniz gerekir Varsa `defaultCredentials` olduğu `true`, Kerberos veya NTLM kullanılacak sunucunun bu protokolleri destekliyorsa.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="ce0dc-147">Temel kimlik doğrulaması ve varsayılan ağ kimlik bilgileri seçenekler birbirini dışlıyor; ayarlarsanız `defaultCredentials` için `true` ve bir kullanıcı adı ve parola belirtin, varsayılan ağ kimlik bilgisi kullanılır ve temel kimlik doğrulama verilerini göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="ce0dc-148">Belirtirseniz, temel kimlik doğrulaması için bir `userName`, de belirtmeniz bir `password` kimlik doğrulaması için kendinize e-posta sunucusu.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="ce0dc-149"><xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Özelliği, geçerli değerini almak için kullanılabilir `userName` geçerli yapılandırma dosyalarından özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="ce0dc-150"><xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> Özelliği, geçerli değerini almak için kullanılabilir `password` geçerli yapılandırma dosyalarından özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="ce0dc-151">A `password` özniteliği değil normalde girilmesi yapılandırma dosyalarında güvenlik nedenleriyle.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="ce0dc-152">`clientDomain` İlk SMTP protokolünü isteğinde bir SMTP sunucusu için kullanılan istemci etki alanı adı özniteliği değiştirir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="ce0dc-153">`clientDomain` Özniteliği, varsayılan olarak kullanılan localhost adı yerine tam etki alanı adı yerel makine ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="ce0dc-154">Bu, SMTP protokolü standartları ile daha yüksek uyumluluk sağlar.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="ce0dc-155">Varsayılan değer isteği yerel bilgisayar localhost adıdır.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="ce0dc-156"><xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> Özelliği, geçerli değerini almak için kullanılabilir `clientDomain` geçerli yapılandırma dosyalarından özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="ce0dc-157">`targetName` Özniteliği, genişletilmiş koruma kullanarak kimlik doğrulaması için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="ce0dc-158">Varsayılan değer biçimindedir "SMTPSVC /\<konak >" nerede \<konak > SMTP posta sunucusunun adıdır.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="ce0dc-159"><xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> Özelliği, geçerli değerini almak için kullanılabilir `targetName` geçerli yapılandırma dosyalarından özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="ce0dc-160">`enableSsl` Özniteliği, bir SMTP posta sunucusuna erişmek için SSL kullanılıp kullanılmayacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="ce0dc-161"><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Sınıfı yalnızca destekler SMTP hizmeti uzantısı için SMTP güvenli Aktarım Katmanı Güvenliği RFC 3207 içinde tanımlanan.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="ce0dc-162">Bu modda, şifrelenmemiş bir kanal SMTP oturumunu başlar ve daha STARTTLS komutu sunucusuna SSL kullanarak güvenli iletişim için geçiş yapmak için istemci tarafından verilir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="ce0dc-163">RFC 3207 yayımlanan Internet Engineering Task Force (IETF) tarafından daha fazla bilgi için bkz.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="ce0dc-164">Burada bir SSL Önden komutları gönderilen herhangi bir protokol önce oturumun bir alternatif bağlantı yöntemidir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="ce0dc-165">Bu bağlantı yöntemi SMTPS adlandırılır ve varsayılan olarak bağlantı noktası 465 kullanır.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="ce0dc-166">SSL kullanarak bu alternatif bağlantı yöntemini şu anda desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="ce0dc-167"><xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> Özelliği, geçerli değerini almak için kullanılabilir `enableSsl` geçerli yapılandırma dosyalarından özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce0dc-168">Örnek</span><span class="sxs-lookup"><span data-stu-id="ce0dc-168">Example</span></span>  
 <span data-ttu-id="ce0dc-169">Aşağıdaki örnek, varsayılan ağ kimlik bilgilerini kullanarak e-posta göndermek için uygun SMTP parametrelerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce0dc-170">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ce0dc-170">See also</span></span>
- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="ce0dc-171">Ağ Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="ce0dc-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
