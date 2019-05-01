---
title: IIS ve WAS'ta Yapılandırma Temelli Etkinleştirme
ms.date: 03/30/2017
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
ms.openlocfilehash: da98d237c066b70398d3238a75500e8a3abbe887
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857551"
---
# <a name="configuration-based-activation-in-iis-and-was"></a><span data-ttu-id="d33c6-102">IIS ve WAS'ta Yapılandırma Temelli Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="d33c6-102">Configuration-Based Activation in IIS and WAS</span></span>

<span data-ttu-id="d33c6-103">Normalde Internet Information Services (IIS) veya Windows İşlem Etkinleştirme Hizmeti (WAS) altında bir Windows Communication Foundation (WCF) hizmeti barındırırken .svc dosyası sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="d33c6-103">Normally when hosting a Windows Communication Foundation (WCF) service under Internet Information Services (IIS) or Windows Process Activation Service (WAS), you must provide a .svc file.</span></span> <span data-ttu-id="d33c6-104">.Svc dosyası, hizmet ve bir isteğe bağlı bir özel hizmet barındırma ortamı fabrikası adını içerir.</span><span class="sxs-lookup"><span data-stu-id="d33c6-104">The .svc file contains the name of the service and an optional custom service host factory.</span></span> <span data-ttu-id="d33c6-105">Bu ek dosya yönetilebilirlik yükü ekler.</span><span class="sxs-lookup"><span data-stu-id="d33c6-105">This additional file adds manageability overhead.</span></span> <span data-ttu-id="d33c6-106">Yapılandırma temelli etkinleştirme özelliği .svc dosya ve bu nedenle ilişkili gereksinimini ortadan kaldırır yükü.</span><span class="sxs-lookup"><span data-stu-id="d33c6-106">The configuration-based activation feature removes the requirement to have a .svc file and therefore the associated overhead.</span></span>

## <a name="configuration-based-activation"></a><span data-ttu-id="d33c6-107">Yapılandırma Temelli Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="d33c6-107">Configuration-Based Activation</span></span>

<span data-ttu-id="d33c6-108">Yapılandırma temelli etkinleştirme .svc dosyasında yerleştirilmesi için kullanılır ve Web.config dosyasına yerleştirir meta verileri alır.</span><span class="sxs-lookup"><span data-stu-id="d33c6-108">Configuration-based activation takes the metadata that used to be placed in the .svc file and places it in the Web.config file.</span></span> <span data-ttu-id="d33c6-109">İçinde <`serviceHostingEnvironment`> öğesi yok bir <`serviceActivations`> öğesi.</span><span class="sxs-lookup"><span data-stu-id="d33c6-109">Within the<`serviceHostingEnvironment`> element there is a <`serviceActivations`> element.</span></span> <span data-ttu-id="d33c6-110">İçinde <`serviceActivations`> öğesi bir veya daha fazla <`add`> öğeleri, her bir barındırılan hizmet için bir tane.</span><span class="sxs-lookup"><span data-stu-id="d33c6-110">Within the <`serviceActivations`> element are one or more <`add`> elements, one for each hosted service.</span></span> <span data-ttu-id="d33c6-111"><`add`> Öğesi, hizmet ve hizmet türü veya bir hizmet barındırma ortamı fabrikası için hizmetin göreli adresini ayarlamanıza olanak tanıyan öznitelikleri içeriyor.</span><span class="sxs-lookup"><span data-stu-id="d33c6-111">The <`add`> element contains attributes that let you set the relative address for the service and the service type or a service host factory.</span></span> <span data-ttu-id="d33c6-112">Aşağıdaki yapılandırma örnek kod, bu bölümde nasıl kullanıldığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="d33c6-112">The following configuration example code shows how this section is used.</span></span>

> [!NOTE]
>  <span data-ttu-id="d33c6-113">Her <`add`> öğesi bir hizmeti ya da bir Fabrika özniteliğini belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="d33c6-113">Each <`add`> element must specify a service or a factory attribute.</span></span> <span data-ttu-id="d33c6-114">Hem hizmet hem de Fabrika öznitelikleri belirterek izin verilir.</span><span class="sxs-lookup"><span data-stu-id="d33c6-114">Specifying both service and factory attributes is allowed.</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>
  </serviceActivations>
</serviceHostingEnvironment>
```

 <span data-ttu-id="d33c6-115">Bu Web.config dosyasında, hizmet kaynak kodu uygulama veya uygulamanın Bin dizinindeki derlenmiş bir bütünleştirilmiş kod App_Code dizinindeki yerleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d33c6-115">With this in the Web.config file, you can place the service source code in the App_Code directory of the application or a complied assembly in the Bin directory of the application.</span></span>

> [!NOTE]
> - <span data-ttu-id="d33c6-116">Yapılandırma temelli etkinleştirme kullanırken, satır içi kod .svc dosyalarında desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="d33c6-116">When using configuration-based activation, inline code in .svc files is not supported.</span></span>
> - <span data-ttu-id="d33c6-117">`relativeAddress` Özniteliği ayarlanmalıdır göreli bir adrese gibi "\<alt dizini > / service.svc" veya "~ /\<alt-directory/service.svc".</span><span class="sxs-lookup"><span data-stu-id="d33c6-117">The `relativeAddress` attribute must be set to a relative address such as "\<sub-directory>/service.svc" or "~/\<sub-directory/service.svc".</span></span>
> - <span data-ttu-id="d33c6-118">WCF ile ilgili bilinen bir uzantı yok. bir göreli adres kaydolarak bir yapılandırma özel durum oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="d33c6-118">A configuration exception is thrown if you register a relative address that does not have a known extension associated with WCF.</span></span>
> - <span data-ttu-id="d33c6-119">Belirtilen göreli sanal uygulama köküne göreli adresidir.</span><span class="sxs-lookup"><span data-stu-id="d33c6-119">The relative address specified is relative to the root of the virtual application.</span></span>
> - <span data-ttu-id="d33c6-120">Hiyerarşik yapılandırma modeli nedeniyle, makine ve site düzeyinde kayıtlı göreli adresleri sanal uygulamalar tarafından devralınır.</span><span class="sxs-lookup"><span data-stu-id="d33c6-120">Due to the hierarchical model of configuration, the registered relative addresses at machine and site level are inherited by virtual applications.</span></span>
> - <span data-ttu-id="d33c6-121">Bir yapılandırma dosyası kayıtları bir .svc, .xamlx, .xoml veya diğer dosya ayarlarında daha önceliklidir.</span><span class="sxs-lookup"><span data-stu-id="d33c6-121">Registrations in a configuration file take precedence over settings in a .svc, .xamlx, .xoml, or other file.</span></span>
> - <span data-ttu-id="d33c6-122">Tüm ' \' (ters eğik çizgi) için IIS gönderilen bir Uri / WAS'da otomatik olarak dönüştürülür bir '/' (eğik çizgi).</span><span class="sxs-lookup"><span data-stu-id="d33c6-122">Any ‘\’ (backslashes) in a URI sent to IIS/WAS are automatically converted to a ‘/’ (forward slash).</span></span> <span data-ttu-id="d33c6-123">Göreli adres eklenirse içeren bir ' \' ve IIS göreli adresini kullanan bir URI göndermek, ters eğik çizgiyi eğik çizgi için dönüştürülür ve IIS, göreli adresine eşleşemez.</span><span class="sxs-lookup"><span data-stu-id="d33c6-123">If a relative address is added that contains a ‘\’ and you send IIS a URI that uses the relative address, the backslash is converted to a forward slash and IIS cannot match it to the relative address.</span></span> <span data-ttu-id="d33c6-124">IIS eşleşme olduğunu gösterir izleme bilgilerini gönderir.</span><span class="sxs-lookup"><span data-stu-id="d33c6-124">IIS sends out trace information that indicates that there are no matches found.</span></span>

## <a name="see-also"></a><span data-ttu-id="d33c6-125">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d33c6-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>
- [<span data-ttu-id="d33c6-126">Barındırma Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="d33c6-126">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="d33c6-127">İş Akışı Hizmetlerini Barındırmaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="d33c6-127">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)
- [<span data-ttu-id="d33c6-128">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="d33c6-128">\<serviceHostingEnvironment></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)
- [<span data-ttu-id="d33c6-129">Windows Server App Fabric barındırma özellikleri</span><span class="sxs-lookup"><span data-stu-id="d33c6-129">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)