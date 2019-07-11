---
title: IMetaDataEmit::DefineMethod Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4297b21970fbca4b5aa53c31680394cab358d255
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777603"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="d5b7d-102">IMetaDataEmit::DefineMethod Yöntemi</span><span class="sxs-lookup"><span data-stu-id="d5b7d-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="d5b7d-103">Belirtilen imzayla bir yöntem veya genel bir işlev için bir tanım oluşturur ve bu yöntem tanımını bir belirteç döndürür.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b7d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d5b7d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5b7d-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="d5b7d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d5b7d-106">[in] `mdTypedef` Üst sınıf veya yöntemin üst arabirimi belirteci.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="d5b7d-107">Ayarlama `td` için `mdTokenNil`, genel bir işlev tanımlıyorsanız.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="d5b7d-108">[in] Üye adı Unicode.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="d5b7d-109">[in] Değerini [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) yöntemi veya genel işlev özniteliklerini belirten sabit listesi.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="d5b7d-110">[in] Yöntem imzası.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-110">[in] The method signature.</span></span> <span data-ttu-id="d5b7d-111">İmza sağlanan olarak kalıcı hale getirilir.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="d5b7d-112">Daha fazla bilgi için herhangi bir parametre belirtmeniz gerekiyorsa, kullanın [Imetadataemit::setparamprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="d5b7d-113">[in] Bayt sayısı `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="d5b7d-114">[in] Kod adresi.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="d5b7d-115">[in] Değerini [Cormethodımpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) yöntemi uygulama özelliklerinin belirten sabit listesi.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="d5b7d-116">[out] Üye belirteci.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5b7d-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d5b7d-117">Remarks</span></span>  
 <span data-ttu-id="d5b7d-118">Bunları yayan çağıranın verilen kapsayan sınıfı veya arabirimi, belirtilen gibi yöntemleri aynı sırayla kalıcı hale getirmek meta veri API'si garanti `td` parametresi.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="d5b7d-119">Kullanımı ile ilgili ek bilgiler `DefineMethod` ve belirli parametre ayarlarını aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="d5b7d-120">V-table yuvaları</span><span class="sxs-lookup"><span data-stu-id="d5b7d-120">Slots in the V-table</span></span>  
 <span data-ttu-id="d5b7d-121">Çalışma zamanı yöntemi tanımları v-table yuvaları ayarlamak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="d5b7d-122">Bir veya daha fazla yuva Atlanan, böyle olması için gereken yere durumda, yuva veya v-table yuvalarda yararlanmak için işlevsiz bir yöntem eşlikli bir COM arabirimi düzeni korumak için farklı tanımlanır; ayarlama `dwMethodFlags` için `mdRTSpecialName` değerini [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) sabit listesi adı olarak belirtin:</span><span class="sxs-lookup"><span data-stu-id="d5b7d-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="d5b7d-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="d5b7d-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="d5b7d-124">Burada *SequenceNumber* yöntemi sıra sayısı ve *CountOfSlots* v tablosunda atlamak için yuvaları sayısıdır.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="d5b7d-125">Varsa *CountOfSlots* olan atlanırsa, 1 varsayılır.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="d5b7d-126">İşlevsiz bu yöntemler yönetilen veya yönetilmeyen koddan çağrılabilir değildir ve her türlü girişim, yönetilen veya yönetilmeyen koddan çağırmak için bir özel durum oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="d5b7d-127">V-table için COM tümleştirme çalışma zamanının oluşturduğu alan yalnızca amaçlarına gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="d5b7d-128">Yinelenen yöntemleri</span><span class="sxs-lookup"><span data-stu-id="d5b7d-128">Duplicate Methods</span></span>  
 <span data-ttu-id="d5b7d-129">Yinelenen yöntemleri tanımlanmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-129">You should not define duplicate methods.</span></span> <span data-ttu-id="d5b7d-130">Diğer bir deyişle, değil, çağırmalıdır `DefineMethod` yinelenen değerleri kümesi ile `td`, `wzName`, ve `pvSig` parametreleri.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="d5b7d-131">(Şu üç parametreyi birlikte yöntem benzersiz olarak tanımlayın.).</span><span class="sxs-lookup"><span data-stu-id="d5b7d-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="d5b7d-132">Ancak, yöntem tanımlarını biri için ayarladığınız olması koşuluyla, yinelenen bir Üçlü kullanabilirsiniz `mdPrivateScope` içindeki bit `dwMethodFlags` parametresi.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="d5b7d-133">( `mdPrivateScope` Bit Derleyici bu yöntem tanımını başvuru yayma değil demektir.)</span><span class="sxs-lookup"><span data-stu-id="d5b7d-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="d5b7d-134">Uygulama bilgileri yöntemi</span><span class="sxs-lookup"><span data-stu-id="d5b7d-134">Method Implementation Information</span></span>  
 <span data-ttu-id="d5b7d-135">Yöntem uygulaması hakkında bilgi yöntemi bildirilen zamanında bilinen değildir.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="d5b7d-136">Bu nedenle, değerleri geçirmek gerekmez `ulCodeRVA` ve `dwImplFlags` çağırırken parametre `DefineMethod`.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="d5b7d-137">Değerleri daha sonra aracılığıyla sağlanabilir [Imetadataemit::setmethodımplflags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) veya [Imetadataemit::setrva](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)uygun şekilde.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="d5b7d-138">Platform çağırma (PInvoke) veya COM birlikte çalışma senaryoları gibi bazı durumlarda, yöntem gövdesini sunulacaktır değil, ve `ulCodeRVA` sıfır olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="d5b7d-139">Çalışma zamanı uygulaması çünkü bu gibi durumlarda yöntemi soyut olarak etiketlenmesi değil.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="d5b7d-140">PInvoke için bir yöntem tanımlama</span><span class="sxs-lookup"><span data-stu-id="d5b7d-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="d5b7d-141">PInvoke aracılığıyla çağrılan her yönetilmeyen bir işlev için hedef yönetilmeyen işlev temsil eden bir yönetilen yöntemin tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="d5b7d-142">Yönetilen yöntemi tanımlamak için `DefineMethod` bazı parametreler PInvoke kullanıldığı şekilde bağlı olarak belirli değerlere ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="d5b7d-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="d5b7d-143">PInvoke true - yönetilmeyen DLL içinde yer alan bir dış yönetilmeyen yöntemi çağırmayı içerir.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="d5b7d-144">Yerel PInvoke - geçerli yönetilen modülde gömülü yerel bir yönetilmeyen yöntemini çağırmayı içerir.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="d5b7d-145">Parametre ayarları aşağıdaki tabloda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="d5b7d-146">Parametre</span><span class="sxs-lookup"><span data-stu-id="d5b7d-146">Parameter</span></span>|<span data-ttu-id="d5b7d-147">Değerleri için doğru PInvoke</span><span class="sxs-lookup"><span data-stu-id="d5b7d-147">Values for true PInvoke</span></span>|<span data-ttu-id="d5b7d-148">Yerel PInvoke değerleri</span><span class="sxs-lookup"><span data-stu-id="d5b7d-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="d5b7d-149">Ayarlama `mdStatic`; clear `mdSynchronized` ve `mdAbstract`.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="d5b7d-150">Yönetilen türler geçersiz parametrelerle geçerli ortak dil çalışma zamanı (CLR) metodu imzası.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="d5b7d-151">Yönetilen türler geçersiz parametrelerle geçerli bir CLR metodu imzası.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="d5b7d-152">0</span><span class="sxs-lookup"><span data-stu-id="d5b7d-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="d5b7d-153">Ayarlama `miCil` ve `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="d5b7d-154">Ayarlama `miNative` ve `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5b7d-155">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="d5b7d-155">Requirements</span></span>  
 <span data-ttu-id="d5b7d-156">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5b7d-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5b7d-157">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="d5b7d-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5b7d-158">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll kullanılan</span><span class="sxs-lookup"><span data-stu-id="d5b7d-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5b7d-159">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5b7d-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b7d-160">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d5b7d-160">See also</span></span>

- [<span data-ttu-id="d5b7d-161">IMetaDataEmit Arabirimi</span><span class="sxs-lookup"><span data-stu-id="d5b7d-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d5b7d-162">IMetaDataEmit2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="d5b7d-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
