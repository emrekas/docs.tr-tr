---
title: .NET Framework Uygulamalarında Önbelleğe Alma
ms.date: 03/30/2017
helpviewer_keywords:
- ASP.NET caching
- caching [.NET Framework]
- caching [ASP.NET]
ms.assetid: c4b47ee0-4b82-4124-9bce-818088385e34
ms.openlocfilehash: 779785e9793939cf121fedf99b23a07288173637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967599"
---
# <a name="caching-in-net-framework-applications"></a>.NET Framework Uygulamalarında Önbelleğe Alma
Önbelleğe alma, verileri hızlı erişim için bellekte depolamanıza olanak sağlar. Verilere yeniden erişildiğinde, uygulamalar verileri özgün kaynaktan almak yerine önbellekten alabilir. Bu, performansı ve ölçeklenebilirliği iyileştirebilir. Ayrıca, veri kaynağı geçici olarak kullanılamadığında önbelleğe alma verilerin kullanılabilir olmasını sağlar.  
  
 .NET Framework, ASP.NET dahil olmak üzere hem Windows istemci hem de sunucu uygulamalarının performansını ve ölçeklenebilirliğini artırmak için kullanabileceğiniz önbelleğe alma işlevselliği sağlar.  
  
> [!NOTE]
> .NET Framework 3,5 ve önceki sürümlerde, ASP.net <xref:System.Web.Caching> ad alanında bellek içi önbellek uygulamasını sağladı. .NET Framework önceki sürümlerinde, önbelleğe alma yalnızca <xref:System.Web> ad alanında kullanılabilir ve bu nedenle ASP.net sınıflarında bir bağımlılık gerektirdi. .NET Framework 4 ' te, <xref:System.Runtime.Caching> ad alanı hem Web hem de Web 'e ait olmayan uygulamalar için tasarlanan API 'leri içerir.  
  
## <a name="caching-data"></a>Verileri Önbelleğe Alma  
 <xref:System.Runtime.Caching> Ad alanındaki sınıfları kullanarak bilgileri önbelleğe alabilirsiniz. Bu ad alanındaki önbelleğe alma sınıfları aşağıdaki özellikleri sağlar:  
  
- Özel önbellek uygulamaları oluşturmak için temel sağlayan soyut türler.  
  
- Somut bellek içi nesne önbelleği uygulama.  
  
 Soyut temel önbelleğe alma sınıfı (<xref:System.Runtime.Caching.ObjectCache>) aşağıdaki önbelleğe alma görevlerini tanımlar:  
  
- Önbellek girişleri oluşturma ve yönetme.  
  
- Süre sonu ve çıkarma bilgilerini belirtme.  
  
- Önbellek girdilerindeki değişikliklere yanıt olarak oluşturulan olayları tetikleyerek.  
  
 Sınıfı, <xref:System.Runtime.Caching.ObjectCache> sınıfının bellek içi nesne önbelleği uygulamasıdır. <xref:System.Runtime.Caching.MemoryCache> En çok önbelleğe alma <xref:System.Runtime.Caching.MemoryCache> görevleri için sınıfını kullanabilirsiniz.  
  
> [!NOTE]
> Sınıfı, <xref:System.Web.Caching> ad alanında tanımlanan ASP.net Cache nesnesi üzerinde modellenir. <xref:System.Runtime.Caching.MemoryCache> Bu nedenle, ASP.NET 'in önceki sürümlerinde sağlanmış mantığa benzer iç önbelleğe alma mantığı.  
  
 WPF uygulamasında önbelleğe alma için kullanmanın bir örneği için bkz [. İzlenecek yol: Bir WPF uygulamasında](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)uygulama verilerini önbelleğe alma.  
  
## <a name="caching-in-aspnet-applications"></a>ASP.NET uygulamalarında önbelleğe alma  
 <xref:System.Runtime.Caching> Ad alanındaki önbelleğe alma sınıfları, ASP.NET içinde verileri önbelleğe alma işlevselliği sağlar.  
  
> [!NOTE]
> Uygulamanız .NET Framework 3,5 veya önceki bir sürümü hedefliyorsa, <xref:System.Web.Caching> ad alanında tanımlanan önbelleğe alma sınıflarını kullanmanız gerekir. Daha fazla bilgi için bkz. [ASP.net Caching Overview](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).  
  
> [!NOTE]
> Yeni uygulamalar geliştirirken <xref:System.Runtime.Caching.MemoryCache> sınıfını kullanmanızı öneririz. <xref:System.Runtime.Caching> Ad alanında belirtilen API, <xref:System.Web.Caching.Cache> ad alanında sağlanmış olan API 'ye benzer. Bu nedenle, ASP.NET 'in önceki sürümlerinde önbelleğe alma kullandıysanız API tanıdık gelecektir. ASP.NET uygulamalarında önbelleğe alma özelliğinin kullanımına ilişkin bir örnek için bkz [. İzlenecek yol: Uygulama verilerini ASP.NET](https://docs.microsoft.com/previous-versions/ff477235(v=vs.100))içinde önbelleğe alma.  
  
### <a name="output-caching"></a>Çıktıyı önbelleğe alma  
 Uygulama verilerini el ile önbelleğe almak için, ASP.NET içinde <xref:System.Runtime.Caching.MemoryCache> sınıfını kullanabilirsiniz. ASP.NET ayrıca, bellek içinde sayfaların, denetimlerin ve HTTP yanıtlarının üretilen çıkışını depolayan çıkış önbelleğe almayı destekler. Çıktıyı önbelleğe alma işlemini bildirimli olarak bir ASP.NET Web sayfasında veya Web. config dosyasındaki ayarları kullanarak yapılandırabilirsiniz. Daha fazla bilgi için bkz. [önbelleğe alma Için OutputCache öğesi (ASP.NET Settings şeması)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms228124(v=vs.100)).  
  
 ASP.NET, özel çıkış önbelleği sağlayıcıları oluşturarak çıktı önbelleğe almayı genişletmenizi sağlar. Özel sağlayıcılar kullanarak, önbelleğe alınmış içeriği diskler, bulut depolaması ve dağıtılmış önbellek motorları gibi diğer depolama cihazlarını kullanarak saklayabilirsiniz. Özel bir çıktı önbelleği sağlayıcısı oluşturmak için, <xref:System.Web.Caching.OutputCacheProvider> sınıfından türeten bir sınıf oluşturur ve uygulamayı özel çıkış önbelleği sağlayıcısını kullanacak şekilde yapılandırırsınız.  
  
## <a name="caching-in-wcf-rest-services"></a>WCF REST hizmetlerinde önbelleğe alma  
 WCF REST Hizmetleri için .NET Framework, ASP.NET ' de bulunan bildirime dayalı çıktı önbelleği avantajlarından yararlanmanıza olanak sağlar. Bu, WCF REST hizmet işlemlerinizin yanıtlarını önbelleğe almanıza olanak sağlar. Kullanıcı, önbelleğe alma için yapılandırılmış bir hizmete HTTP GET isteği gönderdiğinde, ASP.NET önbelleğe alınmış yanıtı geri gönderir ve hizmet yöntemi çağrılmaz. Önbelleğin süresi dolduktan sonra, bir Kullanıcı bir HTTP GET isteği gönderdiğinde, hizmet yönteminiz çağrılır ve yanıt yeniden önbelleğe alınır.  
  
 .NET Framework Ayrıca Koşullu HTTP alma önbelleği uygulamanıza olanak sağlar. REST senaryolarında, hizmetler tarafından [http belirtiminde](https://go.microsoft.com/fwlink/?LinkId=165800)açıklandığı gıbı akıllı http önbelleği uygulamak için genellikle kullanılan koşullu BIR http get isteği kullanılır. Daha fazla bilgi için bkz. [WCF Web HTTP Hizmetleri Için önbelleğe alma desteği](https://go.microsoft.com/fwlink/?LinkId=184598).  
  
## <a name="extending-caching-in-the-net-framework"></a>.NET Framework önbelleğe almayı genişletme  
 .NET Framework önbelleğe alma, genişletilebilir olacak şekilde tasarlanmıştır. Sınıfı <xref:System.Runtime.Caching.ObjectCache> , özel önbellek uygulamaları oluşturmanıza olanak sağlar. Bu sınıf, Windows Forms, Windows Presentation Foundation (WPF) ve Windows Communications Foundation (WCF) dahil olmak üzere tüm yönetilen uygulamalar için kullanılabilen üyeleri sağlar. Bunu, farklı bir depolama mekanizması kullanan bir önbellek sınıfı oluşturmak için veya önbellek işlemleri üzerinde ayrıntılı denetim istiyorsanız yapabilirsiniz.  
  
 Önbelleğe almayı genişletmek için şunları yapabilirsiniz:  
  
- <xref:System.Runtime.Caching.ObjectCache> Sınıfından türeten özel bir sınıf oluşturun ve ardından türetilmiş sınıfta özel bir önbellek uygulamasını sağlayın.  
  
- <xref:System.Runtime.Caching.MemoryCache> Sınıfından türeten bir sınıf oluşturun ve türetilmiş sınıfı özelleştirin veya genişletin. Bunun nasıl yapılacağı hakkında bir örnek için bkz. [bir ASP.NET uygulamasında birden çok Cache nesnesi kullanarak uygulama verilerini önbelleğe alma](https://blogs.msdn.com/aspnetue/archive/2010/03/22/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application.aspx).  
  
- <xref:System.Web.Caching.OutputCacheProvider> Sınıfından türeten bir sınıf oluşturun ve uygulamayı özel çıkış önbelleği sağlayıcısını kullanacak şekilde yapılandırın.  
  
 Daha fazla bilgi için Scott Guthrie 'nin bloguna [ASP.NET 4 (VS 2010 ve .net 4,0 serisi) Ile Genişletilebilir çıkış önbelleği](https://go.microsoft.com/fwlink/?LinkId=185772) girişi bölümüne bakın.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching.MemoryCache>
- [İzlenecek yol: WPF uygulamasında uygulama verilerini önbelleğe alma](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
- [İzlenecek yol: Uygulama verilerini ASP.NET içinde önbelleğe alma](https://docs.microsoft.com/previous-versions/ff477235(v=vs.100))
