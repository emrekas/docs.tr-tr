---
title: Şema Kısıtlamaları
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: d0250e573dc24bfcad97a2f2606cb2e6c8e520da
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782763"
---
# <a name="schema-restrictions"></a>Şema Kısıtlamaları
**GetSchema** yönteminin ikinci isteğe bağlı parametresi döndürülen şema bilgisi miktarını sınırlamak için kullanılan kısıtlamalardır ve **GetSchema** yöntemine dizeler dizisi olarak geçirilir. Dizideki konum, geçirebileceğinizi belirten değerleri belirler ve bu, kısıtlama numarasına eşdeğerdir.  
  
 Örneğin, aşağıdaki tabloda SQL Server için .NET Framework Veri Sağlayıcısı kullanılarak "tablolar" şema koleksiyonu tarafından desteklenen kısıtlamalar açıklanmaktadır. SQL Server şema koleksiyonları için ek kısıtlamalar bu konunun sonunda listelenmiştir.  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1\.|  
|Sahip|@Owner|TABLE_SCHEMA|2|  
|Tablo|@Name|TABLE_NAME|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
## <a name="specifying-restriction-values"></a>Kısıtlama değerlerini belirtme  
 "Tables" şema koleksiyonu kısıtlamalarından birini kullanmak için, dört öğeli bir dize dizisi oluşturmanız yeterlidir, sonra bir değeri kısıtlama numarasıyla eşleşen bir değere yerleştirebilirsiniz. Örneğin, **GetSchema** yöntemi tarafından döndürülen tabloları yalnızca "Sales" şemasında bulunan tablolara kısıtlamak için, dizinin Ikinci öğesini **GetSchema** yöntemine geçirmeden önce "Sales" olarak ayarlayın.  
  
> [!NOTE]
> İçin `SqlClient` kısıtlamalar koleksiyonları ve `OracleClient` ek `ParameterName` bir sütun vardır. Kısıtlama varsayılan sütunu, geriye doğru uyumluluk için hala mevcuttur, ancak şu anda yok sayılır. Kısıtlama değerlerini belirtirken bir SQL ekleme saldırısının riskini en aza indirmek için, dize değiştirme yerine parametreli sorgular kullanılmalıdır.  
  
> [!NOTE]
> Dizideki öğe sayısı, belirtilen şema koleksiyonu için desteklenen kısıtlama sayısına eşit veya ondan küçük olmalıdır, aksi takdirde bir <xref:System.ArgumentException> oluşturulur. En yüksek kısıtlama sayısından daha az olabilir. Eksik kısıtlamaların null (Kısıtlanmamış) olduğu varsayılır.  
  
 "Kısıtlamalar" olan kısıtlama şeması koleksiyonu adı ile **GetSchema** yöntemini çağırarak desteklenen kısıtlamaların listesini öğrenmek için, .NET Framework yönetilen bir sağlayıcıyı sorgulayabilirsiniz. Bu, koleksiyon adlarının <xref:System.Data.DataTable> , kısıtlama adlarının, varsayılan kısıtlama değerlerinin ve kısıtlama numaralarının listesini içeren bir döndürür.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örneklerde, **AdventureWorks** örnek veritabanında bulunan tüm <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> tablolar hakkında şema bilgilerini almak için SQL Server <xref:System.Data.SqlClient.SqlConnection> sınıfının .NET Framework veri sağlayıcısı yönteminin nasıl kullanılacağı gösterilmektedir. ve döndürülen bilgileri yalnızca "Sales" şemasında bulunan tablolara kısıtlamak için:  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =   
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",   
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a>SQL Server şeması kısıtlamaları  
 Aşağıdaki tablolarda SQL Server şema koleksiyonları için kısıtlamalar listelenmektedir.  
  
### <a name="users"></a>Kullanıcılar  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Kullanıcı_adı|@Name|name|1\.|  
  
### <a name="databases"></a>Veritabanları  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Ad|@Name|Ad|1\.|  
  
### <a name="tables"></a>Takvimleri  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1\.|  
|Sahip|@Owner|TABLE_SCHEMA|2|  
|Tablo|@Name|TABLE_NAME|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
### <a name="columns"></a>Sütunlar  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1\.|  
|Sahip|@Owner|TABLE_SCHEMA|2|  
|Tablo|@Table|TABLE_NAME|3|  
|Sütun|@Column|COLUMN_NAME|4|  
  
### <a name="structuredtypemembers"></a>StructuredTypeMembers  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1\.|  
|Sahip|@Owner|TABLE_SCHEMA|2|  
|Tablo|@Table|TABLE_NAME|3|  
|Sütun|@Column|COLUMN_NAME|4|  
  
### <a name="views"></a>Görünümler  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1\.|  
|Sahip|@Owner|TABLE_SCHEMA|2|  
|Tablo|@Table|TABLE_NAME|3|  
  
### <a name="viewcolumns"></a>ViewColumns  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|VIEW_CATALOG|1\.|  
|Sahip|@Owner|VIEW_SCHEMA|2|  
|Tablo|@Table|VIEW_NAME|3|  
|Sütun|@Column|COLUMN_NAME|4|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|SPECIFIC_CATALOG|1\.|  
|Sahip|@Owner|SPECIFIC_SCHEMA|2|  
|Ad|@Name|SPECIFIC_NAME|3|  
|Parametre|@Parameter|PARAMETER_NAME|4|  
  
### <a name="procedures"></a>Yordamlar  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|SPECIFIC_CATALOG|1\.|  
|Sahip|@Owner|SPECIFIC_SCHEMA|2|  
|Ad|@Name|SPECIFIC_NAME|3|  
|Tür|@Type|ROUTINE_TYPE|4|  
  
### <a name="indexcolumns"></a>IndexColumns  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|db_name()|1\.|  
|Sahip|@Owner|user_name ()|2|  
|Tablo|@Table|o.name|3|  
|ConstraintName|@ConstraintName|x.name|4|  
|Sütun|@Column|c.name|5|  
  
### <a name="indexes"></a>Dizinlerde  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|db_name()|1\.|  
|Sahip|@Owner|user_name ()|2|  
|Tablo|@Table|o.name|3|  
  
### <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|assembly_name|@AssemblyName|assemblies.name|1\.|  
|udt_name|@UDTName|Types. assembly_class|2|  
  
### <a name="foreignkeys"></a>Yabancıanahtarlar  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|CONSTRAINT_CATALOG|1\.|  
|Sahip|@Owner|CONSTRAINT_SCHEMA|2|  
|Tablo|@Table|TABLE_NAME|3|  
|Ad|@Name|CONSTRAINT_NAME|4|  
  
## <a name="sql-server-2008-schema-restrictions"></a>SQL Server 2008 şema kısıtlamaları  
 Aşağıdaki tablolarda SQL Server 2008 şema koleksiyonları için kısıtlamalar listelenmektedir. Bu kısıtlamalar .NET Framework sürüm 3,5 SP1 ve 2008 SQL Server itibaren geçerlidir. .NET Framework ve SQL Server daha önceki sürümlerinde desteklenmez.  
  
### <a name="columnsetcolumns"></a>ColumnSetColumns  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1\.|  
|Sahip|@Owner|TABLE_SCHEMA|2|  
|Tablo|@Table|TABLE_NAME|3|  
  
### <a name="allcolumns"></a>AllColumns  
  
|Kısıtlama adı|Parametre Adı|Kısıtlama varsayılanı|Kısıtlama numarası|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1\.|  
|Sahip|@Owner|TABLE_SCHEMA|2|  
|Tablo|@Table|TABLE_NAME|3|  
|Sütun|@Column|COLUMN_NAME|4|  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ADO.NET’e Genel Bakış](ado-net-overview.md)
