---
title: Mikro hizmet başına veri hakimiyeti
description: Mikro hizmet başına veri hakimiyeti mikro kay noktası biridir. Her mikro hizmet kendi veritabanında hiçbir diğer paylaşım sahibi tek olması gerekir. Elbette bir mikro hizmet tüm örnekleri aynı yüksek kullanılabilirlik veritabanına bağlanın.
ms.date: 09/20/2018
ms.openlocfilehash: ccb12451cd7cd44938e09d171eb29e614786f469
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644448"
---
# <a name="data-sovereignty-per-microservice"></a>Mikro hizmet başına veri hakimiyeti

Mikro hizmet mimarisi için önemli bir kuralı, her bir mikro hizmet kendi etki alanı verileri ve mantıksal sahibi olduğunu ' dir. Bu nedenle yalnızca tam bir uygulama, mantık ve veriler sahip olduğu gibi her bir mikro hizmet kendi mantığı ve verileri ile mikro hizmet başına bağımsız olarak dağıtılmasını otonom bir yaşam döngüsü altında sahip olmanız gerekir.

Başka bir deyişle, etki alanının kavramsal model alt sistemler veya mikro hizmetler arasında farklılık gösterir. Kurumsal uygulamaları ve müşteri ilişkileri yönetimi (CRM) uygulamaları, işlem her çağrıda benzersiz Müşteri varlık öznitelikleri ve veri alt sistemleri ve müşteri destek alt sistemler satın yerde ve her farklı bir kullanan göz önünde bulundurun Sınırlanmış bağlam (BC).

Bu ilkeye benzer [etki alanı Odaklı Tasarım (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design), burada her [içerik sınırlanmış](https://martinfowler.com/bliki/BoundedContext.html) veya otonom alt sistemi veya hizmet kendi etki alanı modeli (veri yanı sıra mantığı ve davranışı) sahip olmalıdır. Her DDD içerik sınırlanmış bir iş mikro (bir veya birden fazla hizmet) ilişkilendirir. İçerik sınırlanmış düzeniyle ilgili bu noktadan sonraki bölümde genişletilir.

Öte yandan, birçok uygulamada kullanılan geleneksel (tek parçalı veriler) yaklaşımı tek, merkezi bir veritabanındaki veya yalnızca birkaç veritabanlarına sahip olmaktır. Genellikle tüm uygulama ve tüm kendi iç alt sistemleri için kullanılan normalleştirilmiş bir SQL veritabanı Şekil 4-7'de gösterildiği gibi budur.

![Geleneksel yaklaşımda genellikle katmanlı bir mimari olarak tüm hizmetler arasında paylaşılan tek bir veritabanı yok. Mikro hizmetler yaklaşımı her bir mikro hizmet kendi model/veri sahibi](./media/image7.png)

**Şekil 4-7**. Veri egemenliği karşılaştırması: tek parça veritabanı ile mikro hizmetler karşılaştırması

Merkezi veritabanı yaklaşımı, başlangıçta basit arar ve her şeyi tutarlı hale getirmek için farklı alt sistemler varlık yeniden etkinleştirmek için gibi görünüyor. Ancak, birçok farklı alt sistemleri, hizmet ve çoğu durumda öznitelikleri ve gerekli olmayan sütunları içeren büyük tablolar elde edersiniz gerçeğidir. Bu, aynı fiziksel harita kısa bir iz yürüyüşe ayırır, bir günlük uzun araba yolculuğu alma ve Coğrafya öğrenme kullanmaya çalışıyor gibi olur.

Genellikle tek bir ilişkisel veritabanı ile tek parça bir uygulamayı iki önemli avantajı vardır: [ACID işlemlerini](https://en.wikipedia.org/wiki/ACID) ve SQL dili, tüm tabloları ve uygulamanız ile ilgili veriler arasında her iki çalışma. Bu yaklaşım, kolayca birden fazla tablolardaki verileri birleştiren bir sorgu yazmak için bir yol sağlar.

Ancak, bir mikro hizmet mimarisi için taşıdığınızda veri erişimi çok daha karmaşık hale gelir. Ancak ACID işlemlerini olabilir veya bir mikro hizmet veya içerik sınırlanmış içinde kullanılması gereken olsa bile, her mikro hizmet tarafından sahip olunan veri, mikro hizmet için özeldir ve yalnızca kendi mikro hizmet API aracılığıyla erişilebilir. Veri kapsülleme, mikro Hizmetleri birbirine sıkı şekilde bağlı ve devredebileceği geliştirebilirsiniz sağlar. Şema güncelleştirmeleri, birden fazla hizmeti aynı verileri erişiyorsanız, bu tüm hizmetler için Eşgüdümlü güncelleştirmeleri gerekir. Bu mikro hizmet yaşam döngüsü otonomi çalışmamasına neden. Ancak, Dağıtılmış veri yapıları üzerinde mikro hizmetler tek bir ACID işlemi yapamaz anlamına gelir. Bu sırayla bir iş sürecini birden fazla mikro hizmetin yayıldığında nihai tutarlılık kullanmalısınız anlamına gelir. Bu bütünlük kısıtlamaları oluşturmak veya daha sonra açıklayacağız ayrı veritabanları arasında dağıtılmış işlemler kullanmak basit SQL birleşimleri, uygulamak çok daha zordur. Benzer şekilde, diğer pek çok ilişkisel veritabanı özellikleri arasında birden fazla mikro hizmetin kullanılamaz.

Daha da ileri giderek, farklı bir mikro hizmetler farklı kullandığı *tür* veritabanlarının. Modern uygulamalar depolama ve işlem farklı türlerde veri ve ilişkisel bir veritabanı olmadığından her zaman en iyi seçenek. Bazı için kullanım örnekleri, Azure Cosmosdb'ye veya MongoDB gibi bir NoSQL veritabanı daha kullanışlı bir veri modeline sahip olan ve daha iyi performans ve ölçeklenebilirlik SQL Server gibi bir SQL veritabanı veya Azure SQL veritabanı sağlar. Diğer durumlarda, bir ilişkisel veritabanı hala en iyi yaklaşımdır. Bu nedenle, mikro hizmet tabanlı uygulamaları bazen çağrılan bir karışımını SQL ve NoSQL veritabanları, sık kullandığınız [çok yönlü Kalıcılık](https://martinfowler.com/bliki/PolyglotPersistence.html) yaklaşım.

Veri depolama için bölümlenmiş, polyglot kalıcı bir mimari, pek çok faydası vardır. Bunlar, gevşek bağlantılı Hizmetleri ve daha iyi performans, ölçeklenebilirlik, maliyetleri ve yönetilebilirlik içerir. Ancak, bazı Dağıtılmış veri yönetimi sorunlarını açıklandığı şekilde ortaya çıkarabilir "[etki alanı modeli sınırlarını tanımlama](identify-microservice-domain-model-boundaries.md)" Bu bölümdeki.

## <a name="the-relationship-between-microservices-and-the-bounded-context-pattern"></a>Mikro hizmet ve içerik sınırlanmış deseni arasındaki ilişki

Mikro hizmet kavramını türetildiği [sınırlanmış bağlam (BC) deseni](https://martinfowler.com/bliki/BoundedContext.html) içinde [etki alanı Odaklı Tasarım (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design). DDD, bunları birden çok BCs bölme ve sınırlarının hakkında açık büyük modelleri ile ilgilidir. Her BC kendi model ve veritabanı olmalıdır; benzer şekilde, her bir mikro hizmet kendi ilgili verilere sahip. Ayrıca, her BC genellikle kendi bölümüne sahiptir [bulunabilen dil](https://martinfowler.com/bliki/UbiquitousLanguage.html) yazılım geliştiricileri ve etki alanı uzmanları arasındaki iletişimi yardımcı olmak için.

Bulunabilen dilde Bu terimleri (ağırlıklı olarak etki alanı varlıklarının) farklı sınırlanmış bağlamda farklı adlara sahip olabilir, aynı kimliğe (varlık depodan okumak için kullanılan diğer bir deyişle, benzersiz Tanımlayıcı) bile farklı etki alanı varlıklarının paylaşın. Örneğin, sipariş sınırlanmış bağlam içinde alıcı etki alanı varlığı ile kullanıcı profili sınırlanmış bir bağlamda kullanıcı etki alanı varlığı kimlik paylaşabilir.

Bir mikro hizmet gibi bir sınırlanmış bağlam nedenle gereklidir, ancak ayrıca dağıtılmış bir hizmet olduğunu belirtir. Sınırlanmış her bağlam için ayrı bir işlem olarak oluşturulmuştur ve HTTP/HTTPS gibi WebSockets, daha önce not ettiğiniz dağıtılmış protokolleri kullanması gerekir veya [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol). İçerik sınırlanmış deseni ancak sınırlanmış bağlam, dağıtılmış bir hizmet olup olmadığını veya yalnızca mantıksal bir sınır (örneğin, bir genel alt) olup olmadığını bir dağıtım tek parçalı uygulama içinde belirtmiyor.

Sınırlanmış her bağlam için bir hizmet tanımlama başlatmak için iyi bir yer olduğunu vurgulamak önemlidir. Ancak ona tasarımınızı sınırlamak zorunda değilsiniz. Bazen bir sınırlanmış bağlam tasarlamanız gerekir veya iş mikro hizmet birden fazla fiziksel hizmetlerden oluşan. Ancak sonuç olarak, her ikisi de desenleri - içerik sınırlanmış ve mikro hizmet olan yakından ilgili.

Mikro hizmetler, dağıtılmış mikro hizmetler biçiminde gerçek sınırları alarak DDD sağladığı avantajları. Ancak kullanılmadığı mikro hizmetler arasında model gibi fikirleri ne de bir sınırlanmış bağlam içinde istiyorsunuz.

### <a name="additional-resources"></a>Ek kaynaklar

- **Chris Richardson. Desen: Hizmet başına veritabanı** \
  <https://microservices.io/patterns/data/database-per-service.html>

- **Martin Fowler. BoundedContext** \
  <https://martinfowler.com/bliki/BoundedContext.html>

- **Martin Fowler. PolyglotPersistence** \
  <https://martinfowler.com/bliki/PolyglotPersistence.html>

- **Alberto Brandolini. Stratejik etki alanı Odaklı Tasarım bağlam eşleme ile** \
  <https://www.infoq.com/articles/ddd-contextmapping>

>[!div class="step-by-step"]
>[Önceki](microservices-architecture.md)
>[İleri](logical-versus-physical-architecture.md)
