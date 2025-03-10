---
title: Derleme Yüklerini Çözme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], resolving loads
- application domains, loading assemblies
- resolving assembly loads
- assemblies [.NET Framework], loading
- application domains, resolving assembly loads
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3844f3f1f4135167ac5575dafb4ba63a19b8b55e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927913"
---
# <a name="resolving-assembly-loads"></a>Derleme Yüklerini Çözme
.NET Framework, derleme yüklemesi <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> üzerinde daha fazla denetim gerektiren uygulamalar için olayı sağlar. Uygulamanız, bu olayı işleyerek, yük bağlamına normal yoklama yollarının dışından bir derleme yükleyebilir, kaç tane derleme sürümünden hangilerinin yükleneceğini seçebilir, dinamik bir derlemeyi yayarak ve bu şekilde devam edebilir. Bu konu, <xref:System.AppDomain.AssemblyResolve> olayı işlemeye yönelik rehberlik sağlar.  
  
> [!NOTE]
> Yalnızca yansıma bağlamındaki derleme yüklerini çözümlemek için, bunun yerine <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType> olayını kullanın.  
  
## <a name="how-the-assemblyresolve-event-works"></a>AssemblyResolve olayı nasıl kullanılır?  
 <xref:System.AppDomain.AssemblyResolve> Olay için bir işleyici kaydettiğinizde, çalışma zamanı bir derlemeye ada göre bağlama başarısız olduğunda işleyici çağrılır. Örneğin, aşağıdaki yöntemleri kullanıcı kodundan çağırmak <xref:System.AppDomain.AssemblyResolve> olayın oluşturulmasına neden olabilir:  
  
- İlk bağımsız değişkeni, <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> yüklenecek derlemenin görünen adını temsil eden bir dize olan bir <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> yöntem aşırı yüklemesi veya yöntem aşırı yüklemesi (yani, özelliği tarafından döndürülen dize).  
  
- İlk bağımsız değişkeni yüklenecek <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> derlemeyi tanımlayan bir nesne olan bir <xref:System.Reflection.AssemblyName> yöntem aşırı yüklemesi veya yöntem aşırı yüklemesi. <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
- Bir <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> yöntem aşırı yüklemesi.  
  
- Başka <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> bir <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> uygulama etki alanındaki bir nesneyi örnekleyen bir veya yöntem aşırı yüklemesi.  
  
### <a name="what-the-event-handler-does"></a>Olay Işleyicisinin yaptığı  
 <xref:System.AppDomain.AssemblyResolve> Olay işleyicisi, <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> özelliğindeki, yüklenecek derlemenin görünen adını alır. İşleyici derleme adını tanımıyorsa, null döndürür (`Nothing` Visual Basic, `nullptr` görselde C++).  
  
 İşleyici derleme adını tanırsa, isteği karşılayan bir derlemeyi yükleyebilir ve döndürebilir. Aşağıdaki listede bazı örnek senaryolar açıklanmaktadır.  
  
- İşleyici derlemenin bir sürümünün konumunu biliyorsa, <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> veya <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> yöntemini kullanarak derlemeyi yükleyebilir ve başarılı olursa yüklenen derlemeyi döndürebilir.  
  
- İşleyicinin bayt dizileri olarak depolanan derlemelerin bir veritabanına erişimi varsa, bir bayt dizisi alan aşırı yüklerden birini <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> kullanarak bir bayt dizisi yükleyebilir.  
  
- İşleyici dinamik bir derleme üretebilir ve döndürebilir.  
  
> [!NOTE]
> İşleyici, derlemeyi yük bağlamı içine, yük bağlamına veya Bağlamsız olarak yüklemesi gerekir. İşleyici, <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> veya yöntemini kullanarak derlemeyi yalnızca yansıma bağlamına yüklerse, <xref:System.AppDomain.AssemblyResolve> olayı oluşturan yükleme girişimi başarısız olur.  
  
 Bu, uygun bir derlemeyi döndürecek olay işleyicisinin sorumluluğundadır. İşleyici, <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> özellik değerini <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29> oluşturucuya geçirerek, istenen derlemenin görünen adını ayrıştırtırabilir. .NET Framework 4 ' ten başlayarak, işleyici, geçerli isteğin başka <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> bir derlemenin bağımlılığı olup olmadığını bulmak için özelliğini kullanabilir. Bu bilgiler, bağımlılığı karşılayan bir derlemeyi belirlemesine yardımcı olabilir.  
  
 Olay işleyicisi derlemenin farklı bir sürümünü istenen sürümden döndürebilir.  
  
 Çoğu durumda, işleyici tarafından döndürülen derleme, işleyicinin onu içine yüklediği bağlamdan bağımsız olarak yükleme bağlamında görünür. Örneğin, işleyici bir derlemeyi yük-from <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> bağlamına yüklemek için yöntemini kullanıyorsa, işleyici onu döndürdüğünde, derleme yükleme bağlamında görüntülenir. Ancak, aşağıdaki örnekte, işleyici onu döndürdüğünde derleme bağlam olmadan görünür:  
  
- İşleyici bağlamı olmayan bir derlemeyi yükler.  
  
- <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> Özellik null değil.  
  
- İstekte bulunan derleme (diğer bir deyişle, <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> özelliği tarafından döndürülen derleme), bağlamı olmadan yükleniydi.  
  
 Bağlamlar hakkında bilgi için bkz <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType> . yöntem aşırı yüklemesi.  
  
 Aynı derlemenin birden çok sürümü aynı uygulama etki alanına yüklenebilir. Tür atama sorunlarına yol açabildiğinden bu uygulama önerilmez. Bkz. [derleme yüklemesi Için En Iyi uygulamalar](../../../docs/framework/deployment/best-practices-for-assembly-loading.md).  
  
### <a name="what-the-event-handler-should-not-do"></a>Olay Işleyicisinin yapması gereken  
 <xref:System.AppDomain.AssemblyResolve> Olayı işlemeye yönelik birincil kural, tanımadığınız bir derlemeyi döndürmeye çalışmayın. İşleyiciyi yazdığınızda hangi derlemelerin olay oluşturulmasına neden olabileceğini bilmeniz gerekir. İşleyiciniz diğer derlemeler için null değer döndürmelidir.  
  
> [!IMPORTANT]
> .NET Framework 4 ' ten başlayarak, <xref:System.AppDomain.AssemblyResolve> etkinlik uydu derlemeleri için oluşturulur. Bu değişiklik, işleyici tüm derleme yükleme isteklerini çözümlemeye çalışırsa .NET Framework önceki bir sürümü için yazılmış bir olay işleyicisini etkiler. Tanımadığı derlemeleri yoksaymayan olay işleyicileri bu değişiklikten etkilenmez: Bunlar null döndürür ve normal geri dönüş mekanizmaları izlenir.  
  
 Bir derlemeyi yüklerken olay işleyicisi, <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> <xref:System.AppDomain.AssemblyResolve> olayın yinelemeli olarak oluşturulmasına neden olabilecek bir veya <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> yöntem aşırı yüklerini kullanmamalıdır, çünkü bu bir yığın taşmasına yol açabilir. (Bu konunun önceki kısımlarında sunulan listeye bakın.) Tüm olay işleyicileri döndürülünceye kadar hiçbir özel durum oluşturulmadığından, yükleme isteği için özel durum işleme sağlıyorsanız bile bu durum oluşur. Bu nedenle, aşağıdaki kod, bulunmazsa bir yığın taşmasına `MyAssembly` neden olur:  
  
 [!code-cpp[AssemblyResolveRecursive#1](../../../samples/snippets/cpp/VS_Snippets_CLR/assemblyresolverecursive/cpp/example.cpp#1)]
 [!code-csharp[AssemblyResolveRecursive#1](../../../samples/snippets/csharp/VS_Snippets_CLR/assemblyresolverecursive/cs/example.cs#1)]
 [!code-vb[AssemblyResolveRecursive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/assemblyresolverecursive/vb/example.vb#1)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Bütünleştirilmiş Kod Yükleme için En İyi Yöntemler](../../../docs/framework/deployment/best-practices-for-assembly-loading.md)
- [Uygulama Etki Alanlarını Kullanma](../../../docs/framework/app-domains/use.md)
