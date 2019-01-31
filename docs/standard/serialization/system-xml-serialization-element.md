---
title: <system.xml.serialization> Öğesi
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: f41e3811fc6bab8a354f75f46b0ac79c0ce42f99
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288697"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="c47b4-102">\<system.xml.serialization> Element</span><span class="sxs-lookup"><span data-stu-id="c47b4-102">\<system.xml.serialization> Element</span></span>
<span data-ttu-id="c47b4-103">XML serileştirme denetlemek için üst düzey öğe.</span><span class="sxs-lookup"><span data-stu-id="c47b4-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="c47b4-104">Yapılandırma dosyaları hakkında daha fazla bilgi için bkz. [yapılandırma dosyası şeması](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="c47b4-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="c47b4-105">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="c47b4-105">\<configuration></span></span>  
<span data-ttu-id="c47b4-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="c47b4-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c47b4-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c47b4-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c47b4-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="c47b4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c47b4-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="c47b4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c47b4-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="c47b4-110">Attributes</span></span>  
 <span data-ttu-id="c47b4-111">Yok.</span><span class="sxs-lookup"><span data-stu-id="c47b4-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c47b4-112">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="c47b4-112">Child Elements</span></span>  
  
|<span data-ttu-id="c47b4-113">Öğe</span><span class="sxs-lookup"><span data-stu-id="c47b4-113">Element</span></span>|<span data-ttu-id="c47b4-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c47b4-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c47b4-115">\<dateTimeSerialization > öğesi</span><span class="sxs-lookup"><span data-stu-id="c47b4-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="c47b4-116">Serileştirme modu belirler <xref:System.DateTime> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="c47b4-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="c47b4-117">\<schemaImporterExtensions > öğesi</span><span class="sxs-lookup"><span data-stu-id="c47b4-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="c47b4-118">Tarafından kullanılan türler içerir <xref:System.Xml.Serialization.XmlSchemaImporter> için .NET Framework türleri için XSD türü eşleme.</span><span class="sxs-lookup"><span data-stu-id="c47b4-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c47b4-119">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="c47b4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c47b4-120">Öğe</span><span class="sxs-lookup"><span data-stu-id="c47b4-120">Element</span></span>|<span data-ttu-id="c47b4-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c47b4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c47b4-122">\<Yapılandırma > öğesi</span><span class="sxs-lookup"><span data-stu-id="c47b4-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="c47b4-123">Her yapılandırma dosyasında ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="c47b4-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c47b4-124">Örnek</span><span class="sxs-lookup"><span data-stu-id="c47b4-124">Example</span></span>  
 <span data-ttu-id="c47b4-125">Aşağıdaki kod örneğinde serileştirme modunu belirtmek verilmektedir bir <xref:System.DateTime> nesnesi ve tarafından kullanılan türlerinin eklenmesi <xref:System.Xml.Serialization.XmlSchemaImporter> XSD türleri için .NET Framework türleri eşlerken.</span><span class="sxs-lookup"><span data-stu-id="c47b4-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c47b4-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c47b4-126">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="c47b4-127">Yapılandırma Dosyası Şeması</span><span class="sxs-lookup"><span data-stu-id="c47b4-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="c47b4-128">\<dateTimeSerialization > öğesi</span><span class="sxs-lookup"><span data-stu-id="c47b4-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="c47b4-129">\<schemaImporterExtensions > öğesi</span><span class="sxs-lookup"><span data-stu-id="c47b4-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="c47b4-130">\<Ekle > öğesi için \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="c47b4-130">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
