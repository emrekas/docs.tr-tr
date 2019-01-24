---
title: 'Azaltma: XML şema doğrulaması'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbeeecda3bd34f5eb651cb32246f8b56d5705002
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651012"
---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="5a786-102">Azaltma: XML şema doğrulaması</span><span class="sxs-lookup"><span data-stu-id="5a786-102">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="5a786-103">İçinde [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], XSD şema doğrulaması bir bileşik anahtarı kullanılır ve bir anahtar ise boş bir Benzersizlik kısıtlamasını ihlal algılar.</span><span class="sxs-lookup"><span data-stu-id="5a786-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="5a786-104">Etki</span><span class="sxs-lookup"><span data-stu-id="5a786-104">Impact</span></span>  
 <span data-ttu-id="5a786-105">Bu değişikliğin etkisini en az olmalıdır: şema belirtimine göre bir şema doğrulama hatası varsa beklenmektedir `xsd:unique` boş bir anahtara sahip bir bileşik anahtarı kullanarak ihlal etti.</span><span class="sxs-lookup"><span data-stu-id="5a786-105">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="5a786-106">Azaltma</span><span class="sxs-lookup"><span data-stu-id="5a786-106">Mitigation</span></span>  
 <span data-ttu-id="5a786-107">Boş bir anahtarı bir bileşik anahtarı varsa, şema doğrulama hatası olup olmadığını tespit yapılandırılabilir bir özelliktir:</span><span class="sxs-lookup"><span data-stu-id="5a786-107">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
-   <span data-ttu-id="5a786-108">Hedefleyen uygulamaları ile başlayan [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], şema doğrulama hatası olan algılama, varsayılan olarak etkindir; böylece şema doğrulama hatası algılanmadı ancak bunun dışında bırakmak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="5a786-108">Starting with the apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
-   <span data-ttu-id="5a786-109">Altında çalışan uygulamalar, [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ancak hedef [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] ve önceki sürümlerinde, varsayılan olarak bir şema doğrulama hatası algılanmadı; böylece şema doğrulama hatası algılandı ancak, bunu geri çevirmek mümkündür.</span><span class="sxs-lookup"><span data-stu-id="5a786-109">In apps that run under the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] but target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="5a786-110">Bu davranış kullanarak yapılandırılabilir <xref:System.AppContext> değerini tanımlamak için sınıf `System.Xml.IgnoreEmptyKeySequences` geçin.</span><span class="sxs-lookup"><span data-stu-id="5a786-110">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="5a786-111">Anahtarın varsayılan değeri olduğundan `false` (boş anahtar dizileri yok sayılır), hedefleyen uygulamaları [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] davranışı iptal anahtarın değeri ayarlamak için aşağıdaki kodu kullanarak iyileştirilmiş `true`:</span><span class="sxs-lookup"><span data-stu-id="5a786-111">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 <span data-ttu-id="5a786-112">Hedefleyen uygulamalar için [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] ve önceki sürümleri, anahtarın varsayılan değeri olduğundan `true` (boş anahtar dizileri yok sayılır), boş bir anahtara sahip bir bileşik anahtarı kullanarak bir şema doğrulama hatası üretin emin olmak mümkündür Aşağıdaki kod, anahtarın değeri ayarlamak için `false`.</span><span class="sxs-lookup"><span data-stu-id="5a786-112">For apps that target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5a786-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5a786-113">See also</span></span>
- [<span data-ttu-id="5a786-114">Yeniden Hedefleme Değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="5a786-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
