---
title: Singletagsectionhandler özel öğesi
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 232ad7527e65fd38fa471cccc917752aef766a88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628844"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="fe392-102">Singletagsectionhandler özel öğesi</span><span class="sxs-lookup"><span data-stu-id="fe392-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="fe392-103">Özel yapılandırma bölümü tarafından tanımlanan ayarları tanımlayan bir</span><span class="sxs-lookup"><span data-stu-id="fe392-103">Defines settings in a custom configuration section that is defined by a</span></span> <section> <span data-ttu-id="fe392-104">öğe ve kullandığı <xref:System.Configuration.SingleTagSectionHandler> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="fe392-104">element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="fe392-105">[**\<Yapılandırma >**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fe392-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="fe392-106">&nbsp;&nbsp;*\<sectionName >*</span><span class="sxs-lookup"><span data-stu-id="fe392-106">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="fe392-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fe392-107">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="fe392-108">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="fe392-108">Attributes</span></span>

<span data-ttu-id="fe392-109">Kullanıcı tanımlı öznitelikler ve öznitelik değerleri var.</span><span class="sxs-lookup"><span data-stu-id="fe392-109">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="fe392-110">Üst öğe</span><span class="sxs-lookup"><span data-stu-id="fe392-110">Parent element</span></span>

|     | <span data-ttu-id="fe392-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="fe392-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fe392-112">**\<Yapılandırma >**</span><span class="sxs-lookup"><span data-stu-id="fe392-112">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="fe392-113">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="fe392-113">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="fe392-114">Alt öğeleri</span><span class="sxs-lookup"><span data-stu-id="fe392-114">Child elements</span></span>

<span data-ttu-id="fe392-115">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="fe392-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="fe392-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fe392-116">Remarks</span></span>

<span data-ttu-id="fe392-117"> *\*\<SectionName >** öğedir tarafından tanımlanan özel bir öğe bir [  *\*\<bölüm >** ](~/docs/framework/configure-apps/file-schema/section-element.md) içindeki [  *\*\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="fe392-117">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="fe392-118">Yapılandırma sistemi döndürür bir <xref:System.Collections.IDictionary> nesne çağırdığınızda <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fe392-118">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="fe392-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="fe392-119">Example</span></span>

<span data-ttu-id="fe392-120">Aşağıdaki örnekte adlı özel bir öğe bildirir  **\<sampleSection >** tarafından okunur ayarları içeren <xref:System.Configuration.SingleTagSectionHandler> sınıfı:</span><span class="sxs-lookup"><span data-stu-id="fe392-120">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="fe392-121">Yapılandırma dosyası</span><span class="sxs-lookup"><span data-stu-id="fe392-121">Configuration file</span></span>

<span data-ttu-id="fe392-122">Bu öğe, uygulama yapılandırma dosyasında, makine yapılandırma dosyası kullanılabilir (*Machine.config*), ve *Web.config* uygulama dizin düzeyinde olmayan dosyalar.</span><span class="sxs-lookup"><span data-stu-id="fe392-122">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe392-123">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fe392-123">See also</span></span>

- [<span data-ttu-id="fe392-124">.NET Framework yapılandırma dosyası şeması</span><span class="sxs-lookup"><span data-stu-id="fe392-124">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
