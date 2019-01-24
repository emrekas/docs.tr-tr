---
title: ICLRDataTarget3::GetExceptionContextRecord Metodu
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d55fd042cf478c6b3e39298f84f5a931bb346a74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585451"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>ICLRDataTarget3::GetExceptionContextRecord Metodu
Hedef işlemle ilişkilendirilmiş bağlam kaydını almak için ortak dil çalışma zamanı (CLR) veri erişim Hizmetleri tarafından çağrılır. Örneğin, bir döküm hedef için bu aracılığıyla iletilen bağlam kaydı eşdeğer olacaktır `ExceptionParam` bağımsız değişkeni [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) işlev kitaplığında Windows hata ayıklama yardımcı (DbgHelp).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `bufferSize`  
 [in] Giriş arabelleği bayt cinsinden boyutu. Bu bağlam kaydı tutabilecek kadar büyük olmalıdır.  
  
 `bufferUsed`  
 [out] Bir işaretçi bir `ULONG32` gerçekte arabelleğe yazılan bayt sayısı alan türü.  
  
 `buffer`  
 [out] Bağlam kaydını bir kopyasını alır bir ara belleğe yönelik işaretçi. Özel durum kaydını olarak döndürülen bir [bağlam](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) türü.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri `S_OK` başarı veya hata üzerinde `HRESULT` kodu. `HRESULT` Kodları içerebilir ancak şu şekilde sınırlı değildir:  
  
|Dönüş kodu|Açıklama|  
|-----------------|-----------------|  
|`S_OK`|Yöntem başarılı oldu. Bağlam kaydı için çıkış arabelleği kopyalandı.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Hedefle ilişkili hiçbir bağlam kaydıdır.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Giriş arabelleği boyutu, bağlam kaydı tutabilecek kadar büyük değil.|  
  
## <a name="remarks"></a>Açıklamalar  
 [BAĞLAM](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) olan Windows SDK'sı tarafından sağlanan üstbilgileri içinde tanımlanan bir platforma özgü yapısı.  
  
 Bu yöntem, hata ayıklama uygulamanın yazıcı tarafından uygulanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** ClrData.idl, ClrData.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- [ICLRDataTarget3 Arabirimi](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [GetExceptionRecord Yöntemi](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
- [GetExceptionThreadID Yöntemi](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
