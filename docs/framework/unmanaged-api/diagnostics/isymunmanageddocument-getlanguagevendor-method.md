---
title: ISymUnmanagedDocument::GetLanguageVendor Metodu
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd01dcbd45ecae84ccccffb510c20f580ae8c598
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080815"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a>ISymUnmanagedDocument::GetLanguageVendor Metodu
Bu belgenin dil satıcı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Dil satıcı alan bir değişken için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa S_OK.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ISymUnmanagedDocument Arabirimi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
