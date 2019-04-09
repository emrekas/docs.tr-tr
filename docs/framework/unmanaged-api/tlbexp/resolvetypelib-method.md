---
title: ResolveTypeLib Yöntemi
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d734f35b5878ec39e4f2159c326283d168e3be2b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197899"
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib Yöntemi
Basit bir tür kitaplığı adı, tam nitelenmiş bir yol döndürerek çözümler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a>Parametreler  
 `bstrSimpleName`  
 [in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) içeren basit tür kitaplığı adı.  
  
 `tlbid`  
 [in] Kayıt defterinde tür kitaplığına atanan GUID.  
  
 `lcid`  
 [in] Tür kitaplığının yerelleştirme kimliği.  
  
 `wMajorVersion`  
 [in] Tür kitaplığı sürüm sayısı. Örneğin, sürüm için *x.y*, ana sürüm numarası *x*.  
  
 `wMinorVersion`  
 [in] Tür kitaplığının ikincil sürüm numarası. Örneğin, sürüm için *x.y*, ikincil sürüm numarası *y*.  
  
 `syskind`  
 [in] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) işletim ortamını belirten bayrak. Genel değerler şunlardır: SYS_WIN32 ve SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 [out] Bir işaretçi bir [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) adlı tür kitaplığının tam yolu içeren `bstrSimpleName` parametresi.  
  
## <a name="remarks"></a>Açıklamalar  
 `ResolveTypeLib` Yöntemi tarafından çağrılır [LoadTypeLibWithResolver işlevi](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) sırasında [Tlbexp.exe (tür kitaplığı dışarı Aktarıcı)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) işleniyor.  
  
 Bu arabirim özel uygulamaları döndürmelidir bir [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) adlı tür kitaplığının tam yolu içeren `bstrSimpleName` parametresi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** TlbRef.idl, TlbRef.h  
  
 **Kitaplığı:** TlbRef.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Tlbexp Yardımcı İşlevleri](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
