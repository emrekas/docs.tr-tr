---
title: ADO.NET kod örnekleri
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 3bbb2e046054e35cf01fe223318a3bf560ef7253
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180732"
---
# <a name="adonet-code-examples"></a>ADO.NET kod örnekleri
Bu konudaki kod listeleri aşağıdaki ADO.NET teknolojileri kullanarak bir veritabanından veri almak nasıl ekleyebileceğiniz gösterilmektedir:

- ADO.NET veri sağlayıcıları:

  - [SqlClient](#sqlclient) (`System.Data.SqlClient`)

  - [OleDb](#oledb) (`System.Data.OleDb`)

  - [Odbc](#odbc) (`System.Data.Odbc`)

  - [OracleClient](#oracleclient) (`System.Data.OracleClient`)

- ADO.NET varlık çerçevesi:

  - [LINQ - Varlıklar](#linq-to-entities)

  - [Türü belirlenmiş ObjectQuery](#typed-objectquery)

  - [EntityClient](#entityclient) (`System.Data.EntityClient`)

- [LINQ - SQL](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a>ADO.NET veri sağlayıcı örneği
Aşağıdaki kod listeleri ADO.NET veri sağlayıcıları kullanarak bir veritabanından veri almak nasıl ekleyebileceğiniz gösterilmektedir. Veriler içerisinde geri dönmemiş ise bir `DataReader`. Daha fazla bilgi için [alma verileri kullanarak bir DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).

### <a name="sqlclient"></a>SqlClient
Bu örnekteki kod için bağlanabildiğinizi varsayar `Northwind` örnek veritabanını Microsoft SQL Server. Kod oluşturur bir <xref:System.Data.SqlClient.SqlCommand> Ürünler tablosundan satırları seçmek için ekleme bir <xref:System.Data.SqlClient.SqlParameter> sonuçları belirtilen parametre, bu durumda 5 değerinden bir UnitPrice satırları sınırlamak için. <xref:System.Data.SqlClient.SqlConnection> İçinde açılan bir `using` bloğu, kaynakları kapalı ve kod çıktığında elden emin olmanızı sağlar. Kod kullanarak komutu yürütür. bir <xref:System.Data.SqlClient.SqlDataReader>ve sonuçları konsol penceresinde görüntüler.

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a>OleDb
Bu örnekteki kod Microsoft Access Northwind örnek veritabanına bağlanabildiğinizi varsayar. Kod oluşturur bir <xref:System.Data.OleDb.OleDbCommand> Ürünler tablosundan satırları seçmek için ekleme bir <xref:System.Data.OleDb.OleDbParameter> sonuçları belirtilen parametre, bu durumda 5 değerinden bir UnitPrice satırları sınırlamak için. <xref:System.Data.OleDb.OleDbConnection> İçine açıldığında bir `using` bloğu, kaynakları kapalı ve kod çıktığında elden emin olmanızı sağlar. Kod kullanarak komutu yürütür. bir <xref:System.Data.OleDb.OleDbDataReader>ve sonuçları konsol penceresinde görüntüler.

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a>Odbc
Bu örnekteki kod Microsoft Access Northwind örnek veritabanına bağlanabildiğinizi varsayar. Kod oluşturur bir <xref:System.Data.Odbc.OdbcCommand> Ürünler tablosundan satırları seçmek için ekleme bir <xref:System.Data.Odbc.OdbcParameter> sonuçları belirtilen parametre, bu durumda 5 değerinden bir UnitPrice satırları sınırlamak için. <xref:System.Data.Odbc.OdbcConnection> İçinde açılan bir `using` bloğu, kaynakları kapalı ve kod çıktığında elden emin olmanızı sağlar. Kod kullanarak komutu yürütür. bir <xref:System.Data.Odbc.OdbcDataReader>ve sonuçları konsol penceresinde görüntüler.

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)] 
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)] 

### <a name="oracleclient"></a>OracleClient
Bu örnekteki kod tanıtım bağlantı varsayar. Bir Oracle sunucusunda müşteri. Ayrıca, System.Data.OracleClient.dll bir başvuru eklemeniz gerekir. Kod verileri döndürür bir <xref:System.Data.OracleClient.OracleDataReader>.

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a>Entity Framework örnekleri
Aşağıdaki kod listeleri varlıkları bir varlık veri modeli (EDM) sorgulayarak bir veri kaynağından veri almak nasıl ekleyebileceğiniz gösterilmektedir. Bu örnekler, Northwind örnek veritabanını temel alan bir model kullanır. Entity Framework hakkında daha fazla bilgi için bkz: [Entity Framework'e Genel Bakış](../../../../docs/framework/data/adonet/ef/overview.md).

### <a name="linq-to-entities"></a>LINQ - Varlıklar
Bu örnekteki kod, yalnızca kullanıcı, Categoryıd'si ve CategoryName özellikleri içeren bir anonim tür öngörülen kategorileri nesneleri olarak verileri döndürmek için LINQ sorgusu kullanır. Daha fazla bilgi için [LINQ to Entities genel bakış](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).

```csharp
using System;
using System.Linq;
using System.Data.Objects;
using NorthwindModel;

class LinqSample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            try
            {
                var query = from category in context.Categories
                            select new
                            {
                                categoryID = category.CategoryID,
                                categoryName = category.CategoryName
                            };

                foreach (var categoryInfo in query)
                {
                    Console.WriteLine("\t{0}\t{1}",
                        categoryInfo.categoryID, categoryInfo.categoryName);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Linq
Imports System.Data.Objects
Imports NorthwindModel

Class LinqSample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Try
                Dim query = From category In context.Categories _
                            Select New With _
                            { _
                                .categoryID = category.CategoryID, _
                                .categoryName = category.CategoryName _
                            }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                        categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

### <a name="typed-objectquery"></a>Türü belirlenmiş ObjectQuery
Bu örnekteki kod bir <xref:System.Data.Objects.ObjectQuery%601> veri kategorileri nesneler olarak döndürülecek. Daha fazla bilgi için [nesne sorgularını](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).

```csharp
using System;
using System.Data.Objects;
using NorthwindModel;

class ObjectQuerySample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            ObjectQuery<Categories> categoryQuery = context.Categories;

            foreach (Categories category in 
                categoryQuery.Execute(MergeOption.AppendOnly))
            {
                Console.WriteLine("\t{0}\t{1}",
                    category.CategoryID, category.CategoryName);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Data.Objects
Imports NorthwindModel

Class ObjectQuerySample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Dim categoryQuery As ObjectQuery(Of Categories) = context.Categories

            For Each category As Categories In _
                categoryQuery.Execute(MergeOption.AppendOnly)
                Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                    category.CategoryID, category.CategoryName)
            Next
        End Using
    End Sub
End Class
```

### <a name="entityclient"></a>EntityClient
Bu örnekteki kod bir <xref:System.Data.EntityClient.EntityCommand> varlık SQL sorgusu yürütülemedi. Bu sorgu kategorileri varlık türünün örneğini temsil eden kayıtlarını içeren bir liste döndürür. Bir <xref:System.Data.EntityClient.EntityDataReader> sonuç kümesinde veri kayıtlarını erişmek için kullanılır. Daha fazla bilgi için [Entity Framework için EntityClient sağlayıcısı](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.EntityClient;
using NorthwindModel;

class EntityClientSample
{
    public static void ExecuteQuery()
    {
        string queryString =
            @"SELECT c.CategoryID, c.CategoryName 
                FROM NorthwindEntities.Categories AS c";

        using (EntityConnection conn =
            new EntityConnection("name=NorthwindEntities"))
        {
            try
            {
                conn.Open();
                using (EntityCommand query = new EntityCommand(queryString, conn))
                {
                    using (DbDataReader rdr = 
                        query.ExecuteReader(CommandBehavior.SequentialAccess))
                    {
                        while (rdr.Read())
                        {
                            Console.WriteLine("\t{0}\t{1}", rdr[0], rdr[1]);
                        }
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Data
Imports System.Data.Common
Imports System.Data.EntityClient
Imports NorthwindModel

Class EntityClientSample
    Public Shared Sub ExecuteQuery()
        Dim queryString As String = _
            "SELECT c.CategoryID, c.CategoryName " & _
                "FROM NorthwindEntities.Categories AS c"

        Using conn As EntityConnection = _
            New EntityConnection("name=NorthwindEntities")

            Try
                conn.Open()
                Using query As EntityCommand = _
                New EntityCommand(queryString, conn)
                    Using rdr As DbDataReader = _
                        query.ExecuteReader(CommandBehavior.SequentialAccess)
                        While rdr.Read()
                            Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                                              rdr(0), rdr(1))
                        End While
                    End Using
                End Using
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using 
    End Sub
End Class
```

## <a name="linq-to-sql"></a>LINQ - SQL
Bu örnekteki kod, yalnızca kullanıcı, Categoryıd'si ve CategoryName özellikleri içeren bir anonim tür öngörülen kategorileri nesneleri olarak verileri döndürmek için LINQ sorgusu kullanır. Bu örnekte, Northwind veri bağlama temel alınmıştır. Daha fazla bilgi için [Başlarken](../../../../docs/framework/data/adonet/sql/linq/getting-started.md).

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Northwind;

    class LinqSqlSample
    {
        public static void ExecuteQuery()
        {
            using (NorthwindDataContext db = new NorthwindDataContext())
            {
                try
                {
                    var query = from category in db.Categories
                                select new
                                {
                                    categoryID = category.CategoryID,
                                    categoryName = category.CategoryName
                                };

                    foreach (var categoryInfo in query)
                    {
                        Console.WriteLine("vbTab {0} vbTab {1}",
                            categoryInfo.categoryID, categoryInfo.categoryName);
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine(ex.Message);
                }
            }
        }
    }
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports Northwind

Class LinqSqlSample
    Public Shared Sub ExecuteQuery()
        Using db As NorthwindDataContext = New NorthwindDataContext()
            Try
                Dim query = From category In db.Categories _
                                Select New With _
                                { _
                                    .categoryID = category.CategoryID, _
                                    .categoryName = category.CategoryName _
                                }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                            categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
            End Using 
    End Sub
End Class
```

## <a name="see-also"></a>Ayrıca bkz.

- [ADO.NET’e Genel Bakış](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [ADO.NET’te Veri Alma ve Değiştirme](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Veri Uygulamaları Oluşturma](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))
- [Bir varlık veri modeli (varlık çerçevesi görevler) sorgulama](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))
- [Nasıl yapılır: Anonim türdeki nesneleri döndüren bir sorgu yürütme](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))
- [ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi](https://go.microsoft.com/fwlink/?LinkId=217917)
