---
title: Windows Forms'a Genel Bakış
ms.date: 03/30/2017
helpviewer_keywords:
- smart clients
- Windows Forms, about Windows Forms
ms.assetid: 3a2b6284-c8d6-4e1c-8c69-0bed38f38cd4
ms.openlocfilehash: 71bf50bdcf058e94981dc5df4731b5d32dcc2069
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487201"
---
# <a name="windows-forms-overview"></a>Windows Forms'a genel bakış

Aşağıdaki genel akıllı istemci uygulamaları, Windows Forms programlama ve günümüzde kuruluşların ve son kullanıcıların ihtiyaçlarını akıllı istemciler oluşturmak için Windows Forms nasıl kullanabileceğinizi ana özelliklerini avantajları anlatılmaktadır.

## <a name="windows-forms-and-smart-client-apps"></a>Windows Forms ve akıllı istemci uygulamaları

 Windows Forms ile akıllı istemciler geliştirin. *Akıllı istemciler* dağıtmak ve güncelleştirmek kolay bir görsel açıdan zengin uygulamalar bağlı veya bağlantısı kesilmiş Internet'ten çalışabilir ve yerel bilgisayardaki kaynaklara daha güvenli bir şekilde daha geleneksel erişebilirsiniz Windows tabanlı uygulamalar.

### <a name="build-rich-interactive-user-interfaces"></a>Zengin, etkileşimli kullanıcı arabirimleri oluşturun

 Windows Forms, .NET Framework, dosya sistemine yazma ve okuma gibi ortak uygulama görevleri basitleştirmek yönetilen kitaplıkları kümesi için bir akıllı istemci teknolojisidir. Visual Studio gibi bir geliştirme ortamı kullandığınızda, bir ağ üzerinden uzak bilgisayarlarla iletişim bilgilerini görüntülemek ve kullanıcıların giriş istek Windows Forms akıllı istemci uygulamaları oluşturabilirsiniz.

 Windows Forms'ta bir *form* üzerinde görüntü bilgileri kullanıcıya görsel bir yüzeydir. Normalde formlarına denetimler ekleme ve fare tıklamasına veya tuş basışlarını gibi kullanıcı eylemlerini yanıtlarını geliştirmeye göre Windows Forms uygulamaları oluşturun. A *denetimi* veri girişi kabul eder ya da veri görüntüleyen bir ayrık bir kullanıcı arabirimi (UI) öğesidir.

 Bir kullanıcı bir şey formunuza veya denetimlerinden birini yaptığında, eylem, bir olay oluşturur. Uygulamanız kod kullanarak bu olaylara yanıt verir ve bunlar ortaya çıktığında olayları işler. Daha fazla bilgi için [Windows Forms'ta olay işleyicileri oluşturma](creating-event-handlers-in-windows-forms.md).

 Windows Forms formlara ekleyebilirsiniz denetimleri çeşitli içerir: metin kutuları, düğmeler, aşağı açılan kutusu, radyo düğmeleri ve bile Web sayfalarını görüntüleyen denetimler. Bir form üzerinde kullanabileceğiniz tüm denetimleri listesi için bkz. [Windows Forms'da kullanılacak denetimler](./controls/controls-to-use-on-windows-forms.md). Varolan bir denetimi gereksinimlerinizi karşılamıyorsa, Windows Forms Ayrıca kendi özel denetimler kullanarak oluşturulmasını destekler <xref:System.Windows.Forms.UserControl> sınıfı.

 Windows Forms, yüksek kaliteli uygulamalar Microsoft Office gibi özellikleri öykünmek zengin kullanıcı Arabirimi denetimlerine sahiptir. Kullanırken <xref:System.Windows.Forms.ToolStrip> ve <xref:System.Windows.Forms.MenuStrip> denetimi araç çubuklarında ve menülerde menülerinde görüntülemek ve metin kutuları ve birleşik giriş kutuları gibi diğer denetimleri barındıran metin ve görüntüleri içeren oluşturabilirsiniz.

 Sürükle ve bırak ile **Windows Form Tasarımcısı** Visual Studio'da, Windows Forms uygulamaları kolayca oluşturabilirsiniz. Yalnızca imlecinizi denetimleriyle seçin ve form üzerinde istediğiniz yere ekleyin. Tasarımcı denetimleri hizalama dışında zahmetini için kılavuz çizgilerini ve ek satırlar gibi araçları sağlar. Visual Studio kullanıyorsanız veya komut satırında derleme olup olmadığını kullanabileceğiniz <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> ve <xref:System.Windows.Forms.SplitContainer> Gelişmiş oluşturmak için denetimleri form düzenlerini daha kısa sürede.

 Son olarak, kendi özel kullanıcı Arabirimi öğeleri oluşturmanız gerekirse <xref:System.Drawing> ad alanı yelpazesinden seçim satırları, daire ve diğer şekiller bir form üzerinde doğrudan işlemek için sınıflar içerir.

> [!NOTE]
> Windows Forms denetimleri, uygulama etki alanları arasında sıralanması için tasarlanmamıştır. Bu nedenle, Microsoft genelinde bir Windows Forms denetimi geçirme desteklemiyor bir <xref:System.AppDomain> sınır, olsa bile <xref:System.Windows.Controls.Control> temel türü <xref:System.MarshalByRefObject> mümkün olduğunu belirtmek için görünen. Hiçbir Windows Forms denetimleri uygulama etki alanı sınırları arasında geçirilen sürece birden çok uygulama etki alanları Windows Forms uygulamaları desteklenir.

#### <a name="create-forms-and-controls"></a>Formlar ve denetimler oluşturma

Bu özelliklerin nasıl kullanılacağını hakkında adım adım bilgiler için aşağıdaki Yardım konularına bakın.

|Açıklama|Yardım konusu|
|-----------------|----------------|
|Form üzerinde denetimleri kullanma|[Nasıl yapılır: Windows Forms'a denetimler ekleme](./controls/how-to-add-controls-to-windows-forms.md)|
|Kullanarak <xref:System.Windows.Forms.ToolStrip> denetimi|[Nasıl yapılır: Tasarımcı kullanarak standart öğelerle temel bir ToolStrip oluşturma](./controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md)|
|Grafik oluşturma <xref:System.Drawing>|[Grafik Programlamaya Başlarken](./advanced/getting-started-with-graphics-programming.md)|
|Özel denetimler oluşturma|[Nasıl yapılır: UserControl sınıfından devralma](./controls/how-to-inherit-from-the-usercontrol-class.md)|

### <a name="display-and-manipulate-data"></a>Verileri görüntüleme ve düzenleme
 Birçok uygulama, verileri bir veritabanından, XML dosyası, XML Web hizmeti veya başka bir veri kaynağı görüntülemeniz gerekir. Windows Forms adlı esnek bir denetim sağlar <xref:System.Windows.Forms.DataGridView> kendi hücrenin her veri parçası kapladığı bir tablo gibi veri geleneksel bir satır ve sütun biçiminde, görüntüleme için denetimi. Kullanırken <xref:System.Windows.Forms.DataGridView>, tek tek hücrelerin görünüşünü özelleştirme, rastgele satırları kilitlemek ve sütunlardaki yerleştirin ve karmaşık denetimlerin yanı sıra başka özellikler hücreleri içine görüntülemek.

 Bir ağ üzerinden veri kaynaklarına bağlanma, Windows Forms akıllı istemciler ile basit bir görevdir. <xref:System.Windows.Forms.BindingSource> Bileşenini temsil eder, bir veri kaynağı bağlantısı ve yöntemleri için önceki ve sonraki kayıtların gezinmesi kayıtlarının düzenlenmesi ve değişiklikleri kaydetmeden denetimlere veri bağlama için özgün kaynağına yedekleme. <xref:System.Windows.Forms.BindingNavigator> Denetim sağlayan basit bir arabirim üzerinden <xref:System.Windows.Forms.BindingSource> kayıtlar arasında gezinmek kullanıcılar için bileşen.

 Veri Kaynakları penceresini kullanarak kolayca verilere bağlı denetimler oluşturabilirsiniz. Pencere nesneleri veritabanları ve Web Hizmetleri gibi veri kaynakları projenizde görüntüler. Öğeleri bu pencereden projenizdeki formlara sürükleyerek veriye bağlı denetimler oluşturabilirsiniz. Ayrıca veri mevcut denetimleri için veri nesnelerini veri kaynakları penceresinden mevcut denetimlerin üzerine sürükleyerek bağlama.

 Windows Forms'ta yönetebileceğiniz veri bağlama başka bir tür *ayarları*. Çoğu akıllı istemci uygulamaları, forms, bilinen son boyutu gibi çalışma zamanı durumlarını hakkında bazı bilgiler korumak ve kaydedilen dosyalar için varsayılan konumları gibi kullanıcı tercihi verileri korur. Uygulama ayarları özellik ayarları her iki türde istemci bilgisayarda depolamak için kolay bir yol sağlayarak bu gereksinimleri ele alır. Visual Studio veya bir kod Düzenleyicisi'ni kullanarak bu ayarları tanımladıktan sonra ayarları XML olarak kalıcı ve otomatik olarak çalışma zamanında belleğe geri okuyun.

#### <a name="display-and-manipulate-data"></a>Verileri görüntüleme ve düzenleme

Bu özelliklerin nasıl kullanılacağını hakkında adım adım bilgiler için aşağıdaki Yardım konularına bakın.

|Açıklama|Yardım konusu|
|-----------------|----------------|
|Kullanarak <xref:System.Windows.Forms.BindingSource> bileşeni|[Nasıl yapılır: BindingSource bileşeniyle Tasarımcı kullanarak Windows Forms denetimleri bağlama](./controls/bind-wf-controls-with-the-bindingsource.md)|
|ADO.NET veri kaynaklarıyla çalışma|[Nasıl yapılır: Windows ile ADO.NET verilerini sıralama ve filtreleme Forms BindingSource bileşeni](./controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Veri Kaynakları penceresini kullanma|[Visual Studio'da verilere Windows Forms denetimleri bağlama](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)|
|Uygulama ayarlarını kullanma|[Nasıl yapılır: Uygulama ayarları oluşturma](./advanced/how-to-create-application-settings.md)|

### <a name="deploy-apps-to-client-computers"></a>İstemci bilgisayarlara uygulamaları dağıtma

Uygulamanızı yazdıktan sonra kullanıcılarınıza uygulama yükleyebilir ve kendi istemci bilgisayarlarda çalıştırmak göndermeniz gerekir. ClickOnce teknoloji kullandığınızda, uygulamalarınızı Visual Studio'dan yalnızca birkaç tıklamayla kullanarak dağıtma ve Web uygulamanıza işaret eden bir URL ile kullanıcılarınızın sağlayın. ClickOnce tüm öğeleri ve bağımlılıkları uygulamanızdaki yönetir ve uygulama istemci bilgisayarda doğru şekilde yüklendiğini sağlar.

ClickOnce uygulamalarında, yalnızca kullanıcı ağa bağlandığında çalıştırmak için veya her ikisi de çevrimiçi çalıştırmak için yapılandırılmış ve çevrimdışı olabilir. Uygulama çevrimdışı işlemi desteklemelidir belirttiğinizde, ClickOnce uygulamanıza bir kullanıcının bir bağlantı ekler **Başlat** menüsü. Kullanıcı daha sonra uygulama URL'sini kullanmadan açabilirsiniz.

Uygulamanızı güncelleştirdiğinizde, yeni bir dağıtım bildirimi ve yeni bir kopya, uygulamanızın Web sunucunuza yayımlayın. ClickOnce, bir güncelleştirme kullanılabilir olmadığını ve kullanıcının yüklemeyi yükseltme algılar; özel programlama eski derlemeleri güncelleştirmek için gereklidir.

#### <a name="deploy-clickonce-apps"></a>ClickOnce uygulamaları dağıtma

ClickOnce tam bir giriş için bkz: [ClickOnce güvenliği ve dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment). Bu özelliklerin nasıl kullanılacağını hakkında adım adım bilgiler için aşağıdaki Yardım konularına bakın,

|Açıklama|Yardım konusu|
|-----------------|----------------|
|ClickOnce kullanarak uygulama dağıtma|[Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [İzlenecek yol: ClickOnce Uygulamasını El ile Dağıtma](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|ClickOnce dağıtımını güncelleştirme|[Nasıl yapılır: ClickOnce Uygulaması için Güncelleştirmeleri Yönetme](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|ClickOnce ile güvenliği yönetme|[Nasıl yapılır: ClickOnce Güvenlik Ayarlarını Etkinleştirme](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

### <a name="other-controls-and-features"></a>Diğer denetimler ve özellikleri

Windows Forms'ta olun uygulayan ortak görevleri hızlı ve kolay, iletişim kutuları oluşturma, yazdırma, Yardım ve belgeler ekleme ve uygulamanızı birden çok dilde yerelleştirme desteği gibi diğer birçok özellik vardır. Ayrıca, Windows Forms, .NET Framework'ün sağlam güvenlik sistemine bağlıdır. Bu sistem ile müşterilerinize daha güvenli uygulamalar serbest bırakabilirsiniz.

#### <a name="implement-other-controls-and-features"></a>Diğer denetimler ve özellikleri uygulama

Bu özelliklerin nasıl kullanılacağını hakkında adım adım bilgiler için aşağıdaki Yardım konularına bakın.

|Açıklama|Yardım konusu|
|-----------------|----------------|
|Form içeriklerini yazdırma|[Nasıl yapılır: Windows Forms'ta grafik yazdırma](./advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Nasıl yapılır: Windows Forms'ta çok sayfalı metin dosyası yazdırma](./advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Windows Forms güvenliği hakkında daha fazla bilgi edinin|[Windows Forms'ta Güvenliğe Genel Bakış](security-in-windows-forms-overview.md)|

## <a name="see-also"></a>Ayrıca bkz.

- [Windows Forms'a Başlarken](getting-started-with-windows-forms.md)
- [Yeni bir Windows Formu Oluşturma](creating-a-new-windows-form.md)
- [ToolStrip Denetimine Genel Bakış](./controls/toolstrip-control-overview-windows-forms.md)
- [DataGridView Denetimine Genel Bakış](./controls/datagridview-control-overview-windows-forms.md)
- [BindingSource Bileşenine Genel Bakış](./controls/bindingsource-component-overview.md)
- [Uygulama Ayarlarına Genel Bakış](./advanced/application-settings-overview.md)
- [ClickOnce Güvenliği ve Dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)
