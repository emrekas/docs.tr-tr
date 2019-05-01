---
title: Hizmet
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991451"
---
# <a name="service"></a><span data-ttu-id="4f089-102">Hizmet</span><span class="sxs-lookup"><span data-stu-id="4f089-102">Service</span></span>
<span data-ttu-id="4f089-103">Hizmet</span><span class="sxs-lookup"><span data-stu-id="4f089-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f089-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="4f089-104">Syntax</span></span>  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4f089-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="4f089-105">Methods</span></span>  
 <span data-ttu-id="4f089-106">Hizmet sınıfı, herhangi bir yöntemi tanımlamaz.</span><span class="sxs-lookup"><span data-stu-id="4f089-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4f089-107">Özellikler</span><span class="sxs-lookup"><span data-stu-id="4f089-107">Properties</span></span>  
 <span data-ttu-id="4f089-108">Hizmet sınıfı, aşağıdaki özelliklere sahiptir:</span><span class="sxs-lookup"><span data-stu-id="4f089-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="4f089-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="4f089-109">BaseAddresses</span></span>  
 <span data-ttu-id="4f089-110">Veri türü: dize dizisi</span><span class="sxs-lookup"><span data-stu-id="4f089-110">Data type: string array</span></span>  
  
 <span data-ttu-id="4f089-111">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-112">Hizmet tarafından kullanılan tabanı.</span><span class="sxs-lookup"><span data-stu-id="4f089-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="4f089-113">Davranışlar</span><span class="sxs-lookup"><span data-stu-id="4f089-113">Behaviors</span></span>  
 <span data-ttu-id="4f089-114">Veri türü: Davranış dizi</span><span class="sxs-lookup"><span data-stu-id="4f089-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="4f089-115">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-116">Bu hizmetle ilişkili davranışlar.</span><span class="sxs-lookup"><span data-stu-id="4f089-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="4f089-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="4f089-117">ConfigurationName</span></span>  
 <span data-ttu-id="4f089-118">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="4f089-118">Data type: string</span></span>  
  
 <span data-ttu-id="4f089-119">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f089-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="4f089-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="4f089-121">CounterInstanceName</span></span>  
 <span data-ttu-id="4f089-122">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="4f089-122">Data type: string</span></span>  
  
 <span data-ttu-id="4f089-123">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-124">Performans sayaçlarını hizmetin örneğini örnek adı.</span><span class="sxs-lookup"><span data-stu-id="4f089-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="4f089-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="4f089-125">DistinguishedName</span></span>  
 <span data-ttu-id="4f089-126">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="4f089-126">Data type: string</span></span>  
  
 <span data-ttu-id="4f089-127">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-128">Adresten hizmet adı.</span><span class="sxs-lookup"><span data-stu-id="4f089-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="4f089-129">Uzantıları</span><span class="sxs-lookup"><span data-stu-id="4f089-129">Extensions</span></span>  
 <span data-ttu-id="4f089-130">Veri türü: dize dizisi</span><span class="sxs-lookup"><span data-stu-id="4f089-130">Data type: string array</span></span>  
  
 <span data-ttu-id="4f089-131">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-132">Hizmeti örneğinin uzantıları için örnek bağlamı.</span><span class="sxs-lookup"><span data-stu-id="4f089-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="4f089-133">Meta Veriler</span><span class="sxs-lookup"><span data-stu-id="4f089-133">Metadata</span></span>  
 <span data-ttu-id="4f089-134">Veri türü: dize dizisi</span><span class="sxs-lookup"><span data-stu-id="4f089-134">Data type: string array</span></span>  
  
 <span data-ttu-id="4f089-135">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-136">Hizmet meta verilerini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="4f089-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="4f089-137">Ad</span><span class="sxs-lookup"><span data-stu-id="4f089-137">Name</span></span>  
 <span data-ttu-id="4f089-138">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="4f089-138">Data type: string</span></span>  
  
 <span data-ttu-id="4f089-139">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-140">Bu hizmet benzersiz adı.</span><span class="sxs-lookup"><span data-stu-id="4f089-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="4f089-141">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="4f089-141">Namespace</span></span>  
 <span data-ttu-id="4f089-142">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="4f089-142">Data type: string</span></span>  
  
 <span data-ttu-id="4f089-143">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-144">Hizmet ad alanı.</span><span class="sxs-lookup"><span data-stu-id="4f089-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="4f089-145">Açılan</span><span class="sxs-lookup"><span data-stu-id="4f089-145">Opened</span></span>  
 <span data-ttu-id="4f089-146">Veri türü: tarih/saat</span><span class="sxs-lookup"><span data-stu-id="4f089-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="4f089-147">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-148">Hizmet açıldığı zaman.</span><span class="sxs-lookup"><span data-stu-id="4f089-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="4f089-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="4f089-149">OutgoingChannels</span></span>  
 <span data-ttu-id="4f089-150">Veri türü: Kanal dizisi</span><span class="sxs-lookup"><span data-stu-id="4f089-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="4f089-151">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-152">Hizmeti örneğinin giden kanallar.</span><span class="sxs-lookup"><span data-stu-id="4f089-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="4f089-153">İşlem kimliği</span><span class="sxs-lookup"><span data-stu-id="4f089-153">ProcessId</span></span>  
 <span data-ttu-id="4f089-154">Veri türü: SINT32</span><span class="sxs-lookup"><span data-stu-id="4f089-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="4f089-155">Erişim türü: salt okunur</span><span class="sxs-lookup"><span data-stu-id="4f089-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f089-156">Hizmet barındıran işlemin işlem kimliği.</span><span class="sxs-lookup"><span data-stu-id="4f089-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f089-157">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="4f089-157">Requirements</span></span>  
  
|<span data-ttu-id="4f089-158">MOF</span><span class="sxs-lookup"><span data-stu-id="4f089-158">MOF</span></span>|<span data-ttu-id="4f089-159">Bildirilmiş Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4f089-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4f089-160">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="4f089-160">Namespace</span></span>|<span data-ttu-id="4f089-161">İçinde tanımlı root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4f089-161">Defined in root\ServiceModel</span></span>|
