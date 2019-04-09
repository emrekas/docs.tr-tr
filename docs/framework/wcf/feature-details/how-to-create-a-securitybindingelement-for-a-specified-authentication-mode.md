---
title: 'Nasıl yapılır: Belirtilen Bir Kimlik Doğrulama Modu için SecurityBindingElement Oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
ms.openlocfilehash: e35df9a5dacc5f281af48cec292a09b291312119
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124520"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="3bf59-102">Nasıl yapılır: Belirtilen Bir Kimlik Doğrulama Modu için SecurityBindingElement Oluşturma</span><span class="sxs-lookup"><span data-stu-id="3bf59-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>
<span data-ttu-id="3bf59-103">Windows Communication Foundation (WCF) tarafından istemcileri ve Hizmetleri birbirine kimlik doğrulaması birkaç modu sağlar.</span><span class="sxs-lookup"><span data-stu-id="3bf59-103">Windows Communication Foundation (WCF) provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="3bf59-104">Güvenlik bağlama öğeleri bu kimlik doğrulama modları için statik yöntemler kullanarak oluşturabileceğiniz <xref:System.ServiceModel.Channels.SecurityBindingElement> sınıfı veya aşağıdaki örnekte gösterildiği gibi yapılandırma yoluyla.</span><span class="sxs-lookup"><span data-stu-id="3bf59-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="3bf59-105">18 kimlik doğrulama modları hakkında daha fazla bilgi için bkz. [SecurityBindingElement kimlik doğrulama modları](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="3bf59-105">For more information about the 18 authentication modes, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bf59-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="3bf59-106">Example</span></span>  
 <span data-ttu-id="3bf59-107">Aşağıdaki kod örneği, çeşitli kimlik doğrulama modları için bağlamaları oluşturmak için yöntemleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="3bf59-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bf59-108">Bir kez örneğini <xref:System.ServiceModel.Channels.SecurityBindingElement> nesnesi oluşturulur, çeşitli özellikleri gibi sabit <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> ve <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="3bf59-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="3bf59-109">Çağırma `set` gibi özellikleri üzerinde bunları değiştirmez.</span><span class="sxs-lookup"><span data-stu-id="3bf59-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3bf59-110">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3bf59-110">See also</span></span>

- [<span data-ttu-id="3bf59-111">SecurityBindingElement Kimlik Doğrulama Modları</span><span class="sxs-lookup"><span data-stu-id="3bf59-111">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)
- [<span data-ttu-id="3bf59-112">Nasıl yapılır: SecurityBindingElement Kullanarak Özel Bağlama Oluşturma</span><span class="sxs-lookup"><span data-stu-id="3bf59-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
