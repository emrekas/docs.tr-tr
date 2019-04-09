---
title: <add> , <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 1c6764b37b2aa5349b8ccf63e6b7c2bc580b69b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186608"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="c52ad-102">\<Ekle >, \<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="c52ad-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="c52ad-103">WCF hizmetleri barındırır ve Paylaşım Hizmeti bağlantı erişim izni verilen işlemleri için bir kullanıcı hesabı belirtir.</span><span class="sxs-lookup"><span data-stu-id="c52ad-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="c52ad-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="c52ad-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c52ad-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c52ad-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c52ad-106">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="c52ad-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c52ad-107">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="c52ad-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c52ad-108">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="c52ad-108">Attributes</span></span>  
  
|<span data-ttu-id="c52ad-109">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="c52ad-109">Attribute</span></span>|<span data-ttu-id="c52ad-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c52ad-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c52ad-111">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="c52ad-111">securityIdentifier</span></span>|<span data-ttu-id="c52ad-112">Bir kullanıcı hesabı tanımlamak için kullanılan benzersiz bir tanımlayıcı belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="c52ad-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="c52ad-113">Varsayılan LocalSystem, Yöneticiler, NS, LS ve ııs_usrs değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="c52ad-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c52ad-114">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="c52ad-114">Child Elements</span></span>  
 <span data-ttu-id="c52ad-115">Yok.</span><span class="sxs-lookup"><span data-stu-id="c52ad-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c52ad-116">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="c52ad-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c52ad-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="c52ad-117">Element</span></span>|<span data-ttu-id="c52ad-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c52ad-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c52ad-119">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="c52ad-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="c52ad-120">Bir koleksiyon içeren yapılandırma öğelerinin bir `securityIdentifier` barındıran WCF hizmetleri ve Paylaşım Hizmeti bağlantı erişim izni verilen işlemleri için kullanıcı hesabı belirtmek için özniteliği.</span><span class="sxs-lookup"><span data-stu-id="c52ad-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c52ad-121">Örnek</span><span class="sxs-lookup"><span data-stu-id="c52ad-121">Example</span></span>  
 <span data-ttu-id="c52ad-122">Aşağıdaki yapılandırma örnek kullanıcı hesapları için beş varsayılan tanımlayıcıları, bu koleksiyona ekler.</span><span class="sxs-lookup"><span data-stu-id="c52ad-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="c52ad-123">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c52ad-123">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
