---
title: OracleDataReader Kullanarak Birden Çok REF CURSOR’dan Veri Alma
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 361e9bd4-447d-44b7-8629-3c11f1a7ffbb
ms.openlocfilehash: c4c373fb406292400d8f1cc50123efbcd2960f21
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782819"
---
# <a name="retrieving-data-from-multiple-ref-cursors-using-an-oracledatareader"></a>OracleDataReader Kullanarak Birden Çok REF CURSOR’dan Veri Alma
Bu Microsoft Visual Basic örneği, iki REF CURSOR parametresi döndüren bir PL/SQL saklı yordamı yürütür ve kullanarak <xref:System.Data.OracleClient.OracleDataReader>değerleri okur.  
  
```vb  
Private Sub Button1_Click( _  
  ByVal sender As Object, ByVal e As System.EventArgs)  _  
  Handles Button1.Click  
  
  Dim connString As New String( _  
      "Data Source=Oracle9i;User ID=scott;Password=tiger;")  
  Using conn As New OracleConnection(connString)  
    Dim cmd As New OracleCommand()  
    Dim rdr As OracleDataReader  
  
    conn.Open()  
    cmd.Connection = conn  
    cmd.CommandText = "CURSPKG.OPEN_TWO_CURSORS"  
    cmd.CommandType = CommandType.StoredProcedure  
    cmd.Parameters.Add(New OracleParameter( _  
      "EMPCURSOR", OracleType.Cursor)).Direction = _  
      ParameterDirection.Output  
    cmd.Parameters.Add(New OracleParameter(_  
      "DEPTCURSOR", OracleType.Cursor)).Direction = _  
      ParameterDirection.Output  
  
    rdr = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
    While (rdr.Read())  
        REM do something with the values from the EMP table   
    End While  
  
    rdr.NextResult()  
    While (rdr.Read())  
        REM do something with the values from the DEPT table   
    End While  
    rdr.Close()  
  End Using  
End Sub   
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Oracle REF CURSOR](oracle-ref-cursors.md)
- [ADO.NET’e Genel Bakış](ado-net-overview.md)
