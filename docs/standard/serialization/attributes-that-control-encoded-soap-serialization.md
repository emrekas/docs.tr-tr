---
title: Kodlanmış SOAP serileştirmesini denetleyen öznitelikler
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
ms.openlocfilehash: 2961d9abc6c32e78b5a61e8f2bbea5cfcf6677bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547208"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a><span data-ttu-id="82038-102">Kodlanmış SOAP serileştirmesini denetleyen öznitelikler</span><span class="sxs-lookup"><span data-stu-id="82038-102">Attributes That Control Encoded SOAP Serialization</span></span>

<span data-ttu-id="82038-103">Adlı World Wide Web Consortium (W3C) belgenin [Basit Nesne Erişim Protokolü (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) nasıl SOAP parametreleri kodlanmış açıklayan isteğe bağlı bir bölüm (Bölüm 5) içerir.</span><span class="sxs-lookup"><span data-stu-id="82038-103">The World Wide Web Consortium (W3C) document named [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) contains an optional section (section 5) that describes how SOAP parameters can be encoded.</span></span> <span data-ttu-id="82038-104">Belirtiminin 5 bölümüne uymak için özel öznitelikler bulundu kümesi kullanmak <xref:System.Xml.Serialization> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="82038-104">To conform to section 5 of the specification, you must use a special set of attributes found in the <xref:System.Xml.Serialization> namespace.</span></span> <span data-ttu-id="82038-105">Özniteliklerle sınıfları ve sınıf üyeleri için uygun olarak uygulayın ve ardından <xref:System.Xml.Serialization.XmlSerializer> sınıf veya sınıfların örneklerini serileştirmek için.</span><span class="sxs-lookup"><span data-stu-id="82038-105">Apply those attributes as appropriate to classes and members of classes, and then use the <xref:System.Xml.Serialization.XmlSerializer> to serialize instances of the class or classes.</span></span>

<span data-ttu-id="82038-106">Aşağıdaki tablo nerede bunlar uygulanabilir, öznitelikleri ve neler yaptığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="82038-106">The following table shows the attributes, where they can be applied, and what they do.</span></span> <span data-ttu-id="82038-107">Denetim XML serileştirme için bu öznitelikleri kullanmayla ilgili daha fazla bilgi için bkz. [nasıl yapılır: SOAP kodlu XML Stream olarak bir nesneyi serileştirmek](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) ve [nasıl yapılır: Kodlanmış SOAP XML serileştirmesini geçersiz kılma](how-to-override-encoded-soap-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="82038-107">For more information about using these attributes to control XML serialization, see [How to: Serialize an Object as a SOAP-Encoded XML Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) and [How to: Override Encoded SOAP XML Serialization](how-to-override-encoded-soap-xml-serialization.md).</span></span>

<span data-ttu-id="82038-108">Öznitelikler hakkında daha fazla bilgi için bkz. [öznitelikleri](../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="82038-108">For more information about attributes, see [Attributes](../../../docs/standard/attributes/index.md).</span></span>

|<span data-ttu-id="82038-109">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="82038-109">Attribute</span></span>|<span data-ttu-id="82038-110">Uygulandığı öğe:</span><span class="sxs-lookup"><span data-stu-id="82038-110">Applies to</span></span>|<span data-ttu-id="82038-111">Belirler</span><span class="sxs-lookup"><span data-stu-id="82038-111">Specifies</span></span>|
|---------------|----------------|---------------|
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|<span data-ttu-id="82038-112">Ortak alan, özelliği, parameTRe veya dönüş değeri.</span><span class="sxs-lookup"><span data-stu-id="82038-112">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="82038-113">Sınıf üyesi bir XML özniteliği olarak seri hale.</span><span class="sxs-lookup"><span data-stu-id="82038-113">The class member will be serialized as an XML attribute.</span></span>|
|<xref:System.Xml.Serialization.SoapElementAttribute>|<span data-ttu-id="82038-114">Ortak alan, özelliği, parameTRe veya dönüş değeri.</span><span class="sxs-lookup"><span data-stu-id="82038-114">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="82038-115">Sınıf bir XML öğesi olarak seri hale.</span><span class="sxs-lookup"><span data-stu-id="82038-115">The class will be serialized as an XML element.</span></span>|
|<xref:System.Xml.Serialization.SoapEnumAttribute>|<span data-ttu-id="82038-116">Bir numaralandırma tanımlayıcı ortak alan.</span><span class="sxs-lookup"><span data-stu-id="82038-116">Public field that is an enumeration identifier.</span></span>|<span data-ttu-id="82038-117">Numaralandırma üyesi öğe adı.</span><span class="sxs-lookup"><span data-stu-id="82038-117">The element name of an enumeration member.</span></span>|
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|<span data-ttu-id="82038-118">Ortak özellikler ve alanları.</span><span class="sxs-lookup"><span data-stu-id="82038-118">Public properties and fields.</span></span>|<span data-ttu-id="82038-119">Kapsayan sınıfı serileştirilmiş olduğunda özellik veya alan yoksayılacak.</span><span class="sxs-lookup"><span data-stu-id="82038-119">The property or field should be ignored when the containing class is serialized.</span></span>|
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|<span data-ttu-id="82038-120">Genel türetilmiş sınıf bildirimleri ve Web Hizmetleri Açıklama Dili (WSDL) belgeleri için ortak yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="82038-120">Public-derived class declarations and public methods for Web Services Description Language (WSDL) documents.</span></span>|<span data-ttu-id="82038-121">Türü (serileştirilmiş olduğunda tanınması için) şemalar oluşturulurken dahil edilecek.</span><span class="sxs-lookup"><span data-stu-id="82038-121">The type should be included when generating schemas (to be recognized when serialized).</span></span>|
|<xref:System.Xml.Serialization.SoapTypeAttribute>|<span data-ttu-id="82038-122">Ortak sınıf bildirimleri.</span><span class="sxs-lookup"><span data-stu-id="82038-122">Public class declarations.</span></span>|<span data-ttu-id="82038-123">Sınıf bir XML türü olarak seri hale.</span><span class="sxs-lookup"><span data-stu-id="82038-123">The class should be serialized as an XML type.</span></span>|

## <a name="see-also"></a><span data-ttu-id="82038-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="82038-124">See also</span></span>

- [<span data-ttu-id="82038-125">XML ve SOAP Serileştirme</span><span class="sxs-lookup"><span data-stu-id="82038-125">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="82038-126">Nasıl yapılır: Bir nesne bir SOAP kodlu XML Stream seri hale getirme</span><span class="sxs-lookup"><span data-stu-id="82038-126">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)
- [<span data-ttu-id="82038-127">Nasıl yapılır: Kodlanmış SOAP XML serileştirmesini geçersiz kılma</span><span class="sxs-lookup"><span data-stu-id="82038-127">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)
- [<span data-ttu-id="82038-128">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="82038-128">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="82038-129">Nasıl yapılır: Bir nesneyi serileştirmek</span><span class="sxs-lookup"><span data-stu-id="82038-129">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="82038-130">Nasıl yapılır: Bir nesneyi seri durumdan çıkarma</span><span class="sxs-lookup"><span data-stu-id="82038-130">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
