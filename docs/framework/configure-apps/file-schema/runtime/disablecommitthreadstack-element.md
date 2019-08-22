---
title: <disableCommitThreadStack> Öğesi
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b1f55f056ef1aed4a5eff655650cefe778c97ae
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663790"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="e9740-102">\<disableCommitThreadStack > öğesi</span><span class="sxs-lookup"><span data-stu-id="e9740-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="e9740-103">Bir iş parçacığı başlatıldığında tam iş parçacığı yığınının uygulanıp uygulanmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="e9740-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
 <span data-ttu-id="e9740-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="e9740-104">\<configuration></span></span>  
<span data-ttu-id="e9740-105">\<çalışma zamanı ></span><span class="sxs-lookup"><span data-stu-id="e9740-105">\<runtime></span></span>  
<span data-ttu-id="e9740-106">\<disableCommitThreadStack ></span><span class="sxs-lookup"><span data-stu-id="e9740-106">\<disableCommitThreadStack></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9740-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e9740-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9740-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="e9740-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e9740-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="e9740-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9740-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="e9740-110">Attributes</span></span>  
  
|<span data-ttu-id="e9740-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="e9740-111">Attribute</span></span>|<span data-ttu-id="e9740-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e9740-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9740-113">etkinletir</span><span class="sxs-lookup"><span data-stu-id="e9740-113">enabled</span></span>|<span data-ttu-id="e9740-114">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="e9740-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e9740-115">Tüm iş parçacığı yığınının iş parçacığı başlangıcında (varsayılan davranış) devre dışı bırakılıp bırakılmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="e9740-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e9740-116">etkin Öznitelik</span><span class="sxs-lookup"><span data-stu-id="e9740-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="e9740-117">Değer</span><span class="sxs-lookup"><span data-stu-id="e9740-117">Value</span></span>|<span data-ttu-id="e9740-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e9740-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e9740-119">0</span><span class="sxs-lookup"><span data-stu-id="e9740-119">0</span></span>|<span data-ttu-id="e9740-120">Ortak dil çalışma zamanının varsayılan davranışını devre dışı bırakmayın, bu, bir iş parçacığı başlatıldığında tam iş parçacığı yığınını yürütmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e9740-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="e9740-121">1\.</span><span class="sxs-lookup"><span data-stu-id="e9740-121">1</span></span>|<span data-ttu-id="e9740-122">Ortak dil çalışma zamanının varsayılan davranışını devre dışı bırakın, bu, bir iş parçacığı başlatıldığında tam iş parçacığı yığınını yürütmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e9740-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9740-123">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="e9740-123">Child Elements</span></span>  
 <span data-ttu-id="e9740-124">Yok.</span><span class="sxs-lookup"><span data-stu-id="e9740-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9740-125">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="e9740-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e9740-126">Öğe</span><span class="sxs-lookup"><span data-stu-id="e9740-126">Element</span></span>|<span data-ttu-id="e9740-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e9740-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e9740-128">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="e9740-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e9740-129">Derleme bağlama ve atık toplama hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="e9740-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9740-130">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e9740-130">Remarks</span></span>  
 <span data-ttu-id="e9740-131">Ortak dil çalışma zamanının varsayılan davranışı, bir iş parçacığı başlatıldığında tam iş parçacığı yığınını yürütmeniz olur.</span><span class="sxs-lookup"><span data-stu-id="e9740-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="e9740-132">Sınırlı belleği olan bir sunucuda çok sayıda iş parçacığı oluşturulması gerekiyorsa ve bu iş parçacıklarının çoğu çok az yığın alanı kullanıyorsa, ortak dil çalışma zamanı, iş parçacığı St olduğunda tam iş parçacığı yığınını hemen yürütmezse sunucu daha iyi çalışabilir. başlatıldı.</span><span class="sxs-lookup"><span data-stu-id="e9740-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9740-133">Yönetilmeyen konaklar, `STARTUP_DISABLE_COMMITTHREADSTACK` [startup_flags](../../../unmanaged-api/hosting/startup-flags-enumeration.md) numaralandırmasında başlangıç bayrağını kullanarak aynı sonucu elde edebilir.</span><span class="sxs-lookup"><span data-stu-id="e9740-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9740-134">Örnek</span><span class="sxs-lookup"><span data-stu-id="e9740-134">Example</span></span>  
 <span data-ttu-id="e9740-135">Aşağıdaki örnek, ortak dil çalışma zamanının varsayılan davranışının devre dışı bırakılacağını gösterir. Bu, iş parçacığı başlangıcında tam iş parçacığı yığınını yürütmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e9740-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9740-136">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e9740-136">See also</span></span>

- [<span data-ttu-id="e9740-137">Çalışma Zamanı Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="e9740-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e9740-138">Yapılandırma Dosyası Şeması</span><span class="sxs-lookup"><span data-stu-id="e9740-138">Configuration File Schema</span></span>](../index.md)
