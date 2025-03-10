---
title: Performans Sayaçları ve Devam Eden Yan Yana Uygulamalar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- performance counters
- performance counters,and in-process side-by-side applications
- performance,.NET Framework applications
- performance monitoring,counters
ms.assetid: 6888f9be-c65b-4b03-a07b-df7ebdee2436
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c583e9568a55b994f0516af2dcdf29f0d0f21fb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967272"
---
# <a name="performance-counters-and-in-process-side-by-side-applications"></a>Performans Sayaçları ve Devam Eden Yan Yana Uygulamalar
Performans Izleyicisi 'ni (Perfmon. exe) kullanarak, performans sayaçlarını çalışma zamanına göre ayırmak mümkündür. Bu konuda, bu işlevi etkinleştirmek için gereken kayıt defteri değişikliği açıklanmaktadır.  
  
## <a name="the-default-behavior"></a>Varsayılan davranış  
 Varsayılan olarak performans Izleyicisi, performans sayaçlarını uygulama başına temelinde görüntüler. Bununla birlikte, bunun sorunlu olduğu iki senaryo vardır:  
  
- Aynı ada sahip iki uygulamayı izlerken. Örneğin, her iki uygulama da MyApp. exe olarak adlandırılmışsa, birisi **MyApp** olarak ve diğeri ise **örnek** sütununda **MyApp # 1** olarak görüntülenir. Bu durumda, bir performans sayacını belirli bir uygulamayla eşleştirmek zordur. **MyApp # 1** için toplanan verilerin ilk MyApp. exe ' ye veya ikinci MyApp. exe ' ye başvuruda bulunup olmaması net değildir.  
  
- Bir uygulama ortak dil çalışma zamanının birden çok örneğini kullandığında. .NET Framework 4, işlem içi yan yana barındırma senaryolarını destekler; diğer bir deyişle, tek bir işlem veya uygulama ortak dil çalışma zamanının birden çok örneğini yükleyebilir. MyApp. exe adlı tek bir uygulama iki çalışma zamanı örneği yüklerse varsayılan olarak **MyApp** ve **MyApp # 1**olarak **örnek** sütununda atanır. Bu durumda, **MyApp** ve **MyApp # 1** ' in aynı ada sahip iki uygulamayı ya da iki çalışma alanıyla aynı uygulamayı ifade etmeksizin net değildir. Aynı ada sahip birden çok uygulama birden fazla çalışma zamanı yüklese, belirsizlik daha da büyüktür.  
  
 Bu belirsizliği ortadan kaldırmak için bir kayıt defteri anahtarı ayarlayabilirsiniz. .NET Framework 4 kullanılarak geliştirilen uygulamalar için, bu kayıt defteri değişikliği bir işlem tanımlayıcısı ve ardından bir çalışma zamanı örneği tanımlayıcısı, **örnek** sütunundaki uygulama adına eklenir. Uygulama veya *uygulama*#1 yerine, uygulama artık **örnek** sütununda *Application*_`p`*ProcessId*\_`r`*runtimeId* olarak tanımlanır. Bir uygulama, ortak dil çalışma zamanının önceki bir sürümü kullanılarak geliştirilmişse, bu örnek .NET Framework 4 ' ün yüklü olduğu *\_uygulama*`p`*işlem kimliği* olarak gösterilir.  
  
## <a name="performance-counters-for-in-process-side-by-side-applications"></a>Işlem Içi yan yana uygulamalar için performans sayaçları  
 Tek bir uygulamada barındırılan birden çok ortak dil çalışma zamanı sürümü için performans sayaçlarını işlemek üzere, aşağıdaki tabloda gösterildiği gibi tek bir kayıt defteri anahtarı ayarını değiştirmeniz gerekir.  
  
|||  
|-|-|  
|Anahtar adı|HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\. NETFramework\Performance|  
|Değer adı|ProcessNameFormat|  
|Değer türü|REG_DWORD|  
|Değer|1 (0x00000001)|  
  
 İçin `ProcessNameFormat` 0 değeri, varsayılan davranışın etkinleştirildiğini gösterir; yani, Perfmon. exe performans sayaçlarını uygulama başına temelinde görüntüler. Bu değeri 1 olarak belirlediğinizde, Perfmon. exe, bir uygulamanın birden çok sürümünü belirsizlaştırır ve çalışma zamanı başına performans sayaçlarını sağlar. `ProcessNameFormat` Kayıt defteri anahtarı ayarı için başka bir değer desteklenmez ve gelecekte kullanılmak üzere ayrılmıştır.  
  
 `ProcessNameFormat` Kayıt defteri anahtarı ayarını güncelleştirdikten sonra, yeni örnek adlandırma özelliğinin düzgün çalışması için perfmon. exe ' yi veya herhangi bir performans sayacı tüketicilerini yeniden başlatmanız gerekir.  
  
 Aşağıdaki örnek, programlı olarak `ProcessNameFormat` değerin nasıl değiştirileceğini gösterir.  
  
 [!code-csharp[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/cs/regsetting1.cs#1)]
 [!code-vb[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/vb/regsetting1.vb#1)]  
  
 Bu kayıt defteri değişikliğini yaptığınızda Perfmon. exe, .NET Framework 4 ' ü *uygulama*`p`_*İşlemKimliği*\_`r`*runtimeId*olarak hedefleyen uygulamaların adlarını görüntüler, burada *uygulama* uygulamanın adı, *İşlemKimliği* uygulamanın işlem tanımlayıcısıdır ve *runtimeId* ortak bir dil çalışma zamanı tanımlayıcısıdır. Örneğin, MyApp. exe adlı bir uygulama ortak dil çalışma zamanının iki örneğini yüklerse, Perfmon. exe bir örneği myapp_p1416_r10 ve ikincisi myapp_p3160_r10 olarak tanımlayabilir. Çalışma zamanı tanımlayıcısı yalnızca bir işlemdeki çalışma zamanlarını belirsizlaştırır; çalışma zamanı hakkında başka herhangi bir bilgi sağlamaz. (Örneğin, çalışma zamanı KIMLIĞI, çalışma zamanının sürümü veya SKU 'SU ile ilişkili değildir.)  
  
 .NET Framework 4 yüklüyse, kayıt defteri değişikliği, .NET Framework önceki sürümleri kullanılarak geliştirilen uygulamaları da etkiler. Bunlar, *application_* `p`*İşlemKimliği*olarak Perfmon. exe ' de görünür; burada *uygulama* uygulama adı ve *İşlemKimliği* işlem tanımlayıcısıdır. Örneğin, MyApp. exe adlı iki uygulamanın performans sayaçları izleniyorsa, biri myapp_p23900 ve diğeri myapp_p24908 olarak görünebilir.  
  
> [!NOTE]
> İşlem tanımlayıcısı, çalışma zamanının önceki sürümlerini kullanan aynı ada sahip iki uygulamanın çözümlenme belirsizliğin ortadan kaldırır. Ortak dil çalışma zamanının önceki sürümleri yan yana senaryoları desteklemediğinden, önceki sürümler için bir çalışma zamanı tanımlayıcısı gerekli değildir.  
  
 .NET Framework 4 yoksa veya kaldırılmışsa, kayıt defteri anahtarının ayarlanması etkisizdir. Bu, aynı ada sahip iki uygulamanın, *uygulama* ve *1. uygulama* (örneğin, **MyApp** ve **MyApp # 1**olarak) olarak Perfmon. exe ' de görünmeye devam edemeyeceği anlamına gelir.
