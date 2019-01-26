---
title: Başlangıç Ayarları Şeması
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: e5f9c9af64ff38e7c0f1f26ccab039261b052e30
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083424"
---
# <a name="startup-settings-schema"></a>Başlangıç Ayarları Şeması

Başlangıç ayarları, uygulamanın çalışması gereken ortak dil çalışma zamanı sürümünü belirtin.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<requiredRuntime >](requiredruntime-element.md)|Uygulama yalnızca sürüm 1.0 ortak dil çalışma zamanının desteklediğini belirtir. Çalışma zamanı sürüm 1.1 ile oluşturulan uygulamaların kullanması gereken  **\<supportedRuntime >** öğesi.|  
|[\<supportedRuntime >](supportedruntime-element.md)|Uygulamanın hangi ortak dil çalışma zamanı sürümünü desteklediğini belirtir.|  
|[\<Başlangıç >](startup-element.md)|İçeren  **\<requiredRuntime >** ve  **\<supportedRuntime >** öğeleri.|  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Yapılandırma Dosyası Şeması](../index.md)
- [Nasıl yapılır: Bir uygulamayı .NET Framework 4 veya sonraki sürümler destekleyecek şekilde yapılandırma](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
