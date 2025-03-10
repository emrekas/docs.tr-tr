---
title: EClrOperation Numaralandırması
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01b000ed3d75ddb6a7882cb8f03ff2cec64fb9fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767881"
---
# <a name="eclroperation-enumeration"></a>EClrOperation Numaralandırması
Bir ana bilgisayar ilkesi eylemleri uygulayabilirsiniz işlemleri açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|Ne zaman gerçekleştirilecek eylemleri ilke belirtebilir bir <xref:System.AppDomain> (rude) normal olmayan bir şekilde kaldırıldı.|  
|`OPR_AppDomainUnload`|Ne zaman gerçekleştirilecek eylemleri ilke belirtebilir bir <xref:System.AppDomain> kaldırılır.|  
|`OPR_FinalizerRun`|Konak sonlandırıcılar çalıştırdığınızda, gerçekleştirilecek eylemleri İlkesi belirtebilirsiniz.|  
|`OPR_ProcessExit`|Ana bilgisayar işlemi olduğunda gerçekleştirilecek eylemleri İlkesi belirtebilirsiniz.|  
|`OPR_ThreadAbort`|Konak, bir iş parçacığı durduruldu olduğunda gerçekleştirilecek eylemleri İlkesi belirtebilirsiniz.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Konak rude iş parçacığı durdurma kodu kritik bir bölgede olduğunda gerçekleştirilecek eylemleri İlkesi belirtebilirsiniz.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Ana bilgisayar olması kritik olmayan bir kod bölgede rude iş parçacığı iptal ortaya çıktığında ilke eylemler belirtebilirsiniz.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ortak dil çalışma zamanı (CLR) güvenilirlik altyapısı iptal eder ve kaynak arasında kritik bölge kodu ve kod kritik olmayan bölgelerde ortaya oluşan ayırma hatalarını ayırır. Bu ayrım, bir hata kodu nerede oluştuğunu bağlı olarak farklı ilkeleri ayarlamak konakları izin vermek için tasarlanmıştır.  
  
 A *kritik bölge kodu* herhangi alanı burada CLR garanti etmez, bir görevi iptal etme veya şu anki görevini kaynakları etkiler isteği tamamlayamıyor. Bir görev bir kilit ve bellek ayırma isteği yapan bağlı hata olduğunu gösteren bir HRESULT alır, örneğin, bu yalnızca kararlılığını emin olmak için bu görevi iptal etmek yetersizdir <xref:System.AppDomain>, çünkü <xref:System.AppDomain> diğer içerebilir aynı kilit için bekleyen görevler. Görev geçerli iptal etmek için bu diğer görevlerin yanıt vermeyi durdurmasına neden olabilir. Böyle bir durumda, konak tüm kaldırma yeteneği olması gerekir. <xref:System.AppDomain> risk olası kararsızlığı yerine.  
  
 A *kritik olmayan bölge kodu*, diğer taraftan, CLR burada garanti yalnızca bağlı hata oluşursa görev bir iptal ya da başarısızlık etkiler bir bölgedir.  
  
 CLR ayrıca arasında düzgün ve başarılı olmayan (rude) iptalleri ayırır. Genel olarak, normal veya normal iptal rude durdurma gibi garanti yaparken, bir görev iptal edilmeden önce özel durum işleme rutinleri ve sonlandırıcılar çalıştırmak için her türlü çabayı gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MSCorEE.h  
  
 **Kitaplığı:** MSCorEE.dll  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [EClrFailure Sabit Listesi](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EPolicyAction Sabit Listesi](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Barındırma Sabit Listeleri](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
