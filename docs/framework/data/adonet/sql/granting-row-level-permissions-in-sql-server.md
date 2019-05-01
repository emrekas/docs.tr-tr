---
title: SQL Server’da Satır Düzeyinde İzinler Verme
ms.date: 03/30/2017
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
ms.openlocfilehash: 891b5114551c5784b11504f2463525087125131f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033910"
---
# <a name="granting-row-level-permissions-in-sql-server"></a><span data-ttu-id="7b28c-102">SQL Server’da Satır Düzeyinde İzinler Verme</span><span class="sxs-lookup"><span data-stu-id="7b28c-102">Granting Row-Level Permissions in SQL Server</span></span>

<span data-ttu-id="7b28c-103">Bazı senaryolarda, hangi yalnızca verme, iptal etme veya reddetme izinleri sağlar. daha fazla ayrıntılı bir düzeyde verilere erişimi denetlemek için bir gereksinim yoktur.</span><span class="sxs-lookup"><span data-stu-id="7b28c-103">In some scenarios, there is a requirement to control access to data at a more granular level than what simply granting, revoking, or denying permissions provides.</span></span> <span data-ttu-id="7b28c-104">Örneğin, bir hastane veritabanı uygulaması tek Doktorlar hastaların için yalnızca ilgili bilgiler erişimle sınırlı olmasını gerektirebilir.</span><span class="sxs-lookup"><span data-stu-id="7b28c-104">For example, a hospital database application may require individual Doctors to be restricted to accessing information related to only their patients.</span></span> <span data-ttu-id="7b28c-105">Benzer gereksinimleri, Finans, yasa, resmi ve Askeri uygulamalar dahil, birçok ortamlarında mevcut.</span><span class="sxs-lookup"><span data-stu-id="7b28c-105">Similar requirements exist in many environments, including finance, law, government, and military applications.</span></span> <span data-ttu-id="7b28c-106">Bu senaryolara yardımcı olmak için SQL Server 2016 sağlar. bir [satır düzeyi güvenlik](/sql/relational-databases/security/row-level-security) basitleştirir ve satır düzeyinde erişim mantığı güvenlik ilkesinde otomatik özelliği.</span><span class="sxs-lookup"><span data-stu-id="7b28c-106">To help address these scenarios, SQL Server 2016 provides a [Row-Level Security](/sql/relational-databases/security/row-level-security) feature that simplifies and centralizes row-level access logic in a security policy.</span></span> <span data-ttu-id="7b28c-107">Satır düzeyinde filtreleme geçireceğini görünümlerini kullanarak SQL Server'ın önceki sürümleri için benzer bir işlevsellik gerçekleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="7b28c-107">For earlier versions of SQL Server, similar functionality can be achieved by using views to enact row-level filtering.</span></span>

## <a name="implementing-row-level-filtering"></a><span data-ttu-id="7b28c-108">Satır düzeyi filtre uygulama</span><span class="sxs-lookup"><span data-stu-id="7b28c-108">Implementing Row-level Filtering</span></span>

<span data-ttu-id="7b28c-109">Satır düzeyinde filtreleme uygulamaları gibi tek bir tabloda yukarıdaki hastane örnekte bilgilerini depolamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7b28c-109">Row-level filtering is used for applications storing information in a single table like in the hospital example above.</span></span> <span data-ttu-id="7b28c-110">Satır düzeyi her bir satır filtresi uygulamak için bir kullanıcı adı, etiket veya başka bir tanımlayıcı gibi ayırt edici bir parametre tanımlayan bir sütun vardır.</span><span class="sxs-lookup"><span data-stu-id="7b28c-110">To implement row-level filtering each row has a column that defines a differentiating parameter, such as a user name, label or other identifier.</span></span> <span data-ttu-id="7b28c-111">Bir güvenlik ilkesini veya kullanıcının erişebildiği satırları filtreler tablosunda bir görünüm oluşturun.</span><span class="sxs-lookup"><span data-stu-id="7b28c-111">You create either a security policy or a view on the table, which filters the rows that the user can access.</span></span> <span data-ttu-id="7b28c-112">Daha sonra kullanıcı yürütebilir sorguları türlerini denetlemek için parametreli saklı yordamlar, oluşturursunuz.</span><span class="sxs-lookup"><span data-stu-id="7b28c-112">You then create parameterized stored procedures, which control the types of queries the user can execute.</span></span>

<span data-ttu-id="7b28c-113">Aşağıdaki örnek, satır düzeyinde bir kullanıcı veya oturum açma adına göre filtrelemeyi yapılandırma açıklar:</span><span class="sxs-lookup"><span data-stu-id="7b28c-113">The following example describes how to configure row-level filtering based on a user or login name:</span></span>

- <span data-ttu-id="7b28c-114">Adı depolamak için bir sütun ekleme, tablo oluşturun.</span><span class="sxs-lookup"><span data-stu-id="7b28c-114">Create the table, adding a column to store the name.</span></span>

- <span data-ttu-id="7b28c-115">Satır düzeyinde filtreleme etkinleştir:</span><span class="sxs-lookup"><span data-stu-id="7b28c-115">Enable row-level filtering:</span></span>

  - <span data-ttu-id="7b28c-116">SQL Server 2016 veya sonraki bir sürümünü kullanıyorsanız veya [Azure SQL veritabanı](https://docs.microsoft.com/azure/sql-database/), satırları kısıtlama tablosunda bir koşul döndürülen ya da eşleşen olanlar (CURRENT_USER() kullanarak geçerli bir veritabanı kullanıcısı ekleyen bir güvenlik ilkesi oluşturma Yerleşik işlev) veya (SUSER_SNAME() yerleşik işlevi kullanılarak), geçerli oturum açma adı:</span><span class="sxs-lookup"><span data-stu-id="7b28c-116">If you are using SQL Server 2016 or higher, or [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/), create a security policy that adds a predicate on the table restricting the rows returned to those that match either the current database user (using the CURRENT_USER() built-in function) or the current login name (using the SUSER_SNAME() built-in function):</span></span>

      ```sql
      CREATE SCHEMA Security
      GO

      CREATE FUNCTION Security.userAccessPredicate(@UserName sysname)
          RETURNS TABLE
          WITH SCHEMABINDING
      AS
          RETURN SELECT 1 AS accessResult
          WHERE @UserName = SUSER_SNAME()
      GO

      CREATE SECURITY POLICY Security.userAccessPolicy
          ADD FILTER PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable,
          ADD BLOCK PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable
      GO
      ```

  - <span data-ttu-id="7b28c-117">SQL Server 2016'dan önce bir sürümü kullanıyorsanız benzer işlevselliği bir görüntü kullanarak elde edebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="7b28c-117">If you are using a version of SQL Server prior to 2016, you can achieve similar functionality using a view:</span></span>

      ```sql
      CREATE VIEW vw_MyTable
      AS
          RETURN SELECT * FROM MyTable
          WHERE UserName = SUSER_SNAME()
      GO
      ```

- <span data-ttu-id="7b28c-118">Seçin, ekleme, güncelleştirme ve verileri silmek için saklı yordamlar oluşturun.</span><span class="sxs-lookup"><span data-stu-id="7b28c-118">Create stored procedures to select, insert, update, and delete data.</span></span> <span data-ttu-id="7b28c-119">Güvenlik İlkesi tarafından filtreleme geçirilmeden, saklı yordamları doğrudan temel tablo bu işlemleri gerçekleştirmeniz gerekir; Aksi takdirde, filtre tarafından bir görünümü geçirilmeden, saklı yordamları yerine karşı görünümü çalışması.</span><span class="sxs-lookup"><span data-stu-id="7b28c-119">If the filtering is enacted by a security policy, the stored procedures should perform these operations on the base table directly; otherwise, if the filtering is enacted by a view, the stored procedures should instead operate against the view.</span></span> <span data-ttu-id="7b28c-120">Güvenlik İlkesi veya Görünüm otomatik olarak döndürülen veya kullanıcı sorgular tarafından değiştirilen satırları filtreleyen ve saklı yordam doğrudan sorgu erişimi olan kullanıcılar başarıyla çıkarımını sorgular çalıştırılmasını engellemek için daha zor bir güvenlik sınırı sağlar filtrelenmiş veri varlığını.</span><span class="sxs-lookup"><span data-stu-id="7b28c-120">The security policy or view will automatically filter the rows returned or modified by user queries, and the stored procedure will provide a harder security boundary to prevent users with direct query access from successfully running queries that can infer the existence of filtered data.</span></span>

- <span data-ttu-id="7b28c-121">Veri ekleme, saklı yordamlar, yakalama aynı güvenlik ilkesi veya görünümü'nde belirtilen işlevi kullanarak kullanıcı adı ve değeri kullanıcıadı sütuna ekleyin.</span><span class="sxs-lookup"><span data-stu-id="7b28c-121">For stored procedures that insert data, capture the user name using the same function specified in the security policy or view, and insert that value into the UserName column.</span></span>

- <span data-ttu-id="7b28c-122">Tüm tablolar (ve görünümler, eğer varsa) izinlerini reddetmek için `public` rol.</span><span class="sxs-lookup"><span data-stu-id="7b28c-122">Deny all permissions on the tables (and views, if applicable) to the `public` role.</span></span> <span data-ttu-id="7b28c-123">Kullanıcılar, filtre koşulu kullanıcı veya rol değil, oturum açma adları bağlı olduğu diğer veritabanı rollerden devralmak mümkün olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="7b28c-123">Users will not be able to inherit permissions from other database roles, because the filter predicate is based on user or login names, not on roles.</span></span>

- <span data-ttu-id="7b28c-124">GRANT veritabanı rollerine saklı yordamlar YÜRÜTÜN.</span><span class="sxs-lookup"><span data-stu-id="7b28c-124">Grant EXECUTE on the stored procedures to database roles.</span></span> <span data-ttu-id="7b28c-125">Kullanıcılar sağlanan saklı yordamları yalnızca verilere erişebilir.</span><span class="sxs-lookup"><span data-stu-id="7b28c-125">Users can only access data through the stored procedures provided.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b28c-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7b28c-126">See also</span></span>

- [<span data-ttu-id="7b28c-127">Satır düzeyi güvenlik</span><span class="sxs-lookup"><span data-stu-id="7b28c-127">Row-Level Security</span></span>](/sql/relational-databases/security/row-level-security)
- [<span data-ttu-id="7b28c-128">ADO.NET Uygulamalarının Güvenliğini Sağlama</span><span class="sxs-lookup"><span data-stu-id="7b28c-128">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="7b28c-129">SQL Server Güvenliğine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="7b28c-129">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [<span data-ttu-id="7b28c-130">SQL Server'da Uygulama Güvenliği Senaryoları</span><span class="sxs-lookup"><span data-stu-id="7b28c-130">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="7b28c-131">SQL Server'da Saklı Yordam İzinlerini Yönetme</span><span class="sxs-lookup"><span data-stu-id="7b28c-131">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="7b28c-132">SQL Server’da Secure Dynamic SQL Yazma</span><span class="sxs-lookup"><span data-stu-id="7b28c-132">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="7b28c-133">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="7b28c-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
