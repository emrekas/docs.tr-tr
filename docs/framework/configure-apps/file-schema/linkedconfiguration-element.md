---
title: <linkedConfiguration> öğesi
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
ms.openlocfilehash: 909ee7cbb7cd31cf213f305b23237cb69e295882
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674655"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="75e44-102">\<linkedConfiguration> öğesi</span><span class="sxs-lookup"><span data-stu-id="75e44-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="75e44-103">Dahil edilecek bir yapılandırma dosyası belirtir.</span><span class="sxs-lookup"><span data-stu-id="75e44-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="75e44-104">[ **\<Yapılandırma >** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="75e44-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="75e44-105">&nbsp;&nbsp;[ **\<assemblyBinding >** ](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="75e44-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="75e44-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="75e44-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="75e44-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="75e44-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="75e44-108">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="75e44-108">Attribute</span></span>

|           | <span data-ttu-id="75e44-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="75e44-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="75e44-110">**href**</span><span class="sxs-lookup"><span data-stu-id="75e44-110">**href**</span></span>  | <span data-ttu-id="75e44-111">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="75e44-111">Required attribute.</span></span><br><br><span data-ttu-id="75e44-112">Dahil etmek için yapılandırma dosyasının URL'si.</span><span class="sxs-lookup"><span data-stu-id="75e44-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="75e44-113">Desteklenen tek biçimi **href** özniteliği `file://`.</span><span class="sxs-lookup"><span data-stu-id="75e44-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="75e44-114">Yerel dosyaları ve UNC dosyaları desteklenir.</span><span class="sxs-lookup"><span data-stu-id="75e44-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="75e44-115">Üst öğe</span><span class="sxs-lookup"><span data-stu-id="75e44-115">Parent element</span></span>

|     | <span data-ttu-id="75e44-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="75e44-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="75e44-117"> *\*\<assemblyBinding >** öğesi</span><span class="sxs-lookup"><span data-stu-id="75e44-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="75e44-118">Derleme bağlama ilkesini yapılandırma düzeyinde belirtir.</span><span class="sxs-lookup"><span data-stu-id="75e44-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="75e44-119">Alt öğeleri</span><span class="sxs-lookup"><span data-stu-id="75e44-119">Child elements</span></span>

<span data-ttu-id="75e44-120">None</span><span class="sxs-lookup"><span data-stu-id="75e44-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="75e44-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="75e44-121">Remarks</span></span>

<span data-ttu-id="75e44-122">**\<LinkedConfiguration>** öğesi bileşeni derlemeler için bakım basitleştirir.</span><span class="sxs-lookup"><span data-stu-id="75e44-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="75e44-123">İyi bilinen bir konumda bulunan bir yapılandırma dosyası bir derleme bir veya daha fazla kullanmanız durumunda derleme kullanan uygulamaların yapılandırma dosyalarını kullanabilirler **\<linkedConfiguration>** yapılandırma bilgilerini doğrudan dahil olmak üzere yerine derleme yapılandırma dosyası eklenecek öğe.</span><span class="sxs-lookup"><span data-stu-id="75e44-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="75e44-124">Bileşen derlemesi değiştiğinde, ortak yapılandırma dosyasını güncelleştirme derleme kullanan tüm uygulamalar için güncelleştirilmiş yapılandırma bilgilerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="75e44-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="75e44-125">**\<LinkedConfiguration>** öğesi Windows yan yana bildirimleri olan uygulamalar için desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="75e44-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="75e44-126">Aşağıdaki kuralları bağlantılı yapılandırma dosyaları yöneten:</span><span class="sxs-lookup"><span data-stu-id="75e44-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="75e44-127">Dahil edilen yapılandırma dosyalarındaki ayarlar yalnızca yükleyici bağlama ilkesi etkiler ve yalnızca yükleyicisi tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="75e44-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="75e44-128">Dahil edilen yapılandırma dosyalarını ayarları ilkeleri bağlama dışında olabilir, ancak bu ayarlar, herhangi bir etkisi yok.</span><span class="sxs-lookup"><span data-stu-id="75e44-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="75e44-129">Desteklenen tek biçimi `href` özniteliği `file://`.</span><span class="sxs-lookup"><span data-stu-id="75e44-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="75e44-130">Yerel dosyaları ve UNC dosyaları desteklenir.</span><span class="sxs-lookup"><span data-stu-id="75e44-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="75e44-131">Yapılandırma dosyası başına bağlı yapılandırmaları sayısı hiçbir kısıtlama yoktur.</span><span class="sxs-lookup"><span data-stu-id="75e44-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="75e44-132">Tüm bağlantılı yapılandırma dosyaları davranıştır benzer bir dosya oluşturmak üzere birleştirilir `#include` C/C++'ta yönergesi.</span><span class="sxs-lookup"><span data-stu-id="75e44-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="75e44-133">**\<LinkedConfiguration>** öğesi yalnızca uygulama yapılandırma dosyalarında izin verilir; içindeki sayılır *Machine.config*.</span><span class="sxs-lookup"><span data-stu-id="75e44-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="75e44-134">Döngüsel başvuru algılandı ve sonlandırıldı.</span><span class="sxs-lookup"><span data-stu-id="75e44-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="75e44-135">Diğer bir deyişle, **\<linkedConfiguration>** yapılandırma dosyalarını bir dizi öğeleri formunda bir döngü, döngü algılandı ve durduruldu.</span><span class="sxs-lookup"><span data-stu-id="75e44-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="75e44-136">Örnek</span><span class="sxs-lookup"><span data-stu-id="75e44-136">Example</span></span>

<span data-ttu-id="75e44-137">Aşağıdaki örnek yapılandırma dosyasını yerel sabit diskten nasıl ekleyeceğinizi gösterir:</span><span class="sxs-lookup"><span data-stu-id="75e44-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="75e44-138">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="75e44-138">See also</span></span>

- [<span data-ttu-id="75e44-139"> *\*\<assemblyBinding >** öğesi</span><span class="sxs-lookup"><span data-stu-id="75e44-139">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="75e44-140">.NET Framework yapılandırma dosyası şeması</span><span class="sxs-lookup"><span data-stu-id="75e44-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
