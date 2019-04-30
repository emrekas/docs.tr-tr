---
title: .NET Framework ve Bant Dışı Yayınlar
ms.date: 10/10/2018
ms.assetid: 721f10fa-3189-4124-a00d-56ddabd889b3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6bf92e118d2ef02c0dc3a550c084e2a0a8e0e3d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644001"
---
# <a name="the-net-framework-and-out-of-band-releases"></a>.NET Framework ve Bant Dışı Yayınlar

.NET Framework, Windows Phone ve Windows Mağazası uygulamaları yanı sıra geleneksel masaüstü ve web uygulamaları ve kod tekrar kullanımını en üst düzeye çıkarmak üzere farklı platformlara uyum sağlamak için gelişiyor. Normal .NET Framework yayınlarımızın yanı sıra, platformlar arası geliştirmeyi geliştirmek veya yeni işlevsellikler eklemek için yeni özellikleri bant dışı (OOB) yayınlarız. Bu konu, .NET Framework ve OOB sürümlerinin gelecekteki yönelimlerini tartışır.

## <a name="advantages-of-oob-releases"></a>OOB sürümlerinin avantajları
 Yeni bileşenleri veya bant dışı bileşenlerin güncellemeleri, Microsoft'un .NET Framework'e daha sık güncelleme sağlamasına olanak tanır. Buna ek olarak, müşteri geri bildirimlerini toplayıp olabildiğince hızlı yanıtlayabiliyoruz.

 Uygulamanızda bir OOB özelliğini kullanırsanız, OOB derlemeleri uygulama paketinizle birlikte dağıtıldığından, kullanıcılarınızın uygulamanızı çalıştırmak için .NET Framework'ün son sürümünü yüklemeleri gerekmez.

## <a name="how-oob-packages-are-distributed"></a>OOB paketleri nasıl dağıtılır?
Çekirdek ortak dil çalışma zamanı (CLR) bileşenleri için OOB sürümleri aracılığıyla dağıtılır [NuGet](https://www.nuget.org/), .NET için Paket Yöneticisi olan. NuGet, Visual Studio'daki Çözüm Gezgini'nden .NET Framework projelerinize kolaylıkla göz atmanıza ve kitaplıklar eklemenize olanak sağlar. NuGet, Visual Studio 2012'den itibaren tüm Visual Studio sürümleriyle birlikte gelir. NuGet'ın yüklü olup olmadığını görmek için nelere **NuGet Paket Yöneticisi** Visual Studio **Araçları** menüsü. Yüklü değilse:

1. Visual Studio menü çubuğunda **Araçları**, **Uzantılar ve güncelleştirmeler** (Visual Studio 2010'da seçin **Uzantı Yöneticisi**).

     **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.

2. Seçin **çevrimiçi**, **NuGet Paket Yöneticisi**ve ardından **indirme**.

3. Karşıdan yükleme tamamlandıktan sonra Visual Studio'yu yeniden başlatın.

 Ayrıntılı yükleme yönergeleri için bkz. [NuGet yükleme](/nuget/install-nuget-client-tools) NuGet belgeleri Web sitesinde. NuGet hakkında daha fazla bilgi için bkz. [NuGet belgeleri](/nuget).

## <a name="using-a-nuget-oob-package"></a>NuGet OOB paketini kullanma
 NuGet yükledikten sonra, Visual Studio'da Çözüm Gezgini'ni kullanarak NuGet paketlerine göz atabilir ve başvurular ekleyebilirsiniz:

1. Visual Studio'da projeniz için kısayol menüsünü açın ve ardından **NuGet paketlerini Yönet**. (Bu seçenek ayrıca kullanılabilir **proje** menü.)

2. Sol bölmede seçin **çevrimiçi**.

3. Orta bölmede aşağı açılan liste kutusunda yayın öncesi paketleri kullanmak isterseniz, seçin **öncesini** yerine **yalnızca durağan**.

4. Sağ bölmede, kullanmak **arama** kutusunu kullanmak istediğiniz paketi bulmak için. Bazı Microsoft paketleri, Microsoft .NET Framework logosu ile tanımlanır ve tümü Microsoft'u yayımcı olarak tanımlar.

 ![NuGet Paket Yöneticisi'ni gösteren ekran görüntüsü.](./media/the-net-framework-and-out-of-band-releases/nuget-package-manager-dialog.png)

 Daha önce belirtildiği gibi, OOB paketi kullanan bir uygulamayı dağıttığınızda OOB derlemeleri, uygulama paketinizle birlikte sevk edilir.

## <a name="types-of-oob-releases"></a>OOB sürümlerinin türleri
 Genellikle, bir OOB paketi bir veya daha fazla yayın öncesi sürüm ve kararlı bir sürüm içerir. Bir ön sürümle birlikte verilen lisans genellikle yeniden dağıtıma izin vermeyip değil, ancak bir paket denemenize ve geribildirim sağlamanıza olanak sağlar. Geribildirim, pakete yapılan tüm güncelleştirmelere eklenmiştir. Son sürüm NuGet ile bir kararlı paket olarak dağıtılır ve NuGet paketini uygulamanızla yeniden dağıtmanıza olanak sağlayan bir lisans içerir. Kararlı paketler Microsoft tarafından desteklenir. Microsoft, IntelliSense desteğinin yanı sıra diğer blog gönderilerini gibi belge türlerini sağlar ve forum tüm paketler için yanıtlar. Ayrıca, kaynak kodu bazı, tümü değil, paketlerle kullanılabilir. Yeni ve güncelleştirilmiş paketleri ile ilgili Duyurular almak için abone olabileceğiniz [.NET Framework blogu](https://devblogs.microsoft.com/dotnet/).

 Ön sürüm ve kararlı paketler bulmak için **öncesini** NuGet Paket Yöneticisi'nde.

 Kararlı paket sürümleri size bildirilmesini istiyorsanız, abone [.NET Framework akışına](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).

## <a name="see-also"></a>Ayrıca bkz.

- [Başlarken](../../../docs/framework/get-started/index.md)