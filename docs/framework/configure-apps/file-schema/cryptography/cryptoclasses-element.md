---
title: '&lt;cryptoClasses&gt; öğesi'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 85e47830649b0088d1e1645d73c4fb924ba5591f
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083333"
---
# <a name="ltcryptoclassesgt-element"></a><span data-ttu-id="2ce34-102">&lt;cryptoClasses&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="2ce34-102">&lt;cryptoClasses&gt; Element</span></span>
<span data-ttu-id="2ce34-103">Bir eşleme için bir kolay ad şifreleme sınıflarını listesini içeren [ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="2ce34-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="2ce34-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="2ce34-104">\<configuration></span></span>  
<span data-ttu-id="2ce34-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="2ce34-105">\<mscorlib></span></span>  
<span data-ttu-id="2ce34-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="2ce34-106">\<cryptographySettings></span></span>  
<span data-ttu-id="2ce34-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="2ce34-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="2ce34-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="2ce34-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce34-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="2ce34-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ce34-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="2ce34-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2ce34-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="2ce34-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ce34-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="2ce34-112">Attributes</span></span>  
 <span data-ttu-id="2ce34-113">Yok.</span><span class="sxs-lookup"><span data-stu-id="2ce34-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2ce34-114">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="2ce34-114">Child Elements</span></span>  
  
|<span data-ttu-id="2ce34-115">Öğe</span><span class="sxs-lookup"><span data-stu-id="2ce34-115">Element</span></span>|<span data-ttu-id="2ce34-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2ce34-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ce34-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="2ce34-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="2ce34-118">İçin bir kolay ad eşlemesi var. bir şifreleme sınıfına içeren  **\<nameEntry >** öğesi.</span><span class="sxs-lookup"><span data-stu-id="2ce34-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ce34-119">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="2ce34-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2ce34-120">Öğe</span><span class="sxs-lookup"><span data-stu-id="2ce34-120">Element</span></span>|<span data-ttu-id="2ce34-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2ce34-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2ce34-122">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="2ce34-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="2ce34-123">Şifreleme ayarlarını içerir.</span><span class="sxs-lookup"><span data-stu-id="2ce34-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="2ce34-124">Sınıf için kolay adlar eşlemeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="2ce34-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="2ce34-125">İçeren `cryptographySettings` öğesi.</span><span class="sxs-lookup"><span data-stu-id="2ce34-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2ce34-126">Örnek</span><span class="sxs-lookup"><span data-stu-id="2ce34-126">Example</span></span>  
 <span data-ttu-id="2ce34-127">Aşağıdaki örnek nasıl kullanıldığını gösterir  **\<cryptoClass >** bir şifreleme sınıfına başvurmak için ve çalışma zamanı yapılandırma öğesi.</span><span class="sxs-lookup"><span data-stu-id="2ce34-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="2ce34-128">Ardından "RSA" dize iletebileceğiniz <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> yöntemini <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> döndürülecek yöntemi bir `MyCryptoRSAClass` nesne.</span><span class="sxs-lookup"><span data-stu-id="2ce34-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ce34-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2ce34-129">See also</span></span>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="2ce34-130">Yapılandırma Dosyası Şeması</span><span class="sxs-lookup"><span data-stu-id="2ce34-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="2ce34-131">Şifreleme Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="2ce34-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="2ce34-132">Şifreleme Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="2ce34-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="2ce34-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="2ce34-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="2ce34-134">Şifreleme Sınıflarını Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="2ce34-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
