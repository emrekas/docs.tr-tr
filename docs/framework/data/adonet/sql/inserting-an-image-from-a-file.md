---
title: Dosyadan Görüntü Ekleme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 35900aa2-5615-4174-8212-ba184c6b82fb
ms.openlocfilehash: d47f5b7eaf6b5f6a3174982e6b4cf43859c031a5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794145"
---
# <a name="inserting-an-image-from-a-file"></a>Dosyadan Görüntü Ekleme
Veri kaynağınızdaki alanın türüne bağlı olarak, bir veritabanına ikili veya karakter verisi olarak bir ikili büyük nesne (BLOB) yazabilirsiniz. BLOB, genellikle belge ve resim içeren `text`, `ntext`, ve `image` veri türlerine başvuran genel bir terimdir.  
  
 Veritabanınıza bir BLOB değeri yazmak için, uygun INSERT veya UPDATE ifadesini verin ve BLOB değerini bir giriş parametresi olarak geçirin (bkz. [parametreleri ve parametre veri türlerini yapılandırma](../configuring-parameters-and-parameter-data-types.md)). Blobu bir SQL Server `text` alanı gibi metin olarak depolanıyorsa, blobu dize parametresi olarak geçirebilirsiniz. BLOB, bir SQL Server `image` alanı gibi ikili biçimde depolanıyorsa, türü `byte` bir diziyi ikili parametre olarak geçirebilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, çalışan bilgilerini Northwind veritabanındaki Çalışanlar tablosuna ekler. Çalışan fotoğrafı bir dosyadan okunmalıdır ve tablodaki fotoğraf alanına eklenir. Bu bir görüntü alanıdır.  
  
```vb  
Public Shared Sub AddEmployee( _  
  lastName As String, _  
  firstName As String, _  
  title As String, _  
  hireDate As DateTime, _  
  reportsTo As Integer, _  
  photoFilePath As String, _  
  connectionString As String)  
  
  Dim photo() as Byte = GetPhoto(photoFilePath)  
  
  Using connection As SqlConnection = New SqlConnection( _  
    connectionString)  
  
  Dim command As SqlCommand = New SqlCommand( _  
    "INSERT INTO Employees (LastName, FirstName, Title, " & _  
    "HireDate, ReportsTo, Photo) " & _  
    "Values(@LastName, @FirstName, @Title, " & _  
    "@HireDate, @ReportsTo, @Photo)", connection)   
  
  command.Parameters.Add("@LastName",  _  
    SqlDbType.NVarChar, 20).Value = lastName  
  command.Parameters.Add("@FirstName", _  
    SqlDbType.NVarChar, 10).Value = firstName  
  command.Parameters.Add("@Title", _  
    SqlDbType.NVarChar, 30).Value = title  
  command.Parameters.Add("@HireDate", _  
    SqlDbType.DateTime).Value = hireDate  
  command.Parameters.Add("@ReportsTo", _  
    SqlDbType.Int).Value = reportsTo  
  
  command.Parameters.Add("@Photo", _  
    SqlDbType.Image, photo.Length).Value = photo  
  
  connection.Open()  
  command.ExecuteNonQuery()  
  
  End Using  
End Sub  
  
Public Shared Function GetPhoto(filePath As String) As Byte()  
  Dim stream As FileStream = new FileStream( _  
     filePath, FileMode.Open, FileAccess.Read)  
  Dim reader As BinaryReader = new BinaryReader(stream)  
  
  Dim photo() As Byte = reader.ReadBytes(stream.Length)  
  
  reader.Close()  
  stream.Close()  
  
  Return photo  
End Function  
```  
  
```csharp  
public static void AddEmployee(  
  string lastName,   
  string firstName,   
  string title,   
  DateTime hireDate,   
  int reportsTo,   
  string photoFilePath,   
  string connectionString)  
{  
  byte[] photo = GetPhoto(photoFilePath);  
  
  using (SqlConnection connection = new SqlConnection(  
    connectionString))  
  
  SqlCommand command = new SqlCommand(  
    "INSERT INTO Employees (LastName, FirstName, " +  
    "Title, HireDate, ReportsTo, Photo) " +  
    "Values(@LastName, @FirstName, @Title, " +  
    "@HireDate, @ReportsTo, @Photo)", connection);   
  
  command.Parameters.Add("@LastName",    
     SqlDbType.NVarChar, 20).Value = lastName;  
  command.Parameters.Add("@FirstName",   
      SqlDbType.NVarChar, 10).Value = firstName;  
  command.Parameters.Add("@Title",       
      SqlDbType.NVarChar, 30).Value = title;  
  command.Parameters.Add("@HireDate",   
       SqlDbType.DateTime).Value = hireDate;  
  command.Parameters.Add("@ReportsTo",   
      SqlDbType.Int).Value = reportsTo;  
  
  command.Parameters.Add("@Photo",  
      SqlDbType.Image, photo.Length).Value = photo;  
  
  connection.Open();  
  command.ExecuteNonQuery();  
  }  
}  
  
public static byte[] GetPhoto(string filePath)  
{  
  FileStream stream = new FileStream(  
      filePath, FileMode.Open, FileAccess.Read);  
  BinaryReader reader = new BinaryReader(stream);  
  
  byte[] photo = reader.ReadBytes((int)stream.Length);  
  
  reader.Close();  
  stream.Close();  
  
  return photo;  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Verileri Değiştirmek için Komutları Kullanma](../using-commands-to-modify-data.md)
- [İkili Verileri Alma](../retrieving-binary-data.md)
- [SQL Server İkili ve Büyük Değerli Veriler](sql-server-binary-and-large-value-data.md)
- [SQL Server Veri Türü Eşlemeleri](../sql-server-data-type-mappings.md)
- [ADO.NET’e Genel Bakış](../ado-net-overview.md)
