---
title: Birlikte Çalışma Hazırlama
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, COM interop
- interop marshaling
- interop marshaling, about interop marshaling
ms.assetid: 115f7a2f-d422-4605-ab36-13a8dd28142a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20766f4f7971d8aa304c7c3eead94f089f059d64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946713"
---
# <a name="interop-marshaling"></a>Birlikte Çalışma Hazırlama
<a name="top"></a>Birlikte çalışma sıralama, verilerin Yöntem bağımsız değişkenlerine nasıl geçtiğini ve çağrılar sırasında yönetilen ve yönetilmeyen bellek arasında değer döndürme şeklini yönetir. Birlikte çalışabilirlik sıralaması, ortak dil çalışma zamanının sıralama hizmeti tarafından gerçekleştirilen bir çalışma zamanı etkinliğidir.  
  
 Çoğu veri türü hem yönetilen hem de yönetilmeyen bellekte ortak temsiller vardır. Birlikte çalışma sıralayıcısı sizin için bu türleri işler. Diğer türler, yönetilen bellekte belirsiz veya hiç gösterilemez.  
  
 Belirsiz bir tür, tek bir yönetilen türle eşlenen birden çok yönetilmeyen temsilden ya da bir dizinin boyutu gibi eksik tür bilgilerine sahip olabilir. Belirsiz türler için sıralayıcı, birden fazla temsilin bulunduğu varsayılan bir temsili ve alternatif gösterimleri sağlar. Sıralayıcıya, belirsiz bir tür sıralama yapmak için açık yönergeler sağlayabilirsiniz.  
  
 Bu genel bakış aşağıdaki bölümleri içerir:  
  
- [Platform çağırma ve COM birlikte çalışma modelleri](#platform_invoke_and_com_interop_models)  
  
- [Hazırlama ve COM Apartments](#marshaling_and_com_apartments)  
  
- [Uzak çağrıları sıralama](#marshaling_remote_calls)  
  
- [İlgili konular](#related_topics)  
  
- [Başvuru](#reference)  
  
<a name="platform_invoke_and_com_interop_models"></a>   
## <a name="platform-invoke-and-com-interop-models"></a>Platform çağırma ve COM birlikte çalışma modelleri  
 Ortak dil çalışma zamanı, yönetilmeyen kod ile birlikte çalışmak için iki mekanizma sağlar:  
  
- Yönetilen kodun yönetilmeyen bir kitaplıktan aktarılmış işlevleri çağırmasına olanak sağlayan platform çağırma.  
  
- Yönetilen kodun arabirimler aracılığıyla bileşen nesne modeli (COM) nesneleriyle etkileşime geçmesini sağlayan COM birlikte çalışma.  
  
 Hem platform Invoke hem de COM birlikte çalışması, yöntem bağımsız değişkenlerini çağıran ve çağrılan ve geri dönüş arasında doğru şekilde taşımak için birlikte çalışabilirlik sıralamasını kullanır. Aşağıdaki çizimde gösterildiği gibi, platform çağırma yöntemi, yönetilen 'den yönetilmeyen koda ve [geri çağırma işlevlerinin](callback-functions.md) dahil olduğu durumlar dışında, hiçbir zaman başka bir şekilde yapılır. Platform çağırma çağrıları yalnızca yönetilene yönetilmeyen koda akabilse de, veriler giriş veya çıkış parametreleri olarak her iki yönde de akabilir. COM birlikte çalışma yöntemi çağrıları her iki yönde de akabilir.  
  
 ![Platform çağırma](./media/interop-marshaling/interop-marshaling-invoke-and-com.png "Platform çağırma ve com birlikte çalışma çağrı akışı")  
  
 En düşük düzeyde, her iki mekanizma de aynı birlikte çalışma sıralama hizmetini kullanır; Ancak, belirli veri türleri yalnızca COM birlikte çalışma veya platform çağırma tarafından desteklenir. Ayrıntılar için bkz. [varsayılan sıralama davranışı](default-marshaling-behavior.md).  
  
 [Başa dön](#top)  
  
<a name="marshaling_and_com_apartments"></a>   
## <a name="marshaling-and-com-apartments"></a>Hazırlama ve COM Apartments  
 Birlikte çalışma sıralayıcısı, verileri ortak dil çalışma zamanı yığını ve yönetilmeyen yığın arasında sıralar. Sıralama, çağıran ve çağrılan aynı veri örneğinde çalışamadığında oluşur. Birlikte çalışma sıralayıcısı, çağıran ve çağrılan tarafından verilerin kendilerine ait bir kopyasına sahip olsalar bile aynı verilerde çalışıyor olmasını mümkün kılar.  
  
 COM Ayrıca, verileri COM apartmanları veya farklı COM işlemleri arasında sıraladığında bir Sıralayıcı içerir. Aynı COM grubu içindeki yönetilen ve yönetilmeyen kod arasında çağrılırken, birlikte çalışma sıralayıcısı dahil tek Sıralayıcı olur. Yönetilen kod ve yönetilmeyen kod arasında farklı bir COM grubu ya da farklı bir işlemde çağrılırken, birlikte çalışma sıralayıcısı ve COM sıralayıcısı dahil edilir.  
  
### <a name="com-clients-and-managed-servers"></a>COM Istemcileri ve yönetilen sunucular  
 [Regasm. exe (derleme kayıt aracı)](../tools/regasm-exe-assembly-registration-tool.md) tarafından kaydedilmiş bir tür kitaplığına sahip, aktarılmış bir yönetilen sunucuda, olarak `ThreadingModel` `Both`ayarlanmış bir kayıt defteri girişi vardır. Bu değer, sunucunun tek iş parçacıklı bir grupta (STA) veya çok iş parçacıklı grupta (MTA) etkinleştiribileceğini belirtir. Sunucu nesnesi, aşağıdaki tabloda gösterildiği gibi çağıranı ile aynı grupta oluşturulur.  
  
|COM istemcisi|.NET Server|Hazırlama gereksinimleri|  
|----------------|-----------------|-----------------------------|  
|A|`Both`STA olur.|Aynı apartman sıralaması.|  
|SIRAYA|`Both`MTA olur.|Aynı apartman sıralaması.|  
  
 İstemci ve sunucu aynı grupta olduğundan, birlikte çalışma hazırlama hizmeti tüm veri sıralamasını otomatik olarak işler. Aşağıdaki çizimde, aynı COM stili apartman içinde yönetilen ve yönetilmeyen Heap 'ler arasında çalışan birlikte çalışma sıralama hizmeti gösterilmektedir.  
  
 ![Yönetilen ve yönetilmeyen Heap 'ler arasında birlikte çalışabilirlik sıralaması](./media/interop-marshaling/interop-heaps-managed-and-unmanaged.gif "Aynı apartman sıralama işlemi")  
  
 Yönetilen bir sunucuyu dışarı aktarmayı planlıyorsanız, COM istemcisinin sunucunun bulunduğu grubu belirlediğini unutmayın. Bir MTA içinde başlatılan bir COM istemcisi tarafından çağrılan yönetilen bir sunucu, iş parçacığı güvenliği sağlamalıdır.  
  
### <a name="managed-clients-and-com-servers"></a>Yönetilen Istemciler ve COM sunucuları  
 Yönetilen istemci apartmanları için varsayılan ayar MTA ' dır; Ancak, .NET istemcisinin uygulama türü varsayılan ayarı değiştirebilir. Örneğin, Visual Basic istemci grubu ayarı STA ' dır. Yönetilen bir istemcinin grup <xref:System.STAThreadAttribute?displayProperty=nameWithType>ayarını incelemek <xref:System.MTAThreadAttribute?displayProperty=nameWithType>ve değiştirmek <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> için,, özelliğini <xref:System.Web.UI.Page.AspCompatMode%2A?displayProperty=nameWithType> veya özelliğini kullanabilirsiniz.  
  
 Bileşenin yazarı bir COM sunucusunun iş parçacığı benzeşimini ayarlar. Aşağıdaki tabloda .NET istemcileri ve COM sunucuları için Grup ayarları birleşimleri gösterilmektedir. Ayrıca, kombinasyonlar için elde edilen sıralama gereksinimlerini gösterir.  
  
|.NET istemcisi|COM sunucusu|Hazırlama gereksinimleri|  
|-----------------|----------------|-----------------------------|  
|MTA (varsayılan)|SIRAYA<br /><br /> A|Birlikte çalışma hazırlama.<br /><br /> Birlikte çalışabilirlik ve COM sıralaması.|  
|A|SIRAYA<br /><br /> A|Birlikte çalışabilirlik ve COM sıralaması.<br /><br /> Birlikte çalışma hazırlama.|  
  
 Yönetilen bir istemci ve yönetilmeyen sunucu aynı Apartment ise, birlikte çalışma hazırlama hizmeti tüm veri sıralamasını işler. Ancak, istemci ve sunucu farklı apartmanlar halinde başlatıldığında COM sıralaması de gereklidir. Aşağıdaki çizimde, bir çapraz grup çağrısının öğeleri gösterilmektedir.  
  
 ![Com sıralaması](./media/interop-marshaling/single-process-across-multi-apartment.gif ".Net ISTEMCISIYLE com nesnesi arasında çapraz grup çağrısı")  
  
 Çapraz grup sıralaması için şunları yapabilirsiniz:  
  
- Yalnızca sınır genelinde çok sayıda çağrı olduğunda dikkat çekici olan çapraz grup sıralaması yükünü kabul edin. Grup sınırını başarıyla çapraz olarak aramak için COM bileşeninin tür kitaplığını kaydetmeniz gerekir.  
  
- İstemci iş parçacığını STA veya MTA olarak ayarlayarak ana iş parçacığını değiştirin. Örneğin, C# istemciniz çok SAYıDA sta com bileşeni çağırırsa, ana Iş parçacığını STA olarak ayarlayarak geçici grup sıralamasını önleyebilirsiniz.  
  
    > [!NOTE]
    > Bir C# istemcinin Iş parçacığı STA olarak AYARLANDıĞıNDA, MTA COM bileşenlerine yapılan çağrılar, çapraz grup sıralaması gerektirir.  
  
 Bir grup modelini açıkça seçme yönergeleri için bkz. [yönetilen ve yönetilmeyen Iş parçacığı](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100)).  
  
 [Başa dön](#top)  
  
<a name="marshaling_remote_calls"></a>   
## <a name="marshaling-remote-calls"></a>Uzak çağrıları sıralama  
 Çapraz grup sıralaması gibi, nesneler ayrı işlemlerde olduğunda yönetilen ve yönetilmeyen kod arasındaki her çağrıya COM sıralaması dahil edilir. Örneğin:  
  
- Uzak bir konakta yönetilen bir sunucuyu çağıran bir COM istemcisi Dağıtılmış COM (DCOM) kullanır.  
  
- Uzak bir konakta bir COM sunucusu çağıran yönetilen istemci DCOM kullanır.  
  
 Aşağıdaki çizimde birlikte çalışabilirlik sıralaması ve COM sıralaması, işlem ve konak sınırları genelinde iletişim kanalları sağlar.  
  
 ![Com sıralaması](./media/interop-marshaling/interop-and-com-marshaling.gif "Çapraz işlem sıralaması")  
  
### <a name="preserving-identity"></a>Kimlik koruma  
 Ortak dil çalışma zamanı, yönetilen ve yönetilmeyen başvuruların kimliğini korur. Aşağıdaki çizimde, doğrudan yönetilmeyen başvuruların (üst satır) ve işlem ve konak sınırları genelinde doğrudan yönetilen başvuruların (alt satır) akışı gösterilmektedir.  
  
 ![Com çağrılabilir sarmalayıcı ve çalışma zamanı çağrılabilir sarmalayıcı](./media/interop-marshaling/interop-direct-ref-across-process.gif "İşlem ve konak sınırları arasında başvuru geçirme")  
  
 Bu çizimde:  
  
- Yönetilmeyen istemci, uzak bir ana bilgisayardan bu başvuruyu alan yönetilen bir nesneden bir COM nesnesine başvuru alır. Uzaktan iletişim mekanizması DCOM olur.  
  
- Yönetilen istemci, bir uzak ana bilgisayardan bu başvuruyu alan bir COM nesnesinden yönetilen bir nesneye başvuru alır. Uzaktan iletişim mekanizması DCOM olur.  
  
    > [!NOTE]
    > Yönetilen sunucunun dışarıya aktarılmış tür kitaplığı kayıtlı olmalıdır.  
  
 Çağıran ve çağrılan arasındaki işlem sınırları sayısı ilgisizdir; işlem içi ve işlem dışı çağrılar için aynı doğrudan başvuru oluşur.  
  
### <a name="managed-remoting"></a>Yönetilen uzaktan erişim  
 Çalışma zamanı ayrıca yönetilen uzaktan iletişim sağlar, bu da işlem ve konak sınırları arasında yönetilen nesneler arasında bir iletişim kanalı oluşturmak için kullanabilirsiniz. Yönetilen uzaktan iletişim, aşağıdaki çizimde gösterildiği gibi, iletişim kuran bileşenler arasında bir güvenlik duvarına uyum sağlayabilir.  
  
 ![SOAP veya TcpChannel](./media/interop-marshaling/interop-remote-soap-or-tcp.gif "SOAP veya TcpChannel sınıfı kullanarak güvenlik duvarları genelinde uzaktan çağrılar")  
SOAP veya TcpChannel sınıfı kullanarak güvenlik duvarları genelinde uzaktan çağrılar  
  
 Bazı yönetilmeyen çağrılar, hizmet verilen bileşenler ve COM arasındaki çağrılar gibi SOAP üzerinden channe, olabilir.  
  
 [Başa dön](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Varsayılan Hazırlama Davranışı](default-marshaling-behavior.md)|Birlikte çalışma sıralama hizmetinin verileri sıralamak için kullandığı kuralları açıklar.|  
|[Platform Çağırma ile Veri Hazırlama](marshaling-data-with-platform-invoke.md)|Yöntem parametrelerinin nasıl bildirilemeyeceğini ve yönetilmeyen kitaplıklar tarafından dışarıya alınan işlevlere bağımsız değişkenlerin nasıl geçirileceğini açıklar.|  
|[COM Birlikte Çalışma ile Verileri Hazırlama](marshaling-data-with-com-interop.md)|Sıralama davranışının değiştirmek için COM sarmalayıcılarının nasıl özelleştirileceğini açıklar.|  
|[Nasıl yapılır: Yönetilen kod DCOM 'u WCF 'ye geçirme](how-to-migrate-managed-code-dcom-to-wcf.md)|DCOM 'dan WCF 'ye geçiş işlemini açıklar.|  
|[Nasıl yapılır: HRESULTs ve özel durumları eşleme](how-to-map-hresults-and-exceptions.md)|Özel özel durumların HRESULTs ile nasıl eşlenmesinin ve .NET Framework her HRESULT 'den karşılaştırılabilen özel durum sınıfına tüm eşlemeyi nasıl sağladığını açıklar.|  
|[Genel türler kullanılarak birlikte çalışma](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))|COM birlikte çalışabilirlik için genel türler kullanılırken hangi eylemlerin desteklendiğini açıklar.|  
|[Yönetilmeyen Kod ile Birlikte Çalışma](index.md)|Ortak dil çalışma zamanı tarafından sunulan birlikte çalışabilirlik hizmetlerini açıklar.|  
|[Gelişmiş COM birlikte çalışabilirlik](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))|.NET Framework uygulamanıza COM bileşenlerini ekleme hakkında daha fazla bilgi için bağlantılar sağlar.|  
|[Birlikte çalışabilirlik için tasarım konuları](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))|Tümleşik COM bileşenleri yazmak için ipuçları sağlar.|  
  
 [Başa dön](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a>Başvuru  
 <xref:System.Runtime.InteropServices?displayProperty=nameWithType>  
  
 [Başa dön](#top)
