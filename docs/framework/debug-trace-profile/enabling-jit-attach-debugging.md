---
title: JIT-Ekleme Hata Ayıklamayı Etkinleştirme
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 005395beabd956767b59e0cebd563fe883f6fe53
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489793"
---
# <a name="enabling-jit-attach-debugging"></a>JIT-Ekleme Hata Ayıklamayı Etkinleştirme
JIT-ekleme hata ayıklamayı hatalarla ya da belirli yöntemler ve işlevlere tarafından tetiklenebilir bir hata ayıklayıcı bir işlemine iliştirme açıklamak için kullanılan ifade var.  
  
 JIT-ekleme hata ayıklamayı aşağıdaki hata koşulları altında kullanılır:  
  
- İşlenmeyen özel durumları (yerel ve yönetilen kod).  
  
- <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> yöntem veya [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) işlevi (Windows 7 ailesi).  
  
- Önemli hatalarla çalışma zamanı.  
  
 JIT-ekleme hata ayıklamayı aşağıdaki yöntemleri ve işlevleri yapılan çağrılar tarafından ayrıca başlatılır:  
  
- <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> yöntem.  
  
- <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> yöntem.  
  
- [DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) işlevi (Win32).  
  
 Önce .NET Framework 4 ve .NET Framework, yerel ve yönetilen hata ayıklayıcıları davranışını denetlemek için ayrı bir kayıt defteri anahtarları sağlanır. Denetim, .NET Framework 4 ile başlayarak, bir tek bir kayıt defteri anahtarı altında birleştirilir: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Bu anahtarı ayarlayabilirsiniz değerleri bir hata ayıklayıcı çağrılan, ve olup bu durumda, kullanıcı etkileşimi gerektiren bir iletişim kutusu çağrılır olup olmadığını belirler. Bu kayıt defteri anahtarı ayarlama hakkında daha fazla bilgi için bkz: [otomatik hata ayıklama yapılandırma](https://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Hata Ayıklama, İzleme ve Profil Oluşturma](../../../docs/framework/debug-trace-profile/index.md)
- [Görüntüde Hata Ayıklamayı Kolaylaştırma](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)
