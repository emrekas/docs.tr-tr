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
ms.openlocfilehash: d3071b25392048161ebb40c39842f5da0dce3475
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920825"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="741ed-102">\<disableCommitThreadStack > öğesi</span><span class="sxs-lookup"><span data-stu-id="741ed-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="741ed-103">Bir iş parçacığı başlatıldığında tam iş parçacığı yığınının uygulanıp uygulanmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="741ed-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
 <span data-ttu-id="741ed-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="741ed-104">\<configuration></span></span>  
<span data-ttu-id="741ed-105">\<çalışma zamanı ></span><span class="sxs-lookup"><span data-stu-id="741ed-105">\<runtime></span></span>  
<span data-ttu-id="741ed-106">\<disableCommitThreadStack ></span><span class="sxs-lookup"><span data-stu-id="741ed-106">\<disableCommitThreadStack></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="741ed-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="741ed-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="741ed-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="741ed-108">Attributes and Elements</span></span>  
 <span data-ttu-id="741ed-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="741ed-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="741ed-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="741ed-110">Attributes</span></span>  
  
|<span data-ttu-id="741ed-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="741ed-111">Attribute</span></span>|<span data-ttu-id="741ed-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="741ed-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="741ed-113">etkinletir</span><span class="sxs-lookup"><span data-stu-id="741ed-113">enabled</span></span>|<span data-ttu-id="741ed-114">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="741ed-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="741ed-115">Tüm iş parçacığı yığınının iş parçacığı başlangıcında (varsayılan davranış) devre dışı bırakılıp bırakılmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="741ed-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="741ed-116">etkin Öznitelik</span><span class="sxs-lookup"><span data-stu-id="741ed-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="741ed-117">Değer</span><span class="sxs-lookup"><span data-stu-id="741ed-117">Value</span></span>|<span data-ttu-id="741ed-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="741ed-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="741ed-119">0</span><span class="sxs-lookup"><span data-stu-id="741ed-119">0</span></span>|<span data-ttu-id="741ed-120">Ortak dil çalışma zamanının varsayılan davranışını devre dışı bırakmayın, bu, bir iş parçacığı başlatıldığında tam iş parçacığı yığınını yürütmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="741ed-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="741ed-121">1\.</span><span class="sxs-lookup"><span data-stu-id="741ed-121">1</span></span>|<span data-ttu-id="741ed-122">Ortak dil çalışma zamanının varsayılan davranışını devre dışı bırakın, bu, bir iş parçacığı başlatıldığında tam iş parçacığı yığınını yürütmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="741ed-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="741ed-123">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="741ed-123">Child Elements</span></span>  
 <span data-ttu-id="741ed-124">Yok.</span><span class="sxs-lookup"><span data-stu-id="741ed-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="741ed-125">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="741ed-125">Parent Elements</span></span>  
  
|<span data-ttu-id="741ed-126">Öğe</span><span class="sxs-lookup"><span data-stu-id="741ed-126">Element</span></span>|<span data-ttu-id="741ed-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="741ed-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="741ed-128">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="741ed-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="741ed-129">Derleme bağlama ve atık toplama hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="741ed-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="741ed-130">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="741ed-130">Remarks</span></span>  
 <span data-ttu-id="741ed-131">Ortak dil çalışma zamanının varsayılan davranışı, bir iş parçacığı başlatıldığında tam iş parçacığı yığınını yürütmeniz olur.</span><span class="sxs-lookup"><span data-stu-id="741ed-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="741ed-132">Sınırlı belleği olan bir sunucuda çok sayıda iş parçacığı oluşturulması gerekiyorsa ve bu iş parçacıklarının çoğu çok az yığın alanı kullanıyorsa, ortak dil çalışma zamanı, iş parçacığı St olduğunda tam iş parçacığı yığınını hemen yürütmezse sunucu daha iyi çalışabilir. başlatıldı.</span><span class="sxs-lookup"><span data-stu-id="741ed-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="741ed-133">Yönetilmeyen konaklar, `STARTUP_DISABLE_COMMITTHREADSTACK` [startup_flags](../../../unmanaged-api/hosting/startup-flags-enumeration.md) numaralandırmasında başlangıç bayrağını kullanarak aynı sonucu elde edebilir.</span><span class="sxs-lookup"><span data-stu-id="741ed-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="741ed-134">Örnek</span><span class="sxs-lookup"><span data-stu-id="741ed-134">Example</span></span>  
 <span data-ttu-id="741ed-135">Aşağıdaki örnek, ortak dil çalışma zamanının varsayılan davranışının devre dışı bırakılacağını gösterir. Bu, iş parçacığı başlangıcında tam iş parçacığı yığınını yürütmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="741ed-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="741ed-136">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="741ed-136">See also</span></span>

- [<span data-ttu-id="741ed-137">Çalışma Zamanı Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="741ed-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="741ed-138">Yapılandırma Dosyası Şeması</span><span class="sxs-lookup"><span data-stu-id="741ed-138">Configuration File Schema</span></span>](../index.md)
