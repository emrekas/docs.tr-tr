---
title: ICorProfilerInfo3::GetRuntimeInformation Metodu
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7087864d0305f0cdb0b4977f037cf5a7c4dee18d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783137"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>ICorProfilerInfo3::GetRuntimeInformation Metodu
Profili oluşturulan ortak dil çalışma zamanı (CLR) sürüm bilgilerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pClrInstanceId`  
 [out] Bir işlemde çalışan bir CLR örneği temsilcisi kimliği. Bu, aynı `ClrInstanceID` Windows (ETW) başlangıç olayı için olay izleme olduğunu bildirir.  
  
 `pRuntimeType`  
 [out] Çalışma zamanı türü. Bu parametre döndürür `COR_PRF_DESKTOP_CLR` Masaüstü CLR sürümü için veya `COR_PRF_CORE_CLR` çekirdek Silverlight'ta kullanılan CLR sürümü için.  
  
 `pMajorVersion`  
 [out] CLR sürüm sayısı.  
  
 `pMinorVersion`  
 [out] İkincil sürüm numarası CLR.  
  
 `pBuildVersion`  
 [out] Derleme sürüm numarası CLR.  
  
 `pQFEVersion`  
 [out] Bir yazılım güncelleştirmesiyle ilişkili CLR sürüm sayısı.  
  
 `cchVersionString`  
 [in] Arabelleğin karakter cinsinden uzunluğu, `szVersionString` işaret eder.  
  
 `pcchVersionString`  
 [out] Karakter cinsinden uzunluğu, `szVersionString`.  
  
 `szVersionString`  
 [out] CLR sürüm dizesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Her parametre için null değeri geçirmeye. Ancak, `pcchVersionString` null olamaz sürece `szVersionString` de null.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorProfilerInfo3 Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Profil Oluşturma Arabirimleri](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profil Oluşturma](../../../../docs/framework/unmanaged-api/profiling/index.md)
