---
title: ICorDebugCode3::GetReturnValueLiveOffset Metodu
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5aa53d1c9d101544f532c51f43a8b47143117813
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988272"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>ICorDebugCode3::GetReturnValueLiveOffset Metodu
Belirtilen bir Il ofseti için, hata ayıklayıcının bir işlevden dönüş değeri alabileceği şekilde, bir kesme noktasının yerleştirilmesi gereken yerel uzaklıkları alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `ILoffset`  
 Il kayması. İşlevin çağrı sitesi olması gerekir veya işlev çağrısı başarısız olur.  
  
 `bufferSize`  
 Depolanacak `pOffsets`kullanılabilir bayt sayısı.  
  
 `pFetched`  
 Gerçekten döndürülen uzaklık sayısına yönelik bir işaretçi. Genellikle değeri 1 ' dir, ancak tek bir Il yönergesi birden çok `CALL` derleme yönergesiyle eşleyebilirsiniz.  
  
 `pOffsets`  
 Yerel uzaklık dizisi. Genellikle, `pOffsets` tek bir konum içerir, ancak tek bir Il yönergesi birden `CALL` çok derleme yönergesiyle birden çok haritaya eşlenir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, başvuru türü döndüren bir yöntemin dönüş değerini almak için [ICorDebugILFrame3:: Getreturnvalueforılsapmasını](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) yöntemi ile birlikte kullanılır. Bir işlev çağrısı sitesine bir Il uzaklığının bu yönteme geçirilmesi bir veya daha fazla yerel uzaklık döndürür. Hata ayıklayıcı daha sonra işlevdeki bu yerel kaydırmalar üzerinde kesme noktaları ayarlayabilir. Hata ayıklayıcı kesme noktalarından birine geçtiğinde, dönüş değerini almak için bu yönteme geçirdiğiniz Il sapmasını [ICorDebugILFrame3:: Getreturnvalueforılsapmasını](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) yöntemine geçirebilirsiniz. Hata ayıklayıcı daha sonra, ayarlandığı tüm kesme noktalarını temizlemelidir.  
  
> [!WARNING]
> Ve ICorDebugILFrame3 [:: getreturnvalueforılsapmasını](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) yöntemleri yalnızca başvuru türleri için dönüş değeri bilgilerini almanızı sağlar. `ICorDebugCode3::GetReturnValueLiveOffset` Değer türlerinden dönüş değeri bilgileri alma (yani, öğesinden <xref:System.ValueType>türetilen tüm türler) desteklenmez.  
  
 İşlevi, aşağıdaki tabloda `HRESULT` gösterilen değerleri döndürür.  
  
|`HRESULT`deeri|Açıklama|  
|---------------------|-----------------|  
|`S_OK`|Başarılı.|  
|`CORDBG_E_INVALID_OPCODE`|Verilen Il konum sitesi bir çağrı yönergesi değil veya işlev döndürüyor `void`.|  
|`CORDBG_E_UNSUPPORTED`|Verilen Il kayması uygun bir çağrıdır, ancak dönüş türü bir dönüş değeri almak için desteklenmez.|  
  
 `ICorDebugCode3::GetReturnValueLiveOffset` Yöntemi yalnızca x86 tabanlı ve AMD64 sistemlerinde kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platform** Bkz. [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi** CorDebug. IDL, CorDebug. h  
  
 **Kitaplığı** Corguid. lib  
  
 **.NET Framework sürümleri:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [GetReturnValueForILOffset Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)
- [ICorDebugCode3 Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
