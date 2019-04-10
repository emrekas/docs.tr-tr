---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 1c33e1ce710fea3b1698a6dab47a199e40388f5a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217893"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="fb85a-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="fb85a-102">PeerSecuritySettings</span></span>
<span data-ttu-id="fb85a-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="fb85a-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb85a-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fb85a-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fb85a-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="fb85a-105">Methods</span></span>  
 <span data-ttu-id="fb85a-106">PeerSecuritySettings sınıf herhangi bir yöntemi tanımlamaz.</span><span class="sxs-lookup"><span data-stu-id="fb85a-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fb85a-107">Özellikler</span><span class="sxs-lookup"><span data-stu-id="fb85a-107">Properties</span></span>  
 <span data-ttu-id="fb85a-108">PeerSecuritySettings sınıfı aşağıdaki özelliklere sahiptir:</span><span class="sxs-lookup"><span data-stu-id="fb85a-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="fb85a-109">Mod</span><span class="sxs-lookup"><span data-stu-id="fb85a-109">Mode</span></span>  
 <span data-ttu-id="fb85a-110">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="fb85a-110">Data type: string</span></span>  
  
 <span data-ttu-id="fb85a-111">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="fb85a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb85a-112">İleti düzeyi olup olmadığını ve aktarım düzeyi güvenlik bağlama ile yapılandırılan bir uç nokta tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="fb85a-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="fb85a-113">Taşıma</span><span class="sxs-lookup"><span data-stu-id="fb85a-113">Transport</span></span>  
 <span data-ttu-id="fb85a-114">Veri türü: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="fb85a-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="fb85a-115">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="fb85a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb85a-116">Taşıma güvenliği ayarları.</span><span class="sxs-lookup"><span data-stu-id="fb85a-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb85a-117">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="fb85a-117">Requirements</span></span>  
  
|<span data-ttu-id="fb85a-118">MOF</span><span class="sxs-lookup"><span data-stu-id="fb85a-118">MOF</span></span>|<span data-ttu-id="fb85a-119">Bildirilmiş Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fb85a-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fb85a-120">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="fb85a-120">Namespace</span></span>|<span data-ttu-id="fb85a-121">İçinde tanımlı root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fb85a-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb85a-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fb85a-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
