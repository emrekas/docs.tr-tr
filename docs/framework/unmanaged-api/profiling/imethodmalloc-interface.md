---
title: IMethodMalloc Arabirimi
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c67ce15175f8667139f99cec1ed17531eab473e1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935656"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc Arabirimi
Yeni bir Microsoft ara dili (MSIL) işlev gövdesi için bellek ayırmak üzere bir yöntem sağlar.  
  
> [!NOTE]
> `IMethodMalloc` Arabirim basit bir bellek ayırıcıdır. Bellek ayırmayı, ancak serbest bırakmanıza izin vermez.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Alloc Yöntemi](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|Yeni bir MSIL işlev gövdesi için belirtilen miktarda bellek ayırmaya çalışır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Her ayırıcı modüle özeldir ve işlev gövdesinin, modülün temelini pozitif bir uzaklığa göre olacağını sağlar. Modülün temel aldığı bellek çok değerli olabilir, bu nedenle ayırıcı yalnızca bir işlev gövdesi için bellek ayırmak için kullanılmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platform** Bkz. [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi** CorProf. IDL, CorProf. h  
  
 **Kitaplığı** Corguid. lib  
  
 **.NET Framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Profil Oluşturma Arabirimleri](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
