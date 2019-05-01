---
title: Sorgu Bildirimlerini Etkinleştirme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: a2227b33c7caacdd04c7bf50082bb0cfab7f3302
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877623"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="fb071-102">Sorgu Bildirimlerini Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="fb071-102">Enabling Query Notifications</span></span>
<span data-ttu-id="fb071-103">Sorgu bildirimleri kullanan uygulamaları bir ortak gereksinimleri vardır.</span><span class="sxs-lookup"><span data-stu-id="fb071-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="fb071-104">Veri kaynağı doğru SQL sorgu bildirimleri destekleyecek şekilde yapılandırılmalıdır ve kullanıcı doğru istemci ve sunucu tarafı izinlere sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="fb071-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="fb071-105">Sorgu bildirimleri gerekir kullanmak için:</span><span class="sxs-lookup"><span data-stu-id="fb071-105">To use query notifications you must:</span></span>  
  
- <span data-ttu-id="fb071-106">Veritabanınız için sorgu bildirimleri etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="fb071-106">Enable query notifications for your database.</span></span>  
  
- <span data-ttu-id="fb071-107">Veritabanına bağlanmak için kullanılan kullanıcı kimliği gerekli izinlere sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="fb071-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
- <span data-ttu-id="fb071-108">Kullanım bir <xref:System.Data.SqlClient.SqlCommand> ilişkili bildirim nesnesi ile geçerli bir SELECT deyimi yürütmek için nesne — ya da <xref:System.Data.SqlClient.SqlDependency> veya <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="fb071-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
- <span data-ttu-id="fb071-109">Veri izlenmekte olan bildirim işlemi verirsiniz değişiklikler.</span><span class="sxs-lookup"><span data-stu-id="fb071-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="fb071-110">Sorgu bildirimleri gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="fb071-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="fb071-111">Sorgu bildirimleri yalnızca belirli bir gereksinimler listesini karşılayan SELECT deyimleri için desteklenir.</span><span class="sxs-lookup"><span data-stu-id="fb071-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="fb071-112">Aşağıdaki tablo, SQL Server Çevrimiçi Kitaplar'da Service Broker ve Sorgu Bildirimleri belgelerine bağlantılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="fb071-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="fb071-113">**SQL Server belgeleri**</span><span class="sxs-lookup"><span data-stu-id="fb071-113">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="fb071-114">[Bildirim için sorgu oluşturma](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="fb071-114">[Creating a Query for Notification](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="fb071-115">[Hizmet aracısı için güvenlik konuları](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="fb071-115">[Security Considerations for Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span></span>  
  
- <span data-ttu-id="fb071-116">[Güvenlik ve koruma (hizmet Aracısı)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="fb071-116">[Security and Protection (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span></span>  
  
- <span data-ttu-id="fb071-117">[Bildirim Hizmetleri için güvenlik konuları](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="fb071-117">[Security Considerations for Notifications Services](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span></span>  
  
- <span data-ttu-id="fb071-118">[Sorgu bildirim izinleri](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="fb071-118">[Query Notification Permissions](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span></span>  
  
- <span data-ttu-id="fb071-119">[Service Broker için Uluslararası konular](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="fb071-119">[International Considerations for Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span></span>  
  
- <span data-ttu-id="fb071-120">[Çözüm tasarımı konuları (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="fb071-120">[Solution Design Considerations (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span></span>  
  
- <span data-ttu-id="fb071-121">[Service Broker Geliştirici Bilgi Merkezi](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="fb071-121">[Service Broker Developer InfoCenter](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="fb071-122">[Geliştirici Kılavuzu (hizmet Aracısı)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="fb071-122">[Developer's Guide (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="fb071-123">Örnek kodu çalıştırma etkinleştirme sorgu bildirimleri</span><span class="sxs-lookup"><span data-stu-id="fb071-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="fb071-124">Hizmet Aracısı etkinleştirmek için **AdventureWorks** veritabanı SQL Server Management Studio kullanarak, aşağıdaki Transact-SQL deyimi çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="fb071-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="fb071-125">Sorgu bildirim örnekleri düzgün çalışması aşağıdaki Transact-SQL deyimlerini veritabanı sunucusunda yürütülmelidir.</span><span class="sxs-lookup"><span data-stu-id="fb071-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="fb071-126">Sorgu bildirimleri izinleri</span><span class="sxs-lookup"><span data-stu-id="fb071-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="fb071-127">Bildirim sorgu bildirimleri abone olmalıdır isteyen komutları yürütmek kullanıcılar izin sunucuda veritabanı.</span><span class="sxs-lookup"><span data-stu-id="fb071-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="fb071-128">Kısmi güven durumda çalışan istemci tarafı kod gerektiren <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="fb071-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="fb071-129">Aşağıdaki kod oluşturur bir <xref:System.Data.SqlClient.SqlClientPermission> ayar nesnesi <xref:System.Security.Permissions.PermissionState> için <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span><span class="sxs-lookup"><span data-stu-id="fb071-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="fb071-130"><xref:System.Security.CodeAccessPermission.Demand%2A> Zorlar bir <xref:System.Security.SecurityException> çağrı yığınında daha yüksek tüm çağıranların izni verilmemiş, çalışma zamanında.</span><span class="sxs-lookup"><span data-stu-id="fb071-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="fb071-131">Bir bildirim nesne seçme</span><span class="sxs-lookup"><span data-stu-id="fb071-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="fb071-132">Sorgu bildirimleri API'si bildirimleri işlemek için iki nesne sağlar: <xref:System.Data.SqlClient.SqlDependency> ve <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="fb071-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="fb071-133">Genel olarak, çoğu ASP.NET olmayan uygulamaları kullanması gereken <xref:System.Data.SqlClient.SqlDependency> nesne.</span><span class="sxs-lookup"><span data-stu-id="fb071-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="fb071-134">ASP.NET uygulamaları üst düzey kullanın <xref:System.Web.Caching.SqlCacheDependency>, sarmalayan <xref:System.Data.SqlClient.SqlDependency> ve bildirim ve önbellek nesneleri yönetmek için bir çerçeve sunar.</span><span class="sxs-lookup"><span data-stu-id="fb071-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="fb071-135">SqlDependency kullanma</span><span class="sxs-lookup"><span data-stu-id="fb071-135">Using SqlDependency</span></span>  
 <span data-ttu-id="fb071-136">Kullanılacak <xref:System.Data.SqlClient.SqlDependency>hizmet aracısı için kullanılan SQL Server veritabanı etkin olması ve kullanıcıların bildirimleri almak için izinlere sahip olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="fb071-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="fb071-137">Bildirim sırası gibi hizmet Aracısı nesneleri önceden tanımlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="fb071-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="fb071-138">Ayrıca, <xref:System.Data.SqlClient.SqlDependency> otomatik olarak başlatılan bir çalışan iş parçacığı kuyruğa gönderilen bildirimleri işlemek için; ayrıca olay bağımsız değişkeni veri bilgileri gösterme hizmet Aracısı iletiyi ayrıştırır.</span><span class="sxs-lookup"><span data-stu-id="fb071-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="fb071-139"><xref:System.Data.SqlClient.SqlDependency> çağırarak başlatılmalıdır `Start` veritabanına bir bağımlılık oluşturmak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="fb071-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="fb071-140">Gereken her bir veritabanı bağlantısı için uygulama başlatma sırasında yalnızca bir kez çağrılması gereken bir statik yöntem budur.</span><span class="sxs-lookup"><span data-stu-id="fb071-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="fb071-141">`Stop` Yöntemi sırasında yapılan her bir bağımlılık bağlantısı için uygulama sonlandırma çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="fb071-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="fb071-142">SqlNotificationRequest kullanma</span><span class="sxs-lookup"><span data-stu-id="fb071-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="fb071-143">Buna karşılık, <xref:System.Data.Sql.SqlNotificationRequest> tüm dinleme altyapısını kendi başınıza uygulamak gerektirir.</span><span class="sxs-lookup"><span data-stu-id="fb071-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="fb071-144">Ayrıca, kuyruğu, hizmet ve ileti kuyruğu tarafından desteklenen türleri gibi tüm destekleyici hizmet Aracısı nesnelerini tanımlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="fb071-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="fb071-145">El ile bu yaklaşım, uygulamanız özel bildirim iletileri ya da bildirim davranışları gerektiriyorsa veya uygulamanız daha büyük bir hizmet Aracısı uygulamanın parçası ise yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="fb071-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb071-146">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fb071-146">See also</span></span>

- [<span data-ttu-id="fb071-147">SQL Server'da Sorgu Bildirimleri</span><span class="sxs-lookup"><span data-stu-id="fb071-147">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [<span data-ttu-id="fb071-148">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="fb071-148">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
