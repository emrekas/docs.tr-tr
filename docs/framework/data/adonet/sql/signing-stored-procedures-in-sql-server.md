---
title: SQL Server'da Saklı Yordam İmzalama
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 8dc62527be7273d3ce3222d4d261b81bc40b1e19
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791804"
---
# <a name="signing-stored-procedures-in-sql-server"></a>SQL Server'da Saklı Yordam İmzalama

Dijital imza, imzalayanın özel anahtarıyla şifrelenmiş bir veri özetine sahiptir. Özel anahtar, dijital imzanın kendi taşıyıcının veya sahibinin benzersiz olmasını sağlar. Saklı yordamları, işlevleri (satır içi tablo değerli işlevler hariç), Tetikleyicileri ve derlemeleri imzalayabilirsiniz.

Saklı yordamı sertifikayla veya asimetrik anahtarla imzalayabilirsiniz. Bu, izinler sahiplik zincirden devralınamayacağını veya dinamik SQL gibi sahiplik zinciri kopuk olduğunda senaryolar için tasarlanmıştır. Daha sonra sertifikayla eşlenmiş bir kullanıcı oluşturabilirsiniz, böylece saklı yordamın erişmesi gereken nesneler üzerinde sertifika Kullanıcı izinleri verebilirsiniz.

Aynı sertifikayla eşlenmiş bir oturum açma da oluşturabilir ve ardından bu oturum açma için gerekli sunucu düzeyi izinleri verebilir ya da oturum açma bilgilerini bir veya daha fazla sabit sunucu rolüne ekleyebilirsiniz. Bu, daha üst düzey izinlerin gerekli `TRUSTWORTHY` olduğu senaryolar için veritabanı ayarının etkinleştirilmesini önlemek üzere tasarlanmıştır.

Saklı yordam yürütüldüğünde, sertifika kullanıcısının izinlerini ve/veya arayanla birlikte oturum açma bilgilerini birleştirir SQL Server. `EXECUTE AS` Yan tümcesinin aksine, yordamın yürütme bağlamını değiştirmez. Oturum açma ve Kullanıcı adlarını döndüren yerleşik işlevler, sertifika kullanıcı adını değil, çağıranın adını döndürür.

## <a name="creating-certificates"></a>Sertifika oluşturma

Bir saklı yordamı sertifikayla veya asimetrik anahtarla imzaladığınızda, saklı yordam kodunun şifrelenmiş karmasından oluşan bir veri özeti, özel anahtar kullanılarak oluşturulur. Çalışma zamanında, veri özetinin şifresi ortak anahtarla çözülür ve saklı yordamın karma değeri ile karşılaştırılır. Farklı Çalıştır kullanıcısının değiştirilmesi, dijital imzanın artık eşleşmemesi için karma değeri geçersiz kılar. Saklı yordamı değiştirmek, imzayı tamamen bırakır, bu da özel anahtara erişimi olmayan birinin saklı yordam kodunu değiştirmesini önler. Her iki durumda da, kodu veya farklı çalıştır kullanıcısını her değiştirişinizde yordamı yeniden imzalamanız gerekir.

Modülün imzalanmasında iki gerekli adım vardır:

1. Transact-SQL `CREATE CERTIFICATE [certificateName]` ifadesini kullanarak bir sertifika oluşturun. Bu bildirimde bir başlangıç ve bitiş tarihi ve parola ayarlamak için çeşitli seçenekler bulunur. Varsayılan süre sonu tarihi bir yıldır.

1. Yöntemi Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` ifadesini kullanarak sertifikayla imzalayın.

Modül imzalandıktan sonra sertifikayla ilişkilendirilmesi gereken ek izinleri tutmak için bir veya daha fazla asıl oluşturulması gerekir.

Modülün ek veritabanı düzeyi izinleri olması gerekiyorsa:

1. Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` ifadesini kullanarak bu sertifikayla ilişkili bir veritabanı kullanıcısı oluşturun. Bu Kullanıcı yalnızca veritabanında bulunur ve aynı sertifikadan aynı zamanda bir oturum açma işlemi yoksa bir oturum açma işlemiyle ilişkili değildir.

1. Sertifika kullanıcısına gerekli veritabanı düzeyi izinlerini verin.

Modülün ek sunucu düzeyi izinleri olması gerekiyorsa:

1. Sertifikayı `master` veritabanına kopyalayın.

1. Transact-SQL `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` ifadesini kullanarak bu sertifikayla ilişkili bir oturum açma oluşturun.

1. Sertifika oturumuna gereken sunucu düzeyi izinleri verin.

> [!NOTE]
> Bir sertifika, izinleri reddetme ifadesiyle iptal edilen bir kullanıcıya izin veremez. REDDETME her zaman verme işleminden önceliklidir ve çağıranın sertifika kullanıcısına verilen izinleri devralmasını önler.

## <a name="external-resources"></a>Dış Kaynaklar

Daha fazla bilgi için aşağıdaki kaynaklara bakın.

|Kaynak|Açıklama|
|--------------|-----------------|
|SQL Server Books Online 'da [Modül oturumu açma](https://go.microsoft.com/fwlink/?LinkId=98590)|Modül imzalamayı açıklar, örnek bir senaryo ve ilgili Transact-SQL konularına bağlantılar sağlar.|
|SQL Server Books Online 'daki [bir sertifikayla saklı yordamları imzalama](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate)|Bir saklı yordamı sertifikayla imzalamak için bir öğretici sağlar.|

## <a name="see-also"></a>Ayrıca bkz.

- [ADO.NET Uygulamalarının Güvenliğini Sağlama](../securing-ado-net-applications.md)
- [SQL Server Güvenliğine Genel Bakış](overview-of-sql-server-security.md)
- [SQL Server'da Uygulama Güvenliği Senaryoları](application-security-scenarios-in-sql-server.md)
- [SQL Server'da Saklı Yordam İzinlerini Yönetme](managing-permissions-with-stored-procedures-in-sql-server.md)
- [SQL Server’da Secure Dynamic SQL Yazma](writing-secure-dynamic-sql-in-sql-server.md)
- [SQL Server'da Kimliğe Bürünme İzinlerini Özelleştirme](customizing-permissions-with-impersonation-in-sql-server.md)
- [Saklı Yordamlarla Verileri Değiştirme](../modifying-data-with-stored-procedures.md)
- [ADO.NET’e Genel Bakış](../ado-net-overview.md)
