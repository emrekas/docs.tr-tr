---
title: Güvenliği Genişletme
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 798a1d1cd21fd9a0bc21c6ccaa42c478379cc7a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511543"
---
# <a name="extending-security"></a><span data-ttu-id="44328-102">Güvenliği Genişletme</span><span class="sxs-lookup"><span data-stu-id="44328-102">Extending Security</span></span>
<span data-ttu-id="44328-103">Yeni talep türlerini ve özel belirteçler uyum sağlamak için Windows Communication Foundation (WCF) güvenlik altyapısı genişletebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="44328-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="44328-104">Bu bölümdeki konular, size nasıl yapıldığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="44328-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44328-105">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="44328-105">In This Section</span></span>  
 [<span data-ttu-id="44328-106">Güvenlik mimarisi</span><span class="sxs-lookup"><span data-stu-id="44328-106">Security Architecture</span></span>](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)  
 <span data-ttu-id="44328-107">WCF güvenlik sistem mimarisi size yol gösterir.</span><span class="sxs-lookup"><span data-stu-id="44328-107">Walks through the architecture of the WCF security system.</span></span>  
  
 [<span data-ttu-id="44328-108">Özel Kimlik Bilgileri ve Kimlik Bilgileri Doğrulaması</span><span class="sxs-lookup"><span data-stu-id="44328-108">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="44328-109">Özel kimlik doğrulama sırasında kimlik modeli nasıl kullanıldığını açıklar.</span><span class="sxs-lookup"><span data-stu-id="44328-109">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="44328-110">Özel Belirteçler</span><span class="sxs-lookup"><span data-stu-id="44328-110">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="44328-111">Bir güvenlik belirteci hizmeti (STS) öğesinden verilen belirteçler genellikle SAML belirteçlerini cihazlardır.</span><span class="sxs-lookup"><span data-stu-id="44328-111">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="44328-112">Bu konuda, özel bir belirteç türünün nasıl oluşturulacağı açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="44328-112">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="44328-113">Özel Yetkilendirme</span><span class="sxs-lookup"><span data-stu-id="44328-113">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="44328-114">Özel yetkilendirme uygulanacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="44328-114">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="44328-115">Bir Hizmetin Kimliğini Kimlik Doğrulama için Geçersiz Kılma</span><span class="sxs-lookup"><span data-stu-id="44328-115">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="44328-116">Kimlik doğrulaması için bir hizmetin kimliğini geçersiz kılmayı açıklar.</span><span class="sxs-lookup"><span data-stu-id="44328-116">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="44328-117">Nasıl yapılır: Özel İstemci Kimliği Doğrulayıcı oluşturma</span><span class="sxs-lookup"><span data-stu-id="44328-117">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="44328-118">Özel uç nokta kimlik doğrulama işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="44328-118">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="44328-119">Nasıl yapılır: İmzalama için ayrı X.509 sertifikaları kullanma ve şifreleme</span><span class="sxs-lookup"><span data-stu-id="44328-119">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="44328-120">İletiler genellikle imzalı ve tek bir sertifika ile şifrelenir.</span><span class="sxs-lookup"><span data-stu-id="44328-120">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="44328-121">Bu konu açıklar nasıl iki sertifika, gerekli olduğunda kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="44328-121">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="44328-122">Nasıl yapılır: Bir X.509 sertifikasının şifreleme sağlayıcısını değiştirme</span><span class="sxs-lookup"><span data-stu-id="44328-122">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="44328-123">Nasıl bir X.509 sertifikasının özel anahtar sağlamak için kullanılan şifreleme sağlayıcısını değiştirme ve Windows Communication Foundation (WCF) altyapısına sağlayıcı tümleştirmek nasıl açıklar.</span><span class="sxs-lookup"><span data-stu-id="44328-123">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="44328-124">Başvuru</span><span class="sxs-lookup"><span data-stu-id="44328-124">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="44328-125">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="44328-125">Related Sections</span></span>  
 [<span data-ttu-id="44328-126">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="44328-126">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="44328-127">Temel WCF Programlama</span><span class="sxs-lookup"><span data-stu-id="44328-127">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="44328-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="44328-128">See also</span></span>
- [<span data-ttu-id="44328-129">Güvenliğe Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="44328-129">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
