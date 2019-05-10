---
title: OracleTypes
ms.date: 03/30/2017
ms.assetid: 18143304-d5c7-4c95-9995-678088d0c142
ms.openlocfilehash: eb45bc5b7bc317d04f5275afadbb1879117e3af0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586951"
---
# <a name="oracletypes"></a><span data-ttu-id="86f81-102">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="86f81-102">OracleTypes</span></span>
<span data-ttu-id="86f81-103">Oracle için .NET Framework veri sağlayıcısı, Oracle veri türleriyle çalışmak için kullanabileceğiniz çeşitli yapıları içerir.</span><span class="sxs-lookup"><span data-stu-id="86f81-103">The .NET Framework Data Provider for Oracle includes several structures you can use to work with Oracle data types.</span></span> <span data-ttu-id="86f81-104">Bunlar <xref:System.Data.OracleClient.OracleNumber> ve <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="86f81-104">These include <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86f81-105">Bu yapılar tam bir listesi için bkz. <xref:System.Data.OracleClient>.</span><span class="sxs-lookup"><span data-stu-id="86f81-105">For a complete list of these structures, see <xref:System.Data.OracleClient>.</span></span>  
  
 <span data-ttu-id="86f81-106">Aşağıdaki C# örnekleri:</span><span class="sxs-lookup"><span data-stu-id="86f81-106">The following C# examples:</span></span>  
  
- <span data-ttu-id="86f81-107">Oracle tablosu oluşturun ve ile veri yükleme.</span><span class="sxs-lookup"><span data-stu-id="86f81-107">Create an Oracle table and load it with data.</span></span>  
  
- <span data-ttu-id="86f81-108">Kullanan bir <xref:System.Data.OracleClient.OracleDataReader> verilere erişmek ve birkaç <xref:System.Data.OracleClient.OracleType> verileri görüntülemek için yapılar.</span><span class="sxs-lookup"><span data-stu-id="86f81-108">Use an <xref:System.Data.OracleClient.OracleDataReader> to access the data, and use several <xref:System.Data.OracleClient.OracleType> structures to display the data.</span></span>  
  
## <a name="creating-an-oracle-table"></a><span data-ttu-id="86f81-109">Oracle tablosu oluşturma</span><span class="sxs-lookup"><span data-stu-id="86f81-109">Creating an Oracle Table</span></span>  
 <span data-ttu-id="86f81-110">Bu örnek, bir Oracle tablosu oluşturur ve verileri yükler.</span><span class="sxs-lookup"><span data-stu-id="86f81-110">This example creates an Oracle table and loads it with data.</span></span> <span data-ttu-id="86f81-111">Bu örnek, bir sonraki örneği çalıştırmadan önce çalıştırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="86f81-111">You must run this example before running the next example.</span></span>  
  
```csharp  
public void Setup(string connectionString)  
   {  
   OracleConnection conn = new OracleConnection(connectionString);  
   try  
      {  
      conn.Open();  
      OracleCommand cmd = conn.CreateCommand();  
      cmd.CommandText ="CREATE TABLE OracleTypesTable " +  
        "(MyVarchar2 varchar2(3000),MyNumber number(28,4) " +  
        "PRIMARY KEY ,MyDate date, MyRaw raw(255))";  
      cmd.ExecuteNonQuery();  
      cmd.CommandText ="INSERT INTO OracleTypesTable VALUES " +  
        "( 'test', 2, to_date('2000-01-11 12:54:01','yyyy-mm-dd " +  
        "hh24:mi:ss'), '0001020304' )";  
      cmd.ExecuteNonQuery();  
      }  
   catch(Exception)  
   {  
   }  
   finally  
   {  
      conn.Close();  
   }  
}  
```  
  
## <a name="retrieving-data-from-the-oracle-table"></a><span data-ttu-id="86f81-112">Oracle tablo verilerini alma</span><span class="sxs-lookup"><span data-stu-id="86f81-112">Retrieving Data from the Oracle Table</span></span>  
 <span data-ttu-id="86f81-113">Bu örnekte bir **OracleDataReader** verilere erişmek için birkaç kullanır **OracleType** verileri görüntülemek için yapılar.</span><span class="sxs-lookup"><span data-stu-id="86f81-113">This example uses an **OracleDataReader** to access the data, and uses several **OracleType** structures to display the data.</span></span>  
  
```csharp  
public void ReadOracleTypesExample(string connectionString)  
   {  
   OracleConnection myConnection =   
      new OracleConnection(connectionString);  
   myConnection.Open();  
   OracleCommand myCommand = myConnection.CreateCommand();  
  
   try  
      {  
      myCommand.CommandText = "SELECT * from OracleTypesTable";  
      OracleDataReader oracledatareader1 = myCommand.ExecuteReader();  
      oracledatareader1.Read();  
  
      //Using the oracle specific getters for each type is faster than  
      //using GetOracleValue.  
  
      //First column, MyVarchar2, is a VARCHAR2 data type in Oracle  
      //Server and maps to OracleString.  
      OracleString oraclestring1 =   
        oracledatareader1.GetOracleString(0);  
      Console.WriteLine("OracleString " + oraclestring1.ToString());  
  
      //Second column, MyNumber, is a NUMBER data type in Oracle Server  
      //and maps to OracleNumber.  
      OracleNumber oraclenumber1 =   
        oracledatareader1.GetOracleNumber(1);  
      Console.WriteLine("OracleNumber " + oraclenumber1.ToString());  
  
      //Third column, MyDate, is a DATA data type in Oracle Server  
      //and maps to OracleDateTime.  
      OracleDateTime oracledatetime1 =   
        oracledatareader1.GetOracleDateTime(2);  
      Console.WriteLine("OracleDateTime " + oracledatetime1.ToString());  
  
      //Fourth column, MyRaw, is a RAW data type in Oracle Server and  
      //maps to OracleBinary.  
      OracleBinary oraclebinary1 =   
        oracledatareader1.GetOracleBinary(3);  
      //Calling value on a null OracleBinary throws  
      //OracleNullValueException; therefore, check for a null value.  
      if (oraclebinary1.IsNull==false)  
      {  
         foreach(byte b in oraclebinary1.Value)  
         {  
            Console.WriteLine("byte " + b.ToString());  
         }  
      }  
      oracledatareader1.Close();  
   }  
   catch(Exception e)  
   {  
       Console.WriteLine(e.ToString());  
   }  
   finally  
   {  
       myConnection.Close();  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="86f81-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="86f81-114">See also</span></span>

- [<span data-ttu-id="86f81-115">Oracle ve ADO.NET</span><span class="sxs-lookup"><span data-stu-id="86f81-115">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="86f81-116">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="86f81-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
