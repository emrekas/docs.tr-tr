---
title: CorElementType Sabit Listesi1
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 581c5517144dbc94e16acb777b5c272b8390b212
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091141"
---
# <a name="corelementtype-enumeration1"></a>CorElementType Sabit Listesi1
Ortak dil çalışma zamanı belirtir <xref:System.Type>, bir tür değiştiricisi ya da bir türü bir meta veri türü imzada hakkında bilgiler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef enum CorElementType {  
    ELEMENT_TYPE_END            = 0x0,  
    ELEMENT_TYPE_VOID           = 0x1,  
    ELEMENT_TYPE_BOOLEAN        = 0x2,  
    ELEMENT_TYPE_CHAR           = 0x3,  
    ELEMENT_TYPE_I1             = 0x4,  
    ELEMENT_TYPE_U1             = 0x5,  
    ELEMENT_TYPE_I2             = 0x6,  
    ELEMENT_TYPE_U2             = 0x7,  
    ELEMENT_TYPE_I4             = 0x8,  
    ELEMENT_TYPE_U4             = 0x9,  
    ELEMENT_TYPE_I8             = 0xa,  
    ELEMENT_TYPE_U8             = 0xb,  
    ELEMENT_TYPE_R4             = 0xc,  
    ELEMENT_TYPE_R8             = 0xd,  
    ELEMENT_TYPE_STRING         = 0xe,  
  
    ELEMENT_TYPE_PTR            = 0xf,  
    ELEMENT_TYPE_BYREF          = 0x10,  
  
    ELEMENT_TYPE_VALUETYPE      = 0x11,  
    ELEMENT_TYPE_CLASS          = 0x12,  
    ELEMENT_TYPE_VAR            = 0x13,  
    ELEMENT_TYPE_ARRAY          = 0x14,  
    ELEMENT_TYPE_GENERICINST    = 0x15,  
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,  
  
    ELEMENT_TYPE_I              = 0x18,  
    ELEMENT_TYPE_U              = 0x19,  
    ELEMENT_TYPE_FNPTR          = 0x1B,  
    ELEMENT_TYPE_OBJECT         = 0x1C,  
    ELEMENT_TYPE_SZARRAY        = 0x1D,  
    ELEMENT_TYPE_MVAR           = 0x1e,  
  
    ELEMENT_TYPE_CMOD_REQD      = 0x1F,  
    ELEMENT_TYPE_CMOD_OPT       = 0x20,  
  
    ELEMENT_TYPE_INTERNAL       = 0x21,  
    ELEMENT_TYPE_MAX            = 0x22,  
  
    ELEMENT_TYPE_MODIFIER       = 0x40,  
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,  
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER  
  
} CorElementType;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|Dahili olarak kullanılır.|  
|`ELEMENT_TYPE_VOID`|Void türü.|  
|`ELEMENT_TYPE_BOOLEAN`|Bir Boolean türü|  
|`ELEMENT_TYPE_CHAR`|Bir karakter türü.|  
|`ELEMENT_TYPE_I1`|İmzalı bir 1 baytlık tamsayı.|  
|`ELEMENT_TYPE_U1`|İşaretsiz bir 1 baytlık tamsayı.|  
|`ELEMENT_TYPE_I2`|İmzalı bir 2-bayt tamsayı.|  
|`ELEMENT_TYPE_U2`|İmzalanmamış 2-bayt tamsayı.|  
|`ELEMENT_TYPE_I4`|İmzalı bir 4 baytlık tamsayı.|  
|`ELEMENT_TYPE_U4`|İşaretsiz bir 4 baytlık tamsayı.|  
|`ELEMENT_TYPE_I8`|İşaretli 8-bayt tamsayı.|  
|`ELEMENT_TYPE_U8`|İmzalanmamış 8-bayt tamsayı.|  
|`ELEMENT_TYPE_R4`|4-bayt kayan nokta.|  
|`ELEMENT_TYPE_R8`|Bir 8-bayt kayan nokta.|  
|`ELEMENT_TYPE_STRING`|System.String türü.|  
|`ELEMENT_TYPE_PTR`|Bir işaretçi türü değiştiricisi.|  
|`ELEMENT_TYPE_BYREF`|Bir başvuru türü değiştiricisi.|  
|`ELEMENT_TYPE_VALUETYPE`|Değer tür değiştiricisi.|  
|`ELEMENT_TYPE_CLASS`|Bir sınıf türü değiştiricisi.|  
|`ELEMENT_TYPE_VAR`|Bir sınıf değişken tür değiştiricisi.|  
|`ELEMENT_TYPE_ARRAY`|Çok boyutlu dizi tür değiştiricisi.|  
|`ELEMENT_TYPE_GENERICINST`|Genel türler için tür değiştiricisi.|  
|`ELEMENT_TYPE_TYPEDBYREF`|Belirlenmiş bir başvuru.|  
|`ELEMENT_TYPE_I`|Yerel bir tamsayı boyutu.|  
|`ELEMENT_TYPE_U`|Yerel bir işaretsiz tamsayı boyutu.|  
|`ELEMENT_TYPE_FNPTR`|Bir işlev işaretçisi.|  
|`ELEMENT_TYPE_OBJECT`|System.Object türü.|  
|`ELEMENT_TYPE_SZARRAY`|Tek boyutlu, sıfır alt sınırı dizi tür değiştiricisi.|  
|`ELEMENT_TYPE_MVAR`|Bir yöntem değişken tür değiştiricisi.|  
|`ELEMENT_TYPE_CMOD_REQD`|C dili değiştiricisi gereklidir.|  
|`ELEMENT_TYPE_CMOD_OPT`|Bir C dili isteğe bağlı bir değiştirici.|  
|`ELEMENT_TYPE_INTERNAL`|Dahili olarak kullanılır.|  
|`ELEMENT_TYPE_MAX`|Geçersiz bir tür.|  
|`ELEMENT_TYPE_MODIFIER`|Dahili olarak kullanılır.|  
|`ELEMENT_TYPE_SENTINEL`|Değişken bir dizi parametre listesi için bir sentinel olan bir tür değiştiricisi.|  
|`ELEMENT_TYPE_PINNED`|Dahili olarak kullanılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tür değiştiricileri daha karmaşık türleri temsil eden temelini oluşturur. A `CorElementType` tür değiştiricisi değeri, türü imzada hemen takip eden değerine uygulanır. Aşağıdaki değeri `CorElementType` tür değiştiricisi değeri olabilir bir `CorElementType` basit tür değeri, bir metaveri belirteci veya aşağıdaki tabloda belirtildiği gibi başka bir değer.  
  
> [!NOTE]
>  Tüm sayılar (*numarası*, *bağımsız değişken sayısı*, *meta veri belirteci*, *derece*, *sayısı*ve *bağlı*) sıkıştırılmış tamsayı olarak depolanır. Bkz: [standart ECMA-335 - ortak dil altyapısı (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) ECMA Web sitesinde Ayrıntılar için.  
  
|Tür değiştiricisi|Biçimi|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR < bir `CorElementType` değer >|  
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF < bir `CorElementType` değer >|  
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE < bir `mdTypeDef` meta veri belirteci >|  
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS < bir `mdTypeDef` meta veri belirteci >|  
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR \<sayı >|  
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY < bir `CorElementType` değer > \<derece > \<count1 > \<bound1 >... \<countN > \<boundN >|  
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST < bir `mdTypeDef` meta veri belirteci > \<bağımsız değişken sayısı > \<arg1 >... \<argN >|  
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR \<çağırma kuralı dahil olmak üzere işlev için tam imza >|  
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY < bir `CorElementType` değer >|  
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR \<sayı >|  
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_ < bir `mdTypeRef` veya `mdTypeDef` meta veri belirteci >|  
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT < bir `mdTypeRef` veya `mdTypeDef` meta veri belirteci >|  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorHdr.h  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Meta Veri Sabit Listeleri](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
