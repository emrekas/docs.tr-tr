---
title: CorAttributeTargets Numaralandırması
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fb1dff80fccc920540d370797441b3a019d766c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780916"
---
# <a name="corattributetargets-enumeration"></a>CorAttributeTargets Numaralandırması
Üzerinde bir öznitelik uygulamak için geçerli olduğundan uygulama öğesi belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =   
        catAssembly | catModule | catClass | catStruct |   
        catEnum | catConstructor | catMethod | catProperty |   
        catField | catEvent | catInterface | catParameter |   
        catDelegate | catGenericParameter,  
  
    catClassMembers        =   
        catClass | catStruct | catEnum | catConstructor |   
        catMethod | catProperty | catField | catEvent |   
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`catAssembly`|Öznitelik bir bütünleştirilmiş koda uygulanabilir.|  
|`catModule`|Öznitelik, bir taşınabilir yürütülebilir (.dll veya .exe) modülü için uygulanabilir.|  
|`catClass`|Öznitelik bir sınıfa uygulanabilir.|  
|`catStruct`|Öznitelik, bir yapıya uygulanabilir; diğer bir deyişle, bir değer yazın.|  
|`catEnum`|Öznitelik, bir numaralandırma için uygulanabilir.|  
|`catConstructor`|Öznitelik, bir oluşturucu için uygulanabilir.|  
|`catMethod`|Öznitelik, bir yönteme uygulanabilir.|  
|`catProperty`|Öznitelik, bir özellik için uygulanabilir.|  
|`catField`|Öznitelik, bir alan için uygulanabilir.|  
|`catEvent`|Öznitelik, bir olay için uygulanabilir.|  
|`catInterface`|Öznitelik, bir arabirim için uygulanabilir.|  
|`catParameter`|Öznitelik, bir parametre için uygulanabilir.|  
|`catDelegate`|Öznitelik, bir temsilci için uygulanabilir.|  
|`catGenericParameter`|Genel parametre özniteliği uygulanabilir.|  
|`catAll`|Öznitelik, herhangi bir uygulama öğeye uygulanabilir.|  
|`catClassMembers`|Öznitelik, bir sınıf üyesine uygulanabilir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CorAttributeTargets` Numaralandırma değerlerinin tercih edilen birleşimi almak için bit düzeyinde bir veya işlem ile birleştirilebilir.  
  
 `CorAttributeTargets` Yönetilen parallels <xref:System.AttributeTargets?displayProperty=nameWithType> sabit listesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorHdr.h  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Meta Veri Sabit Listeleri](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
