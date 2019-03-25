---
title: FILESTREAM verileri
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: 1dea5d1e2f40c44e8f24bdbc9742288429d9933a
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410283"
---
# <a name="filestream-data"></a>FILESTREAM verileri

FILESTREAM depolama alanı özniteliğe VARBINARY(max) sütunda depolanan ikili (BLOB) veri içindir. FILESTREAM önce özel işlem ikili verilerin depolanması gerekir. Metin belgeleri, görüntüler ve video gibi yapılandırılmamış verileri yönetmek zorlaştıran veritabanı haricinde, genellikle depolanır.

> [!NOTE]
> .NET Framework 3.5 SP1'i yüklemeniz gerekir (veya üzeri) SqlClient kullanarak FILESTREAM verilerle çalışmak için.

FILESTREAM özniteliğine VARBINARY(max) sütun belirterek SQL Server'ın yerel NTFS dosya sistemi yerine veritabanı dosyasındaki verileri depolamak neden olur. Ayrı olarak depolanır, ancak aynı kullanabilirsiniz [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] deyimleri veritabanında depolanan VARBINARY(max) verilerle çalışmak için desteklenir.

## <a name="sqlclient-support-for-filestream"></a>FILESTREAM için SqlClient desteği

[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] SQL Server için veri sağlayıcısı <xref:System.Data.SqlClient>, FILESTREAM kullanarak veri yazma ve okuma destekler <xref:System.Data.SqlTypes.SqlFileStream> sınıfı içinde tanımlanan <xref:System.Data.SqlTypes> ad alanı. `SqlFileStream` devralınan <xref:System.IO.Stream> veri akışları için yazma ve okuma için yöntemler sağlar sınıfını. Bir akıştan okuma bayt dizisi gibi bir veri yapısı içine akıştan verileri aktarır. Yazma, verileri veri yapısından bir akışa aktarır.

### <a name="creating-the-sql-server-table"></a>SQL Server tablo oluşturma

Aşağıdaki [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] deyimleri employees adlı bir tablo oluşturur ve bir veri satırı ekler. FILESTREAM depolama etkinleştirdikten sonra izleyen kod örnekleri ile birlikte bu tabloyu kullanın. SQL Server Books Online kaynaklarına bağlantılar, bu konunun sonunda yer alır.

```sql
CREATE TABLE employees
(
  EmployeeId INT  NOT NULL  PRIMARY KEY,
  Photo VARBINARY(MAX) FILESTREAM  NULL,
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL
  UNIQUE DEFAULT NEWID()
)
GO
Insert into employees
Values(1, 0x00, default)
GO
```

### <a name="example-reading-overwriting-and-inserting-filestream-data"></a>Örnek: Okuma, üzerine ve FILESTREAM veri ekleme

Aşağıdaki örnek, bir FILESTREAM verileri okumak gösterilmiştir. Ayar dosyasının mantıksal yolu kodunu alır `FileAccess` için `Read` ve `FileOptions` için `SequentialScan`. Kodu daha sonra bayt arabelleğe SqlFileStream okur. Bayt, ardından konsol penceresinde yazılır.

Örnek, ayrıca tüm mevcut veriler yazılır bir FILESTREAM için veri yazmak nasıl gösterir. Kod mantıksal dosyanın yolunu alır ve oluşturur `SqlFileStream`ayarını `FileAccess` için `Write` ve `FileOptions` için `SequentialScan`. Tek bir bayt yazılır `SqlFileStream`, dosyadaki tüm verileri değiştirme.

Örnek ayrıca, dosyanın sonuna veri eklemek için arama yöntemi kullanılarak için bir FILESTREAM veri yazmak nasıl gösterir. Kod mantıksal dosyanın yolunu alır ve oluşturur `SqlFileStream`ayarını `FileAccess` için `ReadWrite` ve `FileOptions` için `SequentialScan`. Kod, bir tek baytlı varolan dosyaya ekleme dosyanın sonuna aramak için arama yöntemi kullanır.

```csharp
using System;
using System.Data.SqlClient;
using System.Data.SqlTypes;
using System.Data;
using System.IO;

namespace FileStreamTest
{
    class Program
    {
        static void Main(string[] args)
        {
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");
            ReadFileStream(builder);
            OverwriteFileStream(builder);
            InsertFileStream(builder);

            Console.WriteLine("Done");
        }

        private static void ReadFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for the file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        // Create the SqlFileStream
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Read the contents as bytes and write them to the console
                            for (long index = 0; index < fileStream.Length; index++)
                            {
                                Console.WriteLine(fileStream.ReadByte());
                            }
                        }
                    }
                }
                tran.Commit();
            }
        }

        private static void OverwriteFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();

                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        // Create the SqlFileStream
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Write a single byte to the file. This will
                            // replace any data in the file.
                            fileStream.WriteByte(0x01);
                        }
                    }
                }
                tran.Commit();
            }
        }

        private static void InsertFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();

                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Seek to the end of the file
                            fileStream.Seek(0, SeekOrigin.End);

                            // Append a single byte
                            fileStream.WriteByte(0x01);
                        }
                    }
                }
                tran.Commit();
            }

        }
    }
}
```

Başka bir örnek için bkz: [depolamak ve bir dosya akışı sütuna ikili verileri getirmek nasıl](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).

## <a name="resources-in-sql-server-books-online"></a>SQL Server Çevrimiçi Kitapları'nda kaynaklar

FILESTREAM için kapsamlı belgeler, aşağıdaki bölümlerde SQL Server Çevrimiçi Kitapları'nda bulunur.

|Konu|Açıklama|
|-----------|-----------------|
|[FILESTREAM (SQL Server)](/sql/relational-databases/blob/filestream-sql-server)|FILESTREAM depolama kullanmak ne zaman ve nasıl bir NTFS dosya sistemi ile SQL Server veritabanı altyapısı tümleştirildiğini açıklar.|
|[FILESTREAM verileri için istemci uygulamalar oluşturun](/sql/relational-databases/blob/create-client-applications-for-filestream-data)|FILESTREAM verileri ile çalışma için Windows API işlevleri açıklar.|
|[FILESTREAM ve diğer SQL Server özellikleri](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|Dikkat edilecek noktalar, yönergeleri ve sınırlamaları kullanarak SQL Server'ın diğer özelliklerle FILESTREAM verileri için sağlar.|

## <a name="see-also"></a>Ayrıca bkz.

- [SQL Server Veri Türleri ve ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [ADO.NET’te Veri Alma ve Değiştirme](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Kod Erişimi Güvenliği ve ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)
- [SQL Server İkili ve Büyük Değerli Veriler](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [ADO.NET’e Genel Bakış](../../../../../docs/framework/data/adonet/ado-net-overview.md)
