---
title: Tablo Değerli Parametreler
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: ccef487eb27a5a170d197a6bc670ec4d2bcf8bdf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645793"
---
# <a name="table-valued-parameters"></a><span data-ttu-id="56f4f-102">Tablo Değerli Parametreler</span><span class="sxs-lookup"><span data-stu-id="56f4f-102">Table-Valued Parameters</span></span>
<span data-ttu-id="56f4f-103">Tablo değerli parametreler birden çok gidiş dönüş veya özel sunucu tarafı mantık verilerin işlenmesi için gerek kalmadan birden çok SQL Server için bir istemci uygulamasından veri satırı sıralama için kolay bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="56f4f-103">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to SQL Server without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="56f4f-104">Bir istemci uygulamasında veri satırı kapsüllemek ve tek bir Parametreli komutu sunucuda veri göndermek için tablo değerli parametreleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56f4f-104">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="56f4f-105">Gelen veri satırları sonra üzerinde kullanarak işletilebilir bir tablo değişkeninde depolanan [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56f4f-105">The incoming data rows are stored in a table variable that can then be operated on by using [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="56f4f-106">Sütun değerleri tablo değerli parametreleri standardını kullanarak erişilebilir [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] SELECT deyimleri.</span><span class="sxs-lookup"><span data-stu-id="56f4f-106">Column values in table-valued parameters can be accessed using standard [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] SELECT statements.</span></span> <span data-ttu-id="56f4f-107">Tablo değerli parametre kesin olarak belirlenmiştir ve yapılarını otomatik olarak doğrulanır.</span><span class="sxs-lookup"><span data-stu-id="56f4f-107">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="56f4f-108">Tablo değerli parametre boyutunu, yalnızca sunucu bellekle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="56f4f-108">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56f4f-109">Tablo değerli parametre veri döndüremez.</span><span class="sxs-lookup"><span data-stu-id="56f4f-109">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="56f4f-110">Tablo değerli salt giriş parametreleridir; Çıkış anahtar sözcüğü desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="56f4f-110">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="56f4f-111">Tablo değerli parametreler hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın.</span><span class="sxs-lookup"><span data-stu-id="56f4f-111">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="56f4f-112">Kaynak</span><span class="sxs-lookup"><span data-stu-id="56f4f-112">Resource</span></span>|<span data-ttu-id="56f4f-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="56f4f-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="56f4f-114">[Tablo değerli parametreleri (veritabanı altyapısı)](https://go.microsoft.com/fwlink/?LinkId=98363) SQL Server Çevrimiçi Kitapları'nda</span><span class="sxs-lookup"><span data-stu-id="56f4f-114">[Table-Valued Parameters (Database Engine)](https://go.microsoft.com/fwlink/?LinkId=98363) in SQL Server Books Online</span></span>|<span data-ttu-id="56f4f-115">Tablo değerli parametreleri oluşturup kullanacağınızı açıklar.</span><span class="sxs-lookup"><span data-stu-id="56f4f-115">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="56f4f-116">[Kullanıcı tanımlı tablo türleri](https://go.microsoft.com/fwlink/?LinkId=98364) SQL Server Çevrimiçi Kitapları'nda</span><span class="sxs-lookup"><span data-stu-id="56f4f-116">[User-Defined Table Types](https://go.microsoft.com/fwlink/?LinkId=98364) in SQL Server Books Online</span></span>|<span data-ttu-id="56f4f-117">Tablo değerli parametreleri bildirmek için kullanılan kullanıcı tanımlı tablo türleri açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="56f4f-117">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="56f4f-118">SQL Server'ın önceki sürümlerinde birden çok satır geçirme</span><span class="sxs-lookup"><span data-stu-id="56f4f-118">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  
 <span data-ttu-id="56f4f-119">Tablo değerli parametreleri SQL Server 2008'e sunulmadan önce bir saklı yordam ya da bir parametreleştirilmiş SQL komutu için birden çok sayıda veri geçirmek için seçenekleri sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="56f4f-119">Before table-valued parameters were introduced to SQL Server 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="56f4f-120">Bir geliştirici, birden çok satır sunucuya geçirmek için aşağıdaki seçeneklerden seçebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="56f4f-120">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
- <span data-ttu-id="56f4f-121">Birden çok sütun ve satır veri değerleri temsil etmek için bir dizi bağımsız parametreleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="56f4f-121">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="56f4f-122">Bu yöntem kullanılarak geçirilebilir veri miktarı tarafından izin verilen parametre sayısı sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="56f4f-122">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> <span data-ttu-id="56f4f-123">SQL Server yordamları en fazla 2100 parametreleri olabilir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-123">SQL Server procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="56f4f-124">Sunucu tarafı mantık tablo değişkeni veya geçici bir tablo işleme için bu değerlerin derlemek için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-124">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
- <span data-ttu-id="56f4f-125">Birden çok veri değeri, ayrılmış bir dize veya XML belgeleri paket ve ardından bu metin değerlerini bir yordam veya deyimi geçirin.</span><span class="sxs-lookup"><span data-stu-id="56f4f-125">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="56f4f-126">Bu yordamı veya veri yapılarını ve unbundling doğrulamak için gerekli mantığı bildirimini değerleri gerektirir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-126">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
- <span data-ttu-id="56f4f-127">Bir dizi çağırarak oluşturulanlar gibi birden çok satır etkileyen değişiklikleri için ayrı SQL deyimi oluşturmak `Update` yöntemi bir <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="56f4f-127">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="56f4f-128">Değişiklikler tek tek sunucuya gönderilen veya gruplar halinde toplu.</span><span class="sxs-lookup"><span data-stu-id="56f4f-128">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="56f4f-129">Ancak, hatta birden fazla deyim içeren toplu olarak gönderildiğinde her deyim ayrı ayrı sunucuda yürütülür.</span><span class="sxs-lookup"><span data-stu-id="56f4f-129">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
- <span data-ttu-id="56f4f-130">Kullanım `bcp` yardımcı programı veya <xref:System.Data.SqlClient.SqlBulkCopy> birçok veri satırı bir tabloya yüklemek için nesne.</span><span class="sxs-lookup"><span data-stu-id="56f4f-130">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="56f4f-131">Bu teknik çok etkili olsa da, verileri bir geçici tablo veya tablo değişkeni içine yüklenen sürece, sunucu tarafı işleme desteklemez.</span><span class="sxs-lookup"><span data-stu-id="56f4f-131">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="56f4f-132">Tablo değerli parametre türleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="56f4f-132">Creating Table-Valued Parameter Types</span></span>  
 <span data-ttu-id="56f4f-133">Tablo değerli parametreleri kullanılarak tanımlanmış tabloyu kesin tür belirtilmiş yapıları dayanır [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] türü oluştur deyimleri.</span><span class="sxs-lookup"><span data-stu-id="56f4f-133">Table-valued parameters are based on strongly-typed table structures that are defined by using [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] CREATE TYPE statements.</span></span> <span data-ttu-id="56f4f-134">Bir tablo türü oluştur, istemci uygulamalarınız tablo değerli parametre kullanmadan önce SQL Server'da yapısı tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-134">You have to create a table type and define the structure in SQL Server before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="56f4f-135">Tablo türleri oluşturma hakkında daha fazla bilgi için bkz. [kullanıcı tanımlı tablo türleri](https://go.microsoft.com/fwlink/?LinkID=98364) SQL Server Books Online.</span><span class="sxs-lookup"><span data-stu-id="56f4f-135">For more information about creating table types, see [User-Defined Table Types](https://go.microsoft.com/fwlink/?LinkID=98364) in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="56f4f-136">Aşağıdaki deyim, kullanıcı, Categoryıd'si ve CategoryName sütundan oluşan CategoryTableType adlı bir tablo türü oluşturur:</span><span class="sxs-lookup"><span data-stu-id="56f4f-136">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```  
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="56f4f-137">Bir tablo türü oluşturduktan sonra o türde bağlı tablo değerli parametreler bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56f4f-137">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="56f4f-138">Aşağıdaki [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] parça bir saklı yordam tanımında tablo değerli bir parametre bildirmek nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-138">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="56f4f-139">READONLY anahtar sözcüğü bir tablo değerli parametre bildirmek için gerekli olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="56f4f-139">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```  
CREATE PROCEDURE usp_UpdateCategories   
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="56f4f-140">Tablo değerli parametreleri (Transact-SQL) ile verileri değiştirme</span><span class="sxs-lookup"><span data-stu-id="56f4f-140">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  
 <span data-ttu-id="56f4f-141">Tablo değerli parametre birden çok satır tek bir deyimde yürüterek etkileyen veri kümesi tabanlı değişiklikler kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-141">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="56f4f-142">Örneğin, bir tablo değerli parametre tüm satırları seçin ve bunları bir veritabanı tablosuna eklemek veya güncelleştirmek istediğiniz tabloya bir tablo değerli parametre katılarak bir güncelleştirme deyimiyle oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56f4f-142">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="56f4f-143">Aşağıdaki [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] güncelleştirme bildirimi kategorileri tabloya katılarak tablo değerli bir parametre kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-143">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="56f4f-144">Bir birleştirme işleminde bir FROM yan tümcesi içeren bir tablo değerli parametre kullandığınızda, ayrıca diğer adı, tablo değerli parametre "AB" Next olduğu burada gösterildiği gibi gerekir:</span><span class="sxs-lookup"><span data-stu-id="56f4f-144">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```  
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="56f4f-145">Bu [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] örnek tablo değerli bir parametre kümesi tabanlı tek bir işlem ile INSERT işlemi satırları seçmek nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-145">This [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```  
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="56f4f-146">Tablo değerli parametre sınırlamaları</span><span class="sxs-lookup"><span data-stu-id="56f4f-146">Limitations of Table-Valued Parameters</span></span>  
 <span data-ttu-id="56f4f-147">Tablo değerli parametrelere birkaç sınırlama vardır:</span><span class="sxs-lookup"><span data-stu-id="56f4f-147">There are several limitations to table-valued parameters:</span></span>  
  
- <span data-ttu-id="56f4f-148">Tablo değerli parametre geçirilemez [kullanıcı tanımlı CLR işlevleri](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span><span class="sxs-lookup"><span data-stu-id="56f4f-148">You cannot pass table-valued parameters to [CLR user-defined functions](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span></span>  
  
- <span data-ttu-id="56f4f-149">Tablo değerli parametrelere, yalnızca UNIQUE ve PRIMARY KEY kısıtlamaları destekleyecek şekilde sıralanabilir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-149">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> <span data-ttu-id="56f4f-150">SQL Server tablo değerli parametre istatistiklerle korumaz.</span><span class="sxs-lookup"><span data-stu-id="56f4f-150">SQL Server does not maintain statistics on table-valued parameters.</span></span>  
  
- <span data-ttu-id="56f4f-151">Tablo değerli parametre, salt okunur [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] kod.</span><span class="sxs-lookup"><span data-stu-id="56f4f-151">Table-valued parameters are read-only in [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="56f4f-152">Tablo değerli bir parametre satırlarını sütun değerleri güncelleştirilemiyor ve ekleyemez veya satırları sil.</span><span class="sxs-lookup"><span data-stu-id="56f4f-152">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="56f4f-153">Bir saklı yordam için geçirilen veya tablo değerli parametre deyiminde parametreli verileri değiştirmek için verileri geçici bir tablo veya tablo değişkeni eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-153">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
- <span data-ttu-id="56f4f-154">Tablo değerli parametre tasarımını değiştirmek için ALTER TABLE deyimleri kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="56f4f-154">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="56f4f-155">SqlParameter örnek yapılandırma</span><span class="sxs-lookup"><span data-stu-id="56f4f-155">Configuring a SqlParameter Example</span></span>  
 <span data-ttu-id="56f4f-156"><xref:System.Data.SqlClient> Tablo değerli parametreler doldurma destekler <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> veya <xref:System.Collections.Generic.IEnumerable%601>  \  <xref:Microsoft.SqlServer.Server.SqlDataRecord> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="56f4f-156"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> objects.</span></span> <span data-ttu-id="56f4f-157">Tablo değerli parametresi için bir tür adını kullanarak belirtmelisiniz <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> özelliği bir <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="56f4f-157">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="56f4f-158">`TypeName` Sunucuda daha önce oluşturduğunuz uyumlu bir tür adıyla eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-158">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="56f4f-159">Aşağıdaki kod parçası nasıl yapılandırılacağını gösteren <xref:System.Data.SqlClient.SqlParameter> veri eklemek için.</span><span class="sxs-lookup"><span data-stu-id="56f4f-159">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  
 
<span data-ttu-id="56f4f-160">Aşağıdaki örnekte, `addedCategories` değişkenini içeren bir <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="56f4f-160">In the following example, the `addedCategories` variable contains a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="56f4f-161">Değişken nasıl doldurulur görmek için sonraki bölümde yer alan örnekler görmek [Table-Valued parametresi için bir saklı yordam geçirme](#passing).</span><span class="sxs-lookup"><span data-stu-id="56f4f-161">To see how the variable is populated, see the examples in the next section, [Passing a Table-Valued Parameter to a Stored Procedure](#passing).</span></span>

```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```  
  
```vb  
' Configure the command and parameter.  
Dim insertCommand As New SqlCommand(sqlInsert, connection)  
Dim tvpParam As SqlParameter = _  
   insertCommand.Parameters.AddWithValue( _  
  "@tvpNewCategories", addedCategories)  
tvpParam.SqlDbType = SqlDbType.Structured  
tvpParam.TypeName = "dbo.CategoryTableType"  
```  
  
 <span data-ttu-id="56f4f-162">Öğesinden türetilen herhangi bir nesne kullanabilirsiniz <xref:System.Data.Common.DbDataReader> bu parçasını gösterildiği gibi bir tablo değerli parametre veri akışı satır:</span><span class="sxs-lookup"><span data-stu-id="56f4f-162">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
```vb  
' Configure the SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  dataReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
```  
  
## <a name="passing"></a> <span data-ttu-id="56f4f-163">Tablo değerli bir parametre için bir saklı yordam geçirme</span><span class="sxs-lookup"><span data-stu-id="56f4f-163">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="56f4f-164">Bu örnek nasıl tablo değerli parametre veri saklı yordama geçirileceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-164">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="56f4f-165">Eklenen satırlarla kod yeni bir ayıklar <xref:System.Data.DataTable> kullanarak <xref:System.Data.DataTable.GetChanges%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="56f4f-165">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="56f4f-166">Ardından kodu tanımlayan bir <xref:System.Data.SqlClient.SqlCommand>ayarını <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> özelliğini <xref:System.Data.CommandType.StoredProcedure>.</span><span class="sxs-lookup"><span data-stu-id="56f4f-166">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="56f4f-167"><xref:System.Data.SqlClient.SqlParameter> Kullanarak doldurulur <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> yöntemi ve <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> ayarlanır `Structured`.</span><span class="sxs-lookup"><span data-stu-id="56f4f-167">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="56f4f-168"><xref:System.Data.SqlClient.SqlCommand> Kullanarak yürütülür <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="56f4f-168">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection object.  
Using connection  
   '  Create a DataTable with the modified rows.  
   Dim addedCategories As DataTable = _  
     CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Configure the SqlCommand and SqlParameter.  
   Dim insertCommand As New SqlCommand( _  
     "usp_InsertCategories", connection)  
   insertCommand.CommandType = CommandType.StoredProcedure  
   Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
     "@tvpNewCategories", addedCategories)  
   tvpParam.SqlDbType = SqlDbType.Structured  
  
   '  Execute the command.  
   insertCommand.ExecuteNonQuery()  
End Using  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="56f4f-169">Bir parametreli SQL deyimi için tablo değerli bir parametre geçirme</span><span class="sxs-lookup"><span data-stu-id="56f4f-169">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  
 <span data-ttu-id="56f4f-170">Aşağıdaki örnek veri dbo nasıl ekleneceğini gösterir. Veri kaynağı olarak bir tablo değerli parametresi olan bir SELECT alt sorgu INSERT deyimini kullanarak tablo kategorileri.</span><span class="sxs-lookup"><span data-stu-id="56f4f-170">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="56f4f-171">Bir parametreli SQL deyimi için tablo değerli bir parametre geçirerek, yeni kullanarak tablo değerli parametresi için bir tür adı belirtmelisiniz <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> özelliği bir <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="56f4f-171">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="56f4f-172">Bu `TypeName` sunucuda daha önce oluşturduğunuz uyumlu bir tür adıyla eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-172">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="56f4f-173">Bu örnekteki kod `TypeName` dbo içinde tanımlanan tür yapısına başvurmak için özellik. CategoryTableType.</span><span class="sxs-lookup"><span data-stu-id="56f4f-173">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56f4f-174">Tablo değerli bir parametre olarak bir kimlik sütunu için bir değer sağlarsanız, oturumu için AYARLANMIŞ IDENTITY_INSERT deyimi yayımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="56f4f-174">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =   
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
Using connection  
  ' Create a DataTable with the modified rows.  
  Dim addedCategories As DataTable = _  
    CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Define the INSERT-SELECT statement.  
  Dim sqlInsert As String = _  
  "INSERT INTO dbo.Categories (CategoryID, CategoryName)" _  
  & " SELECT nc.CategoryID, nc.CategoryName" _  
  & " FROM @tvpNewCategories AS nc;"  
  
  ' Configure the command and parameter.  
  Dim insertCommand As New SqlCommand(sqlInsert, connection)  
  Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
    "@tvpNewCategories", addedCategories)  
  tvpParam.SqlDbType = SqlDbType.Structured  
  tvpParam.TypeName = "dbo.CategoryTableType"  
  
  ' Execute the query  
  insertCommand.ExecuteNonQuery()  
End Using  
```  
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="56f4f-175">DataReader ile akış satırları</span><span class="sxs-lookup"><span data-stu-id="56f4f-175">Streaming Rows with a DataReader</span></span>  
 <span data-ttu-id="56f4f-176">Öğesinden türetilen herhangi bir nesne kullanabilirsiniz <xref:System.Data.Common.DbDataReader> tablo değerli bir parametre veri akışı satır.</span><span class="sxs-lookup"><span data-stu-id="56f4f-176">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="56f4f-177">Aşağıdaki kod parçası kullanarak bir Oracle veritabanından veri alma gösterir bir <xref:System.Data.OracleClient.OracleCommand> ve <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="56f4f-177">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="56f4f-178">Kodu daha sonra yapılandırır bir <xref:System.Data.SqlClient.SqlCommand> tek bir giriş parametresi olan bir saklı yordam çağırmak için.</span><span class="sxs-lookup"><span data-stu-id="56f4f-178">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="56f4f-179"><xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> Özelliği <xref:System.Data.SqlClient.SqlParameter> ayarlanır `Structured`.</span><span class="sxs-lookup"><span data-stu-id="56f4f-179">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="56f4f-180"><xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> Geçirir `OracleDataReader` sonuç kümesi saklı yordam tablo değerli bir parametre olarak.</span><span class="sxs-lookup"><span data-stu-id="56f4f-180">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
' Retrieve data from Oracle.  
Dim selectCommand As New OracleCommand( _  
  "Select CategoryID, CategoryName FROM Categories;", _  
  oracleConnection)  
Dim oracleReader As OracleDataReader = _  
  selectCommand.ExecuteReader(CommandBehavior.CloseConnection)  
  
' Configure SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  oracleReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
  
' Execute the command.  
insertCommand.ExecuteNonQuery()  
```  
  
## <a name="see-also"></a><span data-ttu-id="56f4f-181">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="56f4f-181">See also</span></span>

- [<span data-ttu-id="56f4f-182">Parametreleri ve Parametre Veri Türlerini Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="56f4f-182">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="56f4f-183">Komutlar ve Parametreler</span><span class="sxs-lookup"><span data-stu-id="56f4f-183">Commands and Parameters</span></span>](../../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="56f4f-184">DataAdapter Parametreleri</span><span class="sxs-lookup"><span data-stu-id="56f4f-184">DataAdapter Parameters</span></span>](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)
- [<span data-ttu-id="56f4f-185">ADO.NET’te SQL Server Veri İşlemleri</span><span class="sxs-lookup"><span data-stu-id="56f4f-185">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)
- [<span data-ttu-id="56f4f-186">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="56f4f-186">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
