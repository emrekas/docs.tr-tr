---
title: Başlangıç Ayarları Şeması
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 12f91a1c74e85cbce0c8f641f202a181beb7412c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728914"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="50600-102">Başlangıç Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="50600-102">Startup settings schema</span></span>

<span data-ttu-id="50600-103">Başlangıç ayarları, uygulamanın çalışması gereken ortak dil çalışma zamanı sürümünü belirtin.</span><span class="sxs-lookup"><span data-stu-id="50600-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="50600-104">Öğe</span><span class="sxs-lookup"><span data-stu-id="50600-104">Element</span></span>|<span data-ttu-id="50600-105">Açıklama</span><span class="sxs-lookup"><span data-stu-id="50600-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50600-106">\<requiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="50600-106">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="50600-107">Uygulama yalnızca sürüm 1.0 ortak dil çalışma zamanının desteklediğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="50600-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="50600-108">Çalışma zamanı sürüm 1.1 ile oluşturulan uygulamaların kullanması gereken  **\<supportedRuntime >** öğesi.</span><span class="sxs-lookup"><span data-stu-id="50600-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="50600-109">\<supportedRuntime ></span><span class="sxs-lookup"><span data-stu-id="50600-109">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="50600-110">Uygulamanın hangi ortak dil çalışma zamanı sürümünü desteklediğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="50600-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="50600-111">\<Başlangıç ></span><span class="sxs-lookup"><span data-stu-id="50600-111">\<startup></span></span>](startup-element.md)|<span data-ttu-id="50600-112">İçeren  **\<requiredRuntime >** ve  **\<supportedRuntime >** öğeleri.</span><span class="sxs-lookup"><span data-stu-id="50600-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50600-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="50600-113">See also</span></span>

- [<span data-ttu-id="50600-114">Yapılandırma Dosyası Şeması</span><span class="sxs-lookup"><span data-stu-id="50600-114">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="50600-115">Nasıl yapılır: Bir uygulamayı .NET Framework 4 veya sonraki sürümler destekleyecek şekilde yapılandırma</span><span class="sxs-lookup"><span data-stu-id="50600-115">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
