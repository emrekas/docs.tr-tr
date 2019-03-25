---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 3ff65e995f6a0d405eac3c1fc4a23917b117fdc0
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409178"
---
# <a name="ws2007federationhttpbinding"></a><span data-ttu-id="e5ee6-101">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e5ee6-101">\<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="e5ee6-102">Türetilen bir güvenli ve birlikte çalışabilen bağlama [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) ve birleşik güvenliği destekler.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-102">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) and supports federated security.</span></span>

<span data-ttu-id="e5ee6-103">\<sistemi. ServiceModel > \\</span><span class="sxs-lookup"><span data-stu-id="e5ee6-103">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="e5ee6-104">\<bağlamaları > \\</span><span class="sxs-lookup"><span data-stu-id="e5ee6-104">\<bindings>\\</span></span>
<span data-ttu-id="e5ee6-105">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e5ee6-105">\<ws2007FederationHttpBinding></span></span>

## <a name="syntax"></a><span data-ttu-id="e5ee6-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e5ee6-106">Syntax</span></span>

```xml
<ws2007FederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           privacyNoticeAt="Uri"
           privacyNoticeVersion="Integer"
           proxyAddress="Uri"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007FederationHttpBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e5ee6-107">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="e5ee6-107">Attributes and Elements</span></span>

<span data-ttu-id="e5ee6-108">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e5ee6-109">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="e5ee6-109">Attributes</span></span>

|<span data-ttu-id="e5ee6-110">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="e5ee6-110">Attribute</span></span>|<span data-ttu-id="e5ee6-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e5ee6-111">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="e5ee6-112">Yerel adresler için proxy sunucusunun atlanıp atlanmayacağını gösteren bir değer.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-112">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="e5ee6-113">Varsayılan, `false` değeridir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-113">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="e5ee6-114">A <xref:System.TimeSpan> bir kapatma işlemi tamamlamak sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e5ee6-115">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e5ee6-116">Varsayılan değer 00:01:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-116">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="e5ee6-117">URI ayrıştırmak için kullanılan HTTP ana bilgisayar adını karşılaştırma modunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-117">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="e5ee6-118">Bu öznitelik türünde <xref:System.ServiceModel.HostNameComparisonMode>, ana bilgisayar üzerinde URI'yi eşleştirirken hizmete erişmek için kullanılıp kullanılmayacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-118">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="e5ee6-119">Varsayılan değer <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, ana bilgisayar adı eşleşme yok sayar.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-119">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="e5ee6-120">Bu bağlama için en fazla arabellek havuzu boyutu.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-120">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="e5ee6-121">524.288 bayt (512 \* 1024) varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="e5ee6-122">Windows Communication Foundation (WCF) birçok bölümü arabellekler kullanın.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="e5ee6-123">Oluşturma ve arabellek kullanıldıkları her zaman yok etme pahalıdır ve çöp toplama arabellekler için da pahalıdır.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="e5ee6-124">Arabellek havuzu ile havuzdan bir arabelleğe almak, kullanmak ve tamamladıktan sonra havuza döndürün.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="e5ee6-125">Bu nedenle oluşturmak ve yok etme arabellekler yükü önlenmiş olur.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="e5ee6-126">Bu bağlama ile yapılandırılan bir kanalda alınabilecek üst bilgiler dahil bayt cinsinden en büyük ileti boyutu.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-126">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="e5ee6-127">Bu sınırı aşan bir ileti gönderen bir SOAP hatasını alır.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-127">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="e5ee6-128">Alıcı, iletiyi bırakır ve izleme günlüğüne etkinliğin bir giriş oluşturur.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="e5ee6-129">65536 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-129">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="e5ee6-130">İletisini kodlamak için kullanılan kodlayıcıya tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-130">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="e5ee6-131">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e5ee6-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e5ee6-132">-Metni: Bir metin ileti Kodlayıcı kullanın.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-132">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="e5ee6-133">-Mtom: İleti Aktarım kuruluş mekanizması 1.0 (MTOM) encoder'ı kullanın.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-133">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="e5ee6-134">Metin varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-134">The default is Text.</span></span><br /><br /> <span data-ttu-id="e5ee6-135">Bu öznitelik türünde <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-135">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="e5ee6-136">Bağlama yapılandırma adı.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-136">The configuration name of the binding.</span></span> <span data-ttu-id="e5ee6-137">Bağlama için bir tanımlayıcı olarak kullanıldığından, bu değer benzersiz olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-137">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="e5ee6-138">İle başlayarak [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bağlamalar ve davranışları için gerekli değildir bir ada sahip.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-138">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e5ee6-139">Varsayılan yapılandırma ve adsız bağlamaları ve davranışları hakkında daha fazla bilgi için bkz: [Basitleştirilmiş yapılandırma](../../../../../docs/framework/wcf/simplified-configuration.md) ve [WCF hizmetleri için Basitleştirilmiş yapılandırma](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e5ee6-139">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="e5ee6-140">A <xref:System.TimeSpan> tamamlamak açık işlem için sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e5ee6-141">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e5ee6-142">Varsayılan değer 00:01:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-142">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="e5ee6-143">Gizlilik bildirimini bulunduğu bir URI.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-143">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="e5ee6-144">Geçerli gizlilik bildirimini sürümü.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-144">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="e5ee6-145">HTTP proxy adresini belirten bir URI.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-145">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="e5ee6-146">Varsa `useDefaultWebProxy` olduğu `true`, bu ayar olmalıdır `null`.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-146">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="e5ee6-147">Varsayılan, `null` değeridir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-147">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="e5ee6-148">A <xref:System.TimeSpan> tamamlamak alma işlemi için sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e5ee6-149">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e5ee6-150">Varsayılan değer 00:10:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-150">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="e5ee6-151">A <xref:System.TimeSpan> tamamlamak bir gönderme işlemi için sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e5ee6-152">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e5ee6-153">Varsayılan değer 00:01:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-153">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="e5ee6-154">İletileri bağlamadaki yayma için kullanılacak kodlama karakter kümesini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-154">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="e5ee6-155">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e5ee6-155">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e5ee6-156">-   BigEndianUnicode: Unicode büyük Endian kodlaması.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-156">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="e5ee6-157">-Unicode: 16-bit kodlaması.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-157">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="e5ee6-158">-   UTF8: 8-bit kodlaması.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-158">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="e5ee6-159">UTF8 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-159">The default is UTF8.</span></span> <span data-ttu-id="e5ee6-160">Bu öznitelik türünde <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-160">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="e5ee6-161">WS işlem akışı sağlama bağlama destekleyip desteklemediğini belirten bir değeri.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-161">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="e5ee6-162">Varsayılan, `false` değeridir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-162">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="e5ee6-163">Sistemin otomatik yapılandırılan HTTP Ara sunucusu kullanılıp kullanılmayacağını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-163">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="e5ee6-164">Proxy adresi olmalıdır `null` (diğer bir deyişle, ayarlı değil) Bu öznitelik ise `true`.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-164">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="e5ee6-165">Varsayılan, `true` değeridir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-165">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e5ee6-166">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="e5ee6-166">Child Elements</span></span>

|<span data-ttu-id="e5ee6-167">Öğe</span><span class="sxs-lookup"><span data-stu-id="e5ee6-167">Element</span></span>|<span data-ttu-id="e5ee6-168">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e5ee6-168">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e5ee6-169">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="e5ee6-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="e5ee6-170">İleti için güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-170">Defines the security settings for the message.</span></span> <span data-ttu-id="e5ee6-171">Bu öğe türünde <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-171">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="e5ee6-172">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e5ee6-172">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="e5ee6-173">Bu bağlama ile yapılandırılan bir bitiş noktası tarafından işlenen SOAP iletilerinin karmaşıklığını kısıtlamalar tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-173">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e5ee6-174">Bu öğe türünde <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-174">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="e5ee6-175">[\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e5ee6-175">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="e5ee6-176">Güvenilir oturumlar kanal uç noktaları arasında kurulan olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-176">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e5ee6-177">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="e5ee6-177">Parent Elements</span></span>

|<span data-ttu-id="e5ee6-178">Öğe</span><span class="sxs-lookup"><span data-stu-id="e5ee6-178">Element</span></span>|<span data-ttu-id="e5ee6-179">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e5ee6-179">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e5ee6-180">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="e5ee6-180">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="e5ee6-181">Bu öğe, standart ve özel bağlamalar koleksiyonunu tutar.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-181">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e5ee6-182">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e5ee6-182">Remarks</span></span>

<span data-ttu-id="e5ee6-183">Federasyon kimlikleri birden fazla kuruluşlar veya kimlik doğrulama ve yetkilendirme için güven etki alanları arasında paylaşmak için yeteneğidir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-183">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="e5ee6-184">Bir güven etki alanı kimlik gösterimden diğerine eşlemek için WS-Trust protokolü kullanır.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-184">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="e5ee6-185">Karma mod güvenliği yanı sıra SOAP Güvenliği Federasyon HTTP bağlama destekler, ancak aktarım güvenliği desteklemez.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-185">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="e5ee6-186">Bu bağlama ile yapılandırılan hizmetler, HTTP aktarımı kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-186">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="e5ee6-187">Daha fazla bilgi için [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="e5ee6-187">For more information, see [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="e5ee6-188">Örnek</span><span class="sxs-lookup"><span data-stu-id="e5ee6-188">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007FederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </ws2007FederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e5ee6-189">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e5ee6-189">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [<span data-ttu-id="e5ee6-190">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e5ee6-190">\<wsFederationHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)
- [<span data-ttu-id="e5ee6-191">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="e5ee6-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e5ee6-192">Sistem Tarafından Sağlanan Bağlamaları Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e5ee6-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e5ee6-193">Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma</span><span class="sxs-lookup"><span data-stu-id="e5ee6-193">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e5ee6-194">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="e5ee6-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
