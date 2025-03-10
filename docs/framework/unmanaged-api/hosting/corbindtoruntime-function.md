---
title: CorBindToRuntime İşlevi
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8ed3a85d12d35bb4779297a7bbc94ce911accef
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767977"
---
# <a name="corbindtoruntime-function"></a>CorBindToRuntime İşlevi
Ortak dil çalışma zamanı (CLR) bir işleme yüklemek için yöneilmeyen ana bilgisayarları etkinleştirir.  
  
 Bu işlev .NET Framework 4'te kullanım dışıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pwszVersion`  
 [in] Yüklemek istediğiniz CLR sürümünü tanımlayan dize.  
  
 .NET Framework uygulamasındaki sürüm numarası noktayla ayrılmış dört bölümden oluşur: *major.minor.build.revision*. Olarak geçen dize `pwszVersion` (örneğin, "v1.0.1529") sürüm numarasının ilk üç parçalar tarafından izlenen "v" karakteriyle başlamalıdır.  
  
 CLR'nin bazı sürümleri, CLR'nin önceki sürümleriyle uyumluluğu belirten bir ilke bildirimiyle birlikte yüklenir. Varsayılan olarak, başlangıç dolgusu değerlendirir `pwszVersion` ilke bildirimlerine ve yükleri karşı çalışma zamanının en son sürümü olan istenen sürümle uyumlu. Bir konak ilke değerlendirmesini atlamaya ve belirtilen tam sürümü yüklemeye zorlayabilir `pwszVersion` değerini geçirerek `STARTUP_LOADER_SAFEMODE` için `flags` aşağıda açıklandığı gibi parametre.  
  
 Arayan için null belirtiyorsa `pwszVersion`, çalışma zamanının en son sürümü yüklendi. Null geçirme konak çalışma zamanının yüklendiği üzerinde hiçbir denetimi sağlar. Bu yaklaşım bazı senaryolarda uygun olsa da, konağın belirli bir sürümünü yüklemek için sağlamanız önerilir.  
  
 `pwszBuildFlavor`  
 [in] Sunucunun veya CLR çalışma istasyonu yapısı yükleneceğini belirten bir dize. Geçerli değerler `svr` ve `wks`. Sunucu yapısı çöp toplama için birden çok işlemciden yararlanmak için optimize edilmiştir ve çalışma istasyonu yapısı tek işlemcili makinede çalışan istemci uygulamaları için optimize edilmiştir.  
  
 Varsa `pwszBuildFlavor` ayarlamak null iş istasyonu derlemesi yüklenir. İş istasyonu yapısı, bir tek işlemcili makinede çalışırken daima yüklenir, bile `pwszBuildFlavor` ayarlanır `svr`. Ancak, varsa `pwszBuildFlavor` ayarlanır `svr` ve eş zamanlı çöp toplama belirtilmişse (açıklamasına bakın `flags` parametresi), sunucu yapısı yüklenir.  
  
 `rclsid`  
 [in] `CLSID` Ya da uygulayan yardımcı sınıf, [Icorruntimehost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) veya [Iclrruntimehost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) arabirimi. Desteklenen değerler: clsıd_corruntimehost veya clsıd_clrruntimehost şunlardır.  
  
 `riid`  
 [in] `IID` , İstenen arabiriminden `rclsid`. Desteklenen değerler: ııd_ıcorruntimehost veya ııd_ıclrruntimehost şunlardır.  
  
 `ppv`  
 [out] Döndürülen arabirim işaretçisi `riid`.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `pwszVersion` mevcut değil, bir çalışma zamanı sürümünü belirten `CorBindToRuntimeEx` CLR_E_SHIM_RUNTIMELOAD bir HRESULT değerini döndürür.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Yürütme bağlamı ve Windows Identity akışı  
 CLR sürüm 1 <xref:System.Security.Principal.WindowsIdentity> nesne yeni iş parçacığı, iş parçacığı havuzları ya da Zamanlayıcı geri çağırmaları gibi zaman uyumsuz noktalar arasında akış değil. CLR 2.0 sürümünde bir <xref:System.Threading.ExecutionContext> nesne yürütülmekte olan iş parçacığını hakkında bazı bilgiler sarmalar ve herhangi bir zaman uyumsuz noktası arasında ancak olmayan uygulama etki alanı sınırları üzerinden akar. Benzer şekilde, <xref:System.Security.Principal.WindowsIdentity> nesne de herhangi bir zaman uyumsuz noktası üzerinden akar. Bu nedenle, iş parçacığı üzerinde geçerli kimliğe bürünme varsa, çok akar.  
  
 Flow'a iki şekilde değiştirebilirsiniz:  
  
1. Değiştirerek <xref:System.Threading.ExecutionContext> akışını bir iş parçacığı başına temelinde bastırmak için ayarları (bkz <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, ve <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> yöntemleri).  
  
2. Sürüm 1 uyumluluk modu için varsayılan işlem modu değiştirerek burada <xref:System.Security.Principal.WindowsIdentity> nesne akan tüm zaman uyumsuz noktası üzerinden açmamasından <xref:System.Threading.ExecutionContext> ayarlar geçerli iş parçacığı üzerinde. Varsayılan mod nasıl değiştirmeniz mi yönetilen bir yürütülebilir dosya veya yönetilmeyen bir barındırma arabiriminin CLR'yi yüklemek için kullandığınıza bağlıdır:  
  
    1. Yönetilen yürütülebilir dosyalar için ayarlamanız gerekir `enabled` özniteliği [ \<Legacyımpersonationpolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) öğesine `true`.  
  
    2. Yönetilmeyen barındırma arabirimleri için ayarlanan `STARTUP_LEGACY_IMPERSONATION` bayrağını `flags` çağırırken parametre `CorBindToRuntimeEx` işlevi.  
  
     Sürüm 1 uyumluluk modu, tüm işlem ve işlemde tüm uygulama etki alanları için geçerlidir.  
  
## <a name="remarks"></a>Açıklamalar  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) ve `CorBindToRuntime` aynı işlemi gerçekleştirmek ancak `CorBindToRuntimeEx` işlevi CLR'nin davranışını belirtmek için bayrakları ayarlamanızı sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MSCorEE.h  
  
 **Kitaplığı:** MSCorEE.dll  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [CorBindToCurrentRuntime İşlevi](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeByCfg İşlevi](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx İşlevi](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost İşlevi](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost Arabirimi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Kullanım Dışı CLR Barındırma İşlevleri](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
