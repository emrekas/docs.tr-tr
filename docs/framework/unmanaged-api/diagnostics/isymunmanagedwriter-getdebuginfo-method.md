---
title: ISymUnmanagedWriter::GetDebugInfo Yöntemi
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8737885015055994bff3f6066bccb551f19f74f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777313"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>ISymUnmanagedWriter::GetDebugInfo Yöntemi
Hata ayıklama dizin girdisi taşınabilir yürütülebilir (PE) dosya üst bilgisinde yazmak bir derleyici için gerekli bilgileri döndürür. Sembol yazıcı dışındaki tüm alanları doldurur `TimeDateStamp` ve `PointerToRawData`. (Derleyici bu iki alan uygun şekilde ayarlamaktan sorumludur.)  
  
 Bir derleyici bu yöntemi çağırın, PE dosyasının işlem veri blobunu yayma, Ayarla `PointerToRawData` yayılan bir veri noktası ve IMAGE_DEBUG_DIRECTORY PE dosyasına yazmak için IMAGE_DEBUG_DIRECTORY alanındaki. Derleyici ayrıca ayarlamanız gerekir `TimeDateStamp` eşit alan `TimeDateStamp` PE dosyasının oluşturulmasını.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pIDD`  
 [out içinde] Sembol yazıcı dolduracak bir IMAGE_DEBUG_DIRECTORY işaretçisi.  
  
 `cData`  
 [in] A `DWORD` , hata ayıklama verilerin boyutunu içerir.  
  
 `pcData`  
 [out] Bir işaretçi bir `DWORD` hata ayıklama veri içermesini gerekli arabellek boyutunu alır.  
  
 `data`  
 [out] Sembol deposu için hata ayıklama verileri tutabilecek kadar büyük arabellek için işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa S_OK; Aksi takdirde, E_FAIL veya başka bir hata kodu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Üst bilgi:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ISymUnmanagedWriter Arabirimi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
