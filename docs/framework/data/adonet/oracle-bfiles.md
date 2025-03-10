---
title: Oracle BFILE
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 214140bb8fcf43154b014ea3db609d355a27af7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794632"
---
# <a name="oracle-bfiles"></a>Oracle BFILE
Oracle için .NET Framework veri sağlayıcısı, Oracle <xref:System.Data.OracleClient.OracleBFile> <xref:System.Data.OracleClient.OracleType.BFile> veri türüyle çalışmak için kullanılan sınıfını içerir.  
  
 Oracle **bDosya** veri türü, en fazla 4 gigabayt boyutlu ikili verilere başvuru Içeren bir Oracle **lob** veri türüdür. Oracle **bDosya** , verileri sunucu yerine işletim sistemindeki fiziksel bir dosyada depolanan diğer Oracle **lob** veri türlerinden farklıdır. **BDosya** veri türünün verilere salt okunurdur erişimi sağladığını unutmayın.  
  
 **Bir bu veri türünün** bir **lob** veri türünden ayırt edilmesini sağlayan diğer özellikleri şunlardır:  
  
- Yapılandırılmamış verileri içerir.  
  
- Sunucu tarafı parçalama destekler.  
  
- Başvuru kopyalama semantiğini kullanır. Örneğin, bir **bDosya**üzerinde kopyalama işlemi gerçekleştirirseniz, yalnızca **bDosya** Konumlandırıcı (dosyanın bir başvurusu) kopyalanır. Dosyadaki veriler kopyalanmaz.  
  
 **BDosya** veri türü,, boyutu büyük olan LOBs 'ye başvurmak için kullanılmalıdır ve bu nedenle veritabanında depolanması pratik değildir. **Lob** veri türü ile karşılaştırıldığında bir **bDosya** veri türü kullanılırken daha fazla istemci, sunucu ve iletişim yükü söz konusu olur. Yalnızca az miktarda veri edinmeniz gerekiyorsa, bir **bDosya** 'ya erişmek daha etkilidir. Nesnenin tamamını edinmeniz gerekiyorsa, veritabanına yerleşik lob 'Ları erişmek daha etkilidir.  
  
 NULL olmayan her bir **Oraclebdosya** nesnesi, temel alınan fiziksel dosyanın konumunu tanımlayan iki varlıkla ilişkilendirilir:  
  
1. Dosya sistemindeki bir dizin için veritabanı diğer adı olan Oracle DIZIN nesnesi ve  
  
2. DIZIN nesnesiyle ilişkili dizinde bulunan, temel alınan fiziksel dosyanın dosya adı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki C# örnek, bir Oracle tablosunda bir **bDosya** oluşturma ve bunu bir **oraclebdosya** nesnesi biçiminde alma işlemlerinin nasıl yapılacağını gösterir. Örnek <xref:System.Data.OracleClient.OracleDataReader> , nesnesinin ve **oraclebdosya** **Seek** ve **Read** yöntemlerinin kullanımını gösterir. Bu örneği kullanmak için, önce Oracle sunucusunda "c:\\\bfiles" adlı bir dizin ve "dosyam. jpg" adlı dosyayı oluşturmanız gerektiğini unutmayın.  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =   
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =   
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Oracle ve ADO.NET](oracle-and-adonet.md)
- [ADO.NET’e Genel Bakış](ado-net-overview.md)
