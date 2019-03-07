---
title: GUID_ManagedName Özniteliği
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48ad6e4d1d03d8362123e65f16907880b18893f9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496397"
---
# <a name="guidmanagedname-attribute"></a>GUID_ManagedName Özniteliği
Bileşen Nesne Modeli (COM) kitaplığı için yönetilen ad alanı adını belirten bir özel arabirim özniteliği tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a>Parametreler  
 `value`  
 Kitaplığı yönetilen bir ad alanı adı.  
  
## <a name="definition"></a>Tanım  
 `GUID_ManagedName` içinde COR.h şu şekilde tanımlanır:  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Özel arabirim özniteliği tür kitaplığında bir nesne için meta verileri tanımlar.  
  
 Kullanım <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> veya <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> özniteliğinden yönetilen adı alınamadı.  
  
 Daha fazla bilgi için [arabirim öznitelikleri](/cpp/windows/interface-attributes) Visual c++'ta başvuru belgeleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir kitaplık tanımı kullanarak gösterir `GUID_ManagedName` özniteliği.  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Üst bilgi:** COR.h
