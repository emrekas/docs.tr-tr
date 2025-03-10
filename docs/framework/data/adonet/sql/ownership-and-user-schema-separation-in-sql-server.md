---
title: SQL Server'da Sahiplik ve Kullanıcı Şeması Ayrımı
ms.date: 03/30/2017
ms.assetid: 242830c1-31b5-4427-828c-cc22ff339f30
ms.openlocfilehash: f0aa0a67bfbc64124fe2510915d0945341aeb49e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791939"
---
# <a name="ownership-and-user-schema-separation-in-sql-server"></a>SQL Server'da Sahiplik ve Kullanıcı Şeması Ayrımı
SQL Server güvenliği temel bir kavramı, nesne sahiplerinin bunları yönetmek için geri alınamaz izinlere sahip olmalarından oluşur. Bir nesne sahibinden ayrıcalıkları kaldıramazsınız ve içindeki nesneler varsa kullanıcıları bir veritabanından bırakamazsınız.  
  
## <a name="user-schema-separation"></a>Kullanıcı şeması ayrımı  
 Kullanıcı şeması ayrımı, veritabanı nesne izinlerinin yönetiminde daha fazla esneklik sağlar. *Şema* , nesneleri ayrı ad alanlarına gruplandırmanıza olanak tanıyan veritabanı nesneleri için adlandırılmış bir kapsayıcıdır. Örneğin, AdventureWorks örnek veritabanı üretim, satış ve ınsana kaynakları için şemalar içerir.  
  
 Nesnelere başvurmak için dört bölümden oluşan adlandırma sözdizimi, şema adını belirtir.  
  
```  
Server.Database.DatabaseSchema.DatabaseObject  
```  
  
### <a name="schema-owners-and-permissions"></a>Şema sahipleri ve Izinleri  
 Şemaların herhangi bir veritabanı sorumlusu olabilir ve tek bir sorumlu birden çok şemaya sahip olabilir. Şemadaki tüm nesneler tarafından devralınan bir şemaya güvenlik kuralları uygulayabilirsiniz. Bir şema için erişim izinleri ayarladıktan sonra, şemaya yeni nesneler eklendikçe bu izinler otomatik olarak uygulanır. Kullanıcılara varsayılan bir şema atanabilir ve birden çok veritabanı kullanıcısı aynı şemayı paylaşabilir.  
  
 Varsayılan olarak, geliştiriciler bir şemada nesne oluştururken nesneler, geliştiriciye değil, şemanın sahibi olan güvenlik sorumlusuna aittir. Nesne sahipliği, ALTER AUTHORIZATION Transact-SQL ifadesiyle aktarılabilir. Şema, farklı kullanıcılara ait olan ve şemaya atananlardan daha ayrıntılı izinlere sahip olan nesneleri de içerebilir, ancak bu, izinleri yönetmek için karmaşıklık eklediğinden bu önerilmez. Nesneler şemalar arasında taşınabilir ve şema sahipliği sorumlular arasında aktarılabilir. Veritabanı kullanıcıları şemalar etkilenmeden bırakılamaz.  
  
### <a name="built-in-schemas"></a>Yerleşik şemalar  
 SQL Server, yerleşik veritabanı kullanıcıları ve rolleriyle aynı adlara sahip olan on önceden tanımlanmış şemalar ile birlikte gelir. Bunlar genellikle geriye dönük uyumluluk için vardır. Aynı ada sahip olan şemaları, gerek duymadıysanız, sabit veritabanı rolleriyle bırakabilirsiniz. Aşağıdaki şemaları bırakamazsınız:  
  
- `dbo`  
  
- `guest`  
  
- `sys`  
  
- `INFORMATION_SCHEMA`  
  
 Bunları model veritabanından bırakırsanız, bu yeni veritabanlarında görünmez.  
  
> [!NOTE]
> `sys` Ve`INFORMATION_SCHEMA` şemaları sistem nesneleri için ayrılmıştır. Bu şemalarda nesne oluşturamazsınız ve bunları bırakamazsınız.  
  
#### <a name="the-dbo-schema"></a>Dbo şeması  
 `dbo` Şema, yeni oluşturulan bir veritabanı için varsayılan şemadır. `dbo` Şemanın `dbo` Kullanıcı hesabına ait olması. Varsayılan olarak, Create User Transact-SQL komutuyla oluşturulan kullanıcılar varsayılan şemasına sahiptir `dbo` .  
  
 `dbo` Şemaya atanan kullanıcılar, `dbo` Kullanıcı hesabının izinlerini almıyor. Bir şemadan kullanıcılar tarafından devralınan izin yok; şema izinleri, şemada bulunan veritabanı nesneleri tarafından devralınır.  
  
> [!NOTE]
> Veritabanı nesnelerine tek parçalı ad kullanılarak başvurulduğunda, SQL Server önce kullanıcının varsayılan şemasına bakar. Nesne bulunamazsa, `dbo` şemada bir sonraki SQL Server görünür. Nesne `dbo` şemada değilse bir hata döndürülür.  
  
## <a name="external-resources"></a>Dış Kaynaklar  
 Nesne sahipliği ve şemaları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın.  
  
|Kaynak|Açıklama|  
|--------------|-----------------|  
|[Kullanıcı şeması ayrımı](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms190387(v=sql.105))|Kullanıcı şeması ayrımı tarafından tanıtılan değişiklikleri açıklar. Yeni davranış, sahiplik üzerindeki etkisi, katalog görünümleri ve izinleri içerir.|  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ADO.NET Uygulamalarının Güvenliğini Sağlama](../securing-ado-net-applications.md)
- [SQL Server'da Uygulama Güvenliği Senaryoları](application-security-scenarios-in-sql-server.md)
- [SQL Server’da Kimlik Doğrulaması](authentication-in-sql-server.md)
- [SQL Server’da Sunucu ve Veritabanı Rolleri](server-and-database-roles-in-sql-server.md)
- [SQL Server’da Yetkilendirme ve İzinler](authorization-and-permissions-in-sql-server.md)
- [ADO.NET’e Genel Bakış](../ado-net-overview.md)
