---
title: <remove> ConnectionManagement (ağ ayarları) için
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: d9c584fb2faa971e7ce1ca287a94c8c6129820fd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158866"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="3e4d5-102">\<kaldırma > connectionManagement (ağ ayarları) için</span><span class="sxs-lookup"><span data-stu-id="3e4d5-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="3e4d5-103">Bir IP adresi veya DNS adı bağlantı yönetimi listesinden kaldırır.</span><span class="sxs-lookup"><span data-stu-id="3e4d5-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="3e4d5-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="3e4d5-104">\<configuration></span></span>  
<span data-ttu-id="3e4d5-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3e4d5-105">\<system.net></span></span>  
<span data-ttu-id="3e4d5-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="3e4d5-106">\<connectionManagement></span></span>  
<span data-ttu-id="3e4d5-107">\<kaldırma ></span><span class="sxs-lookup"><span data-stu-id="3e4d5-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e4d5-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3e4d5-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e4d5-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="3e4d5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3e4d5-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="3e4d5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e4d5-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="3e4d5-111">Attributes</span></span>  
  
|**<span data-ttu-id="3e4d5-112">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="3e4d5-112">Attribute</span></span>**|**<span data-ttu-id="3e4d5-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3e4d5-113">Description</span></span>**|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="3e4d5-114">Bir IP adresi veya DNS adı.</span><span class="sxs-lookup"><span data-stu-id="3e4d5-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e4d5-115">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="3e4d5-115">Child Elements</span></span>  
 <span data-ttu-id="3e4d5-116">Yok.</span><span class="sxs-lookup"><span data-stu-id="3e4d5-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e4d5-117">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="3e4d5-117">Parent Elements</span></span>  
  
|**<span data-ttu-id="3e4d5-118">Öğe</span><span class="sxs-lookup"><span data-stu-id="3e4d5-118">Element</span></span>**|**<span data-ttu-id="3e4d5-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3e4d5-119">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="3e4d5-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="3e4d5-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="3e4d5-121">Bir ağ konak bağlantı maksimum sayısını belirtir.</span><span class="sxs-lookup"><span data-stu-id="3e4d5-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e4d5-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3e4d5-122">Remarks</span></span>  
 <span data-ttu-id="3e4d5-123">`remove` Bağlantı yönetim listesi girişi için belirtilen server öğeyi kaldırır.</span><span class="sxs-lookup"><span data-stu-id="3e4d5-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="3e4d5-124">Değerini `address` özniteliği geçerli bir IP adresi veya ana bilgisayar adı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="3e4d5-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3e4d5-125">Yapılandırma Dosyaları</span><span class="sxs-lookup"><span data-stu-id="3e4d5-125">Configuration Files</span></span>  
 <span data-ttu-id="3e4d5-126">Bu öğe, uygulama yapılandırma dosyası veya makine yapılandırma dosyası (Machine.config) kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3e4d5-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e4d5-127">Örnek</span><span class="sxs-lookup"><span data-stu-id="3e4d5-127">Example</span></span>  
 <span data-ttu-id="3e4d5-128">Aşağıdaki örnek, tüm sunucu için bağlantı yönetim Liste girişlerini kaldırır `www.adventure-works.com` ve ardından sunucu için dört bağlantıları kullanmak için bir uygulamayı yapılandırır `www.contoso.com` ve diğer tüm sunucular iki bağlantı.</span><span class="sxs-lookup"><span data-stu-id="3e4d5-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e4d5-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3e4d5-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="3e4d5-130">Ağ Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="3e4d5-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
