---
title: Bekleme Tanıtıcıları Kullanan ASP.NET Uygulamaları
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f588597a-49de-4206-8463-4ef377e112ff
ms.openlocfilehash: 0a17755af4027238393890545c051a063d607b6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877766"
---
# <a name="aspnet-applications-using-wait-handles"></a><span data-ttu-id="5b15e-102">Bekleme Tanıtıcıları Kullanan ASP.NET Uygulamaları</span><span class="sxs-lookup"><span data-stu-id="5b15e-102">ASP.NET Applications Using Wait Handles</span></span>
<span data-ttu-id="5b15e-103">Uygulamanız bir anda yalnızca bir zaman uyumsuz işlemi işlenirken zaman uyumsuz işlemleri işlemek için yoklama modelleri ve geri çağırma yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="5b15e-103">The callback and polling models for handling asynchronous operations are useful when your application is processing only one asynchronous operation at a time.</span></span> <span data-ttu-id="5b15e-104">Bekleme modeller, birden çok zaman uyumsuz işleme için daha esnek bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="5b15e-104">The Wait models provide a more flexible way of processing multiple asynchronous operations.</span></span> <span data-ttu-id="5b15e-105">Adlı iki bekleme modeli vardır <xref:System.Threading.WaitHandle> bunları uygulamak için kullanılan yöntemleri: bekleme (Any) modeli ve bekleme (Tümü) modeli.</span><span class="sxs-lookup"><span data-stu-id="5b15e-105">There are two Wait models, named for the <xref:System.Threading.WaitHandle> methods used to implement them: the Wait (Any) model and the Wait (All) model.</span></span>  
  
 <span data-ttu-id="5b15e-106">Ya da bekleme modelini kullanmak için kullanmanız gerekir <xref:System.IAsyncResult.AsyncWaitHandle%2A> özelliği <xref:System.IAsyncResult> tarafından döndürülen nesne <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A>, veya <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="5b15e-106">To use either Wait model, you need to use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> object returned by the <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A>, or <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A> methods.</span></span> <span data-ttu-id="5b15e-107"><xref:System.Threading.WaitHandle.WaitAny%2A> Ve <xref:System.Threading.WaitHandle.WaitAll%2A> yöntemleri göndermenizi gerektiren <xref:System.Threading.WaitHandle> nesneler bir bağımsız değişken olarak birlikte gruplandırılmış bir dizi.</span><span class="sxs-lookup"><span data-stu-id="5b15e-107">The <xref:System.Threading.WaitHandle.WaitAny%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> methods both require you to send the <xref:System.Threading.WaitHandle> objects as an argument, grouped together in an array.</span></span>  
  
 <span data-ttu-id="5b15e-108">Her iki bekleme yöntemi zaman uyumsuz işlemlerin tamamlanması bekleniyor izleyin.</span><span class="sxs-lookup"><span data-stu-id="5b15e-108">Both Wait methods monitor the asynchronous operations, waiting for completion.</span></span> <span data-ttu-id="5b15e-109"><xref:System.Threading.WaitHandle.WaitAny%2A> Yöntemi herhangi bir işlemlerinin tamamlanması veya zaman aşımı için bekler. Belirli bir işlem tamamlandığında, öğrendikten sonra sonuçları işleyebilir ve ardından sonraki işlemin tamamlanması veya zaman aşımı için beklemeye devam. <xref:System.Threading.WaitHandle.WaitAll%2A> Yöntemi bekler tüm işlemlerin dizisindeki <xref:System.Threading.WaitHandle> örnekleri tamamlanması veya devam etmeden önce zaman aşımı.</span><span class="sxs-lookup"><span data-stu-id="5b15e-109">The <xref:System.Threading.WaitHandle.WaitAny%2A> method waits for any of the operations to complete or time out. Once you know a particular operation is complete, you can process its results and then continue waiting for the next operation to complete or time out. The <xref:System.Threading.WaitHandle.WaitAll%2A> method waits for all of the processes in the array of <xref:System.Threading.WaitHandle> instances to complete or time out before continuing.</span></span>  
  
 <span data-ttu-id="5b15e-110">Bekleme modelleri çoğu çarpıcı, farklı sunucularda bazı uzunlukta birden çok işlemi çalıştırmak ihtiyacınız olduğunda ya da aynı anda tüm sorguları işlemek için güçlü sunucunuzdur avantajdır.</span><span class="sxs-lookup"><span data-stu-id="5b15e-110">The Wait models' benefit is most striking when you need to run multiple operations of some length on different servers, or when your server is powerful enough to process all the queries at the same time.</span></span> <span data-ttu-id="5b15e-111">Burada verilen örneklerde, üç sorgu değişimlerle SELECT sorgusu için değişen uzunluktaki WAITFOR komutlar ekleyerek uzun işlemler taklit.</span><span class="sxs-lookup"><span data-stu-id="5b15e-111">In the examples presented here, three queries emulate long processes by adding WAITFOR commands of varying lengths to inconsequential SELECT queries.</span></span>  
  
## <a name="example-wait-any-model"></a><span data-ttu-id="5b15e-112">Örnek: Bekleme (herhangi) modeli</span><span class="sxs-lookup"><span data-stu-id="5b15e-112">Example: Wait (Any) Model</span></span>  
 <span data-ttu-id="5b15e-113">Aşağıdaki örnek, bekleme (herhangi) modelini gösterir.</span><span class="sxs-lookup"><span data-stu-id="5b15e-113">The following example illustrates the Wait (Any) model.</span></span> <span data-ttu-id="5b15e-114">Üç zaman uyumsuz işlem başladıktan sonra <xref:System.Threading.WaitHandle.WaitAny%2A> herhangi biri tamamlanması için beklenecek yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="5b15e-114">Once three asynchronous processes are started, the <xref:System.Threading.WaitHandle.WaitAny%2A> method is called to wait for the completion of any one of them.</span></span> <span data-ttu-id="5b15e-115">Her işlem tamamlandığında <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A> yöntemi çağrılır ve ortaya çıkan <xref:System.Data.SqlClient.SqlDataReader> nesne okunur.</span><span class="sxs-lookup"><span data-stu-id="5b15e-115">As each process completes, the <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A> method is called and the resulting <xref:System.Data.SqlClient.SqlDataReader> object is read.</span></span> <span data-ttu-id="5b15e-116">Bu noktada, gerçek yaşam uygulaması büyük olasılıkla kullanacağınız <xref:System.Data.SqlClient.SqlDataReader> sayfasının bir bölümü doldurmak için.</span><span class="sxs-lookup"><span data-stu-id="5b15e-116">At this point, a real-world application would likely use the <xref:System.Data.SqlClient.SqlDataReader> to populate a portion of the page.</span></span> <span data-ttu-id="5b15e-117">Bu basit örnekte işleminin tamamlanmasını zaman işleme karşılık gelen bir metin kutusuna eklenir.</span><span class="sxs-lookup"><span data-stu-id="5b15e-117">In this simple example, the time the process completed is added to a text box corresponding to the process.</span></span> <span data-ttu-id="5b15e-118">Birlikte ele alındığında noktası metin kutularına zamanları gösterilmiştir: Kod, bir işlemin tamamlanmasını her zaman yürütülür.</span><span class="sxs-lookup"><span data-stu-id="5b15e-118">Taken together, the times in the text boxes illustrate the point: Code is executed each time a process completes.</span></span>  
  
 <span data-ttu-id="5b15e-119">Bu örnekte ayarlamak için yeni bir ASP.NET Web sitesi projesi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="5b15e-119">To set up this example, create a new ASP.NET Web Site project.</span></span> <span data-ttu-id="5b15e-120">Bir yerde bir <xref:System.Web.UI.WebControls.Button> denetimi ve dört <xref:System.Web.UI.WebControls.TextBox> (her denetim için varsayılan adı kabul etme) sayfadaki denetimleri.</span><span class="sxs-lookup"><span data-stu-id="5b15e-120">Place a <xref:System.Web.UI.WebControls.Button> control and four <xref:System.Web.UI.WebControls.TextBox> controls on the page (accepting the default name for each control).</span></span>  
  
 <span data-ttu-id="5b15e-121">Ortamınız için gerektiği gibi bağlantı dizesini değiştirerek formun sınıfına aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="5b15e-121">Add the following code to the form's class, modifying the connection string as necessary for your environment.</span></span>  
  
```vb  
' Add these to the top of the class  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Threading  
  
' Add this code to the page's class:  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,              
        ' you can retrieve it from a configuration file.   
  
        ' If you have not included "Asynchronous Processing=true"   
        ' in the connection string, the command will not be able  
        ' to execute asynchronously.  
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks;" & _  
          "Asynchronous Processing=true"  
    End Function    
  
    Sub Button1_Click( _  
     ByVal sender As Object, ByVal e As System.EventArgs)  
  
        ' In a real-world application, you might be connecting to   
        '  three different servers or databases. For the example,  
        '  we connect to only one.  
        Dim connection1 As New SqlConnection(GetConnectionString())  
        Dim connection2 As New SqlConnection(GetConnectionString())  
        Dim connection3 As New SqlConnection(GetConnectionString())  
  
        ' To keep the example simple, all three asynchronous   
        ' processes select a row from the same table. WAITFOR  
        ' commands are used to emulate long-running processes  
        ' that complete after different periods of time.  
        Dim commandText1 As String = _  
            "WAITFOR DELAY '0:0:01';" & _  
            "SELECT * FROM Production.Product " & _  
            "WHERE ProductNumber = 'BL-2036'"  
  
        Dim commandText2 As String = _  
            "WAITFOR DELAY '0:0:05';" & _  
            "SELECT * FROM Production.Product " & _  
            "WHERE ProductNumber = 'BL-2036'"  
  
        Dim commandText3 As String = _  
            "WAITFOR DELAY '0:0:10';" & _  
            "SELECT * FROM Production.Product " & _  
            "WHERE ProductNumber = 'BL-2036'"  
  
        Dim waitHandles(2) As WaitHandle  
        Try  
            ' For each process, open a connection and begin execution.  
            ' Use the IAsyncResult object returned by   
            ' BeginExecuteReader to add a WaitHandle for the process  
            ' to the array.  
            connection1.Open()  
            Dim command1 As New SqlCommand(commandText1, connection1)  
            Dim result1 As IAsyncResult = _  
             command1.BeginExecuteReader()  
            waitHandles(0) = result1.AsyncWaitHandle  
  
            connection2.Open()  
            Dim command2 As New SqlCommand(commandText2, connection2)  
            Dim result2 As IAsyncResult = _  
             command2.BeginExecuteReader()  
            waitHandles(1) = result2.AsyncWaitHandle  
  
            connection3.Open()  
            Dim command3 As New SqlCommand(commandText3, connection3)  
            Dim result3 As IAsyncResult = _  
             command3.BeginExecuteReader()  
            waitHandles(2) = result3.AsyncWaitHandle  
  
            Dim index As Integer  
            For countWaits As Integer = 1 To 3  
                ' WaitAny waits for any of the processes to complete.  
                ' The return value is either the index of the  
                ' array element whose process just completed, or  
                ' the WaitTimeout value.  
                index = WaitHandle.WaitAny(waitHandles, 60000, False)  
                ' This example doesn't actually do anything with the   
                ' data returned by the processes, but the code opens   
                ' readers for each just to demonstrate the concept.  
                ' Instead of using the returned data to fill the   
                ' controls on the page, the example adds the time  
                ' the process was completed to the corresponding  
                ' text box.  
                Select Case index  
                    Case 0  
                        Dim reader1 As SqlDataReader  
                        reader1 = command1.EndExecuteReader(result1)  
                        If reader1.Read Then  
                            TextBox1.Text = _  
                             "Completed " & _  
                             System.DateTime.Now.ToLongTimeString()  
                        End If  
                        reader1.Close()  
  
                    Case 1  
                        Dim reader2 As SqlDataReader  
                        reader2 = command2.EndExecuteReader(result2)  
                        If reader2.Read Then  
                            TextBox2.Text = _  
                             "Completed " & _  
                             System.DateTime.Now.ToLongTimeString()  
                        End If  
                        reader2.Close()  
                    Case 2  
                        Dim reader3 As SqlDataReader  
                        reader3 = command3.EndExecuteReader(result3)  
                        If reader3.Read Then  
                            TextBox3.Text = _  
                             "Completed " & _  
                             System.DateTime.Now.ToLongTimeString()  
                        End If  
                        reader3.Close()  
                    Case WaitHandle.WaitTimeout  
                        Throw New Exception("Timeout")  
                End Select  
  
            Next  
        Catch ex As Exception  
            TextBox4.Text = ex.ToString  
        End Try  
        connection1.Close()  
        connection2.Close()  
        connection3.Close()  
  
    End Sub  
```  
  
```csharp  
// Add the following using statements, if they are not already there.  
using System;  
using System.Data;  
using System.Configuration;  
using System.Web;  
using System.Web.Security;  
using System.Web.UI;  
using System.Web.UI.WebControls;  
using System.Web.UI.WebControls.WebParts;  
using System.Web.UI.HtmlControls;  
using System.Threading;  
using System.Data.SqlClient;  
  
// Add this code to the page's class  
string GetConnectionString()  
     //  To avoid storing the connection string in your code,              
     //  you can retrieve it from a configuration file.   
     //  If you have not included "Asynchronous Processing=true"   
     //  in the connection string, the command will not be able  
     //  to execute asynchronously.  
{  
     return "Data Source=(local);Integrated Security=SSPI;" +  
          "Initial Catalog=AdventureWorks;" +  
          "Asynchronous Processing=true";  
}  
void Button1_Click(object sender, System.EventArgs e)  
{  
     //  In a real-world application, you might be connecting to   
     //   three different servers or databases. For the example,  
     //   we connect to only one.  
  
     SqlConnection connection1 =   
          new SqlConnection(GetConnectionString());  
     SqlConnection connection2 =   
          new SqlConnection(GetConnectionString());  
     SqlConnection connection3 =   
          new SqlConnection(GetConnectionString());  
     //  To keep the example simple, all three asynchronous   
     //  processes select a row from the same table. WAITFOR  
     //  commands are used to emulate long-running processes  
     //  that complete after different periods of time.  
  
     string commandText1 = "WAITFOR DELAY '0:0:01';" +   
          "SELECT * FROM Production.Product " +   
          "WHERE ProductNumber = 'BL-2036'";  
     string commandText2 = "WAITFOR DELAY '0:0:05';" +   
          "SELECT * FROM Production.Product " +   
          "WHERE ProductNumber = 'BL-2036'";  
     string commandText3 = "WAITFOR DELAY '0:0:10';" +   
          "SELECT * FROM Production.Product " +   
          "WHERE ProductNumber = 'BL-2036'";  
     try  
          //  For each process, open a connection and begin   
          //  execution. Use the IAsyncResult object returned by   
          //  BeginExecuteReader to add a WaitHandle for the   
          //  process to the array.  
     {  
          connection1.Open();  
          SqlCommand command1 =  
               new SqlCommand(commandText1, connection1);  
          IAsyncResult result1 = command1.BeginExecuteReader();  
          WaitHandle waitHandle1 = result1.AsyncWaitHandle;  
  
          connection2.Open();  
          SqlCommand command2 =  
               new SqlCommand(commandText2, connection2);  
          IAsyncResult result2 = command2.BeginExecuteReader();  
          WaitHandle waitHandle2 = result2.AsyncWaitHandle;  
  
          connection3.Open();  
          SqlCommand command3 =  
               new SqlCommand(commandText3, connection3);  
          IAsyncResult result3 = command3.BeginExecuteReader();  
          WaitHandle waitHandle3 = result3.AsyncWaitHandle;  
  
          WaitHandle[] waitHandles = {  
               waitHandle1, waitHandle2, waitHandle3  
          };  
  
          int index;  
          for (int countWaits = 0; countWaits <= 2; countWaits++)  
          {  
               //  WaitAny waits for any of the processes to   
               //  complete. The return value is either the index   
               //  of the array element whose process just   
               //  completed, or the WaitTimeout value.  
  
               index = WaitHandle.WaitAny(waitHandles,   
                    60000, false);  
               //  This example doesn't actually do anything with   
               //  the data returned by the processes, but the   
               //  code opens readers for each just to demonstrate       
               //  the concept.  
               //  Instead of using the returned data to fill the   
               //  controls on the page, the example adds the time  
               //  the process was completed to the corresponding  
               //  text box.  
  
               switch (index)  
               {  
                    case 0:  
                         SqlDataReader reader1;  
                         reader1 =   
                              command1.EndExecuteReader(result1);  
                         if (reader1.Read())  
                         {  
                           TextBox1.Text =   
                           "Completed " +  
                           System.DateTime.Now.ToLongTimeString();  
                         }  
                         reader1.Close();  
                         break;  
                    case 1:  
                         SqlDataReader reader2;  
                         reader2 =   
                              command2.EndExecuteReader(result2);  
                         if (reader2.Read())  
                         {  
                           TextBox2.Text =   
                           "Completed " +  
                           System.DateTime.Now.ToLongTimeString();  
                         }  
                         reader2.Close();  
                         break;  
                    case 2:  
                         SqlDataReader reader3;  
                         reader3 =   
                              command3.EndExecuteReader(result3);  
                         if (reader3.Read())  
                         {  
                           TextBox3.Text =   
                           "Completed " +  
                           System.DateTime.Now.ToLongTimeString();  
                         }  
                         reader3.Close();  
                         break;  
                    case WaitHandle.WaitTimeout:  
                         throw new Exception("Timeout");  
                         break;  
               }  
          }  
     }  
     catch (Exception ex)  
     {  
          TextBox4.Text = ex.ToString();  
     }  
     connection1.Close();  
     connection2.Close();  
     connection3.Close();  
}  
```  
  
## <a name="example-wait-all-model"></a><span data-ttu-id="5b15e-122">Örnek: Bekleme (Tümü) modeli</span><span class="sxs-lookup"><span data-stu-id="5b15e-122">Example: Wait (All) Model</span></span>  
 <span data-ttu-id="5b15e-123">Aşağıdaki örnekte, bekleme (Tümü) modeli gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="5b15e-123">The following example illustrates the Wait (All) model.</span></span> <span data-ttu-id="5b15e-124">Üç zaman uyumsuz işlem başladıktan sonra <xref:System.Threading.WaitHandle.WaitAll%2A> işlemlerin tamamlanmasını bekleyin veya zaman aşımı yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="5b15e-124">Once three asynchronous processes are started, the <xref:System.Threading.WaitHandle.WaitAll%2A> method is called to wait for the processes to complete or time out.</span></span>  
  
 <span data-ttu-id="5b15e-125">(Any) modeli bekleme örneği gibi işleminin tamamlanmasını zaman işleme karşılık gelen bir metin kutusuna eklenir.</span><span class="sxs-lookup"><span data-stu-id="5b15e-125">Like the example of the Wait (Any) model, the time the process completed is added to a text box corresponding to the process.</span></span> <span data-ttu-id="5b15e-126">Tekrar metin kutularına zamanları noktası göstermektedir: Kod aşağıdaki <xref:System.Threading.WaitHandle.WaitAny%2A> yöntemi yalnızca tüm işlemler tamamlandıktan sonra yürütülür.</span><span class="sxs-lookup"><span data-stu-id="5b15e-126">Again, the times in the text boxes illustrate the point: Code following the <xref:System.Threading.WaitHandle.WaitAny%2A> method is executed only after all processes are complete.</span></span>  
  
 <span data-ttu-id="5b15e-127">Bu örnekte ayarlamak için yeni bir ASP.NET Web sitesi projesi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="5b15e-127">To set up this example, create a new ASP.NET Web Site project.</span></span> <span data-ttu-id="5b15e-128">Bir yerde bir <xref:System.Web.UI.WebControls.Button> denetimi ve dört <xref:System.Web.UI.WebControls.TextBox> (her denetim için varsayılan adı kabul etme) sayfadaki denetimleri.</span><span class="sxs-lookup"><span data-stu-id="5b15e-128">Place a <xref:System.Web.UI.WebControls.Button> control and four <xref:System.Web.UI.WebControls.TextBox> controls on the page (accepting the default name for each control).</span></span>  
  
 <span data-ttu-id="5b15e-129">Ortamınız için gerektiği gibi bağlantı dizesini değiştirerek formun sınıfına aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="5b15e-129">Add the following code to the form's class, modifying the connection string as necessary for your environment.</span></span>  
  
```vb  
' Add these to the top of the class  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Threading  
  
' Add this code to the page's class:  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,              
        ' you can retrieve it from a configuration file.   
  
        ' If you have not included "Asynchronous Processing=true"   
        ' in the connection string, the command will not be able  
        ' to execute asynchronously.  
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks;" & _  
          "Asynchronous Processing=true"  
    End Function    
    Sub Button1_Click( _  
     ByVal sender As Object, ByVal e As System.EventArgs)  
  
        ' In a real-world application, you might be connecting to   
        '  three different servers or databases. For the example,  
        '  we connect to only one.  
        Dim connection1 As New SqlConnection(GetConnectionString())  
        Dim connection2 As New SqlConnection(GetConnectionString())  
        Dim connection3 As New SqlConnection(GetConnectionString())  
  
        ' To keep the example simple, all three asynchronous   
        ' processes select a row from the same table. WAITFOR  
        ' commands are used to emulate long-running processes  
        ' that complete after different periods of time.  
        Dim commandText1 As String = _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint + 1 " & _  
         "WHERE ReorderPoint Is Not Null;" & _  
         "WAITFOR DELAY '0:0:01';" & _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint - 1 " & _  
         "WHERE ReorderPoint Is Not Null"  
  
        Dim commandText2 As String = _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint + 1 " & _  
         "WHERE ReorderPoint Is Not Null;" & _  
         "WAITFOR DELAY '0:0:05';" & _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint - 1 " & _  
         "WHERE ReorderPoint Is Not Null"  
  
        Dim commandText3 As String = _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint + 1 " & _  
         "WHERE ReorderPoint Is Not Null;" & _  
         "WAITFOR DELAY '0:0:10';" & _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint - 1 " & _  
         "WHERE ReorderPoint Is Not Null"  
  
        Dim waitHandles(2) As WaitHandle  
  
        Try  
            ' For each process, open a connection and begin execution.  
            ' Use the IAsyncResult object returned by   
            ' BeginExecuteReader to add a WaitHandle for the process  
            ' to the array.  
            connection1.Open()  
            Dim command1 As New SqlCommand(commandText1, connection1)  
            Dim result1 As IAsyncResult = _  
             command1.BeginExecuteNonQuery()  
            waitHandles(0) = result1.AsyncWaitHandle  
  
            connection2.Open()  
            Dim command2 As New SqlCommand(commandText2, connection2)  
            Dim result2 As IAsyncResult = _  
             command2.BeginExecuteNonQuery()  
            waitHandles(1) = result2.AsyncWaitHandle  
  
            connection3.Open()  
            Dim command3 As New SqlCommand(commandText3, connection3)  
            Dim result3 As IAsyncResult = _  
             command3.BeginExecuteNonQuery()  
            waitHandles(2) = result3.AsyncWaitHandle  
  
            ' WaitAll waits for all of the processes to complete.  
            ' The return value is True if all processes completed,   
            ' False if any process timed out.  
            Dim result As Boolean = _  
             WaitHandle.WaitAll(waitHandles, 60000, False)  
            If result Then  
                Dim rowCount1 As Long = _  
                 command1.EndExecuteNonQuery(result1)  
                TextBox1.Text = _  
                 "Completed " & _  
                 System.DateTime.Now.ToLongTimeString()  
  
                Dim rowCount2 As Long = _  
                 command2.EndExecuteNonQuery(result2)  
                TextBox2.Text = _  
                 "Completed " & _  
                 System.DateTime.Now.ToLongTimeString()  
  
                Dim rowCount3 As Long = _  
                 command3.EndExecuteNonQuery(result3)  
                TextBox3.Text = _  
                 "Completed " & _  
                 System.DateTime.Now.ToLongTimeString()  
            Else  
                Throw New Exception("Timeout")  
            End If  
        Catch ex As Exception  
            TextBox4.Text = ex.ToString  
        End Try  
        connection1.Close()  
        connection2.Close()  
        connection3.Close()  
  
    End Sub  
```  
  
```csharp  
// Add the following using statements, if they are not already there.  
using System;  
using System.Data;  
using System.Configuration;  
using System.Web;  
using System.Web.Security;  
using System.Web.UI;  
using System.Web.UI.WebControls;  
using System.Web.UI.WebControls.WebParts;  
using System.Web.UI.HtmlControls;  
using System.Threading;  
using System.Data.SqlClient;  
  
// Add this code to the page's class  
string GetConnectionString()  
    //  To avoid storing the connection string in your code,              
    //  you can retrieve it from a configuration file.   
    //  If you have not included "Asynchronous Processing=true"   
    //  in the connection string, the command will not be able  
    //  to execute asynchronously.  
{  
    return "Data Source=(local);Integrated Security=SSPI;" +  
        "Initial Catalog=AdventureWorks;" +  
        "Asynchronous Processing=true";  
}  
void Button1_Click(object sender, System.EventArgs e)  
{  
    //  In a real-world application, you might be connecting to   
    //   three different servers or databases. For the example,  
    //   we connect to only one.  
  
    SqlConnection connection1 =   
        new SqlConnection(GetConnectionString());  
    SqlConnection connection2 =   
        new SqlConnection(GetConnectionString());  
    SqlConnection connection3 =   
        new SqlConnection(GetConnectionString());  
    //  To keep the example simple, all three asynchronous   
    //  processes execute UPDATE queries that result in  
      //  no change to the data. WAITFOR  
    //  commands are used to emulate long-running processes  
    //  that complete after different periods of time.  
  
    string commandText1 =   
        "UPDATE Production.Product " +  
        "SET ReorderPoint = ReorderPoint + 1 " +  
        "WHERE ReorderPoint Is Not Null;" +  
        "WAITFOR DELAY '0:0:01';" +  
        "UPDATE Production.Product " +  
        "SET ReorderPoint = ReorderPoint - 1 " +  
        "WHERE ReorderPoint Is Not Null";  
  
    string commandText2 =   
      "UPDATE Production.Product " +  
      "SET ReorderPoint = ReorderPoint + 1 " +  
      "WHERE ReorderPoint Is Not Null;" +  
      "WAITFOR DELAY '0:0:05';" +  
      "UPDATE Production.Product " +  
      "SET ReorderPoint = ReorderPoint - 1 " +  
      "WHERE ReorderPoint Is Not Null";  
  
    string commandText3 =  
       "UPDATE Production.Product " +  
       "SET ReorderPoint = ReorderPoint + 1 " +  
       "WHERE ReorderPoint Is Not Null;" +  
       "WAITFOR DELAY '0:0:10';" +  
       "UPDATE Production.Product " +  
       "SET ReorderPoint = ReorderPoint - 1 " +  
       "WHERE ReorderPoint Is Not Null";  
    try  
        //  For each process, open a connection and begin   
        //  execution. Use the IAsyncResult object returned by   
        //  BeginExecuteReader to add a WaitHandle for the   
        //  process to the array.  
    {  
        connection1.Open();  
        SqlCommand command1 =  
            new SqlCommand(commandText1, connection1);  
        IAsyncResult result1 = command1.BeginExecuteNonQuery();  
        WaitHandle waitHandle1 = result1.AsyncWaitHandle;  
        connection2.Open();  
  
        SqlCommand command2 =  
            new SqlCommand(commandText2, connection2);  
        IAsyncResult result2 = command2.BeginExecuteNonQuery();  
        WaitHandle waitHandle2 = result2.AsyncWaitHandle;  
        connection3.Open();  
  
        SqlCommand command3 =  
            new SqlCommand(commandText3, connection3);  
        IAsyncResult result3 = command3.BeginExecuteNonQuery();  
        WaitHandle waitHandle3 = result3.AsyncWaitHandle;  
  
        WaitHandle[] waitHandles = {  
            waitHandle1, waitHandle2, waitHandle3  
        };  
  
        bool result;  
        //  WaitAll waits for all of the processes to   
        //  complete. The return value is True if the processes  
        //  all completed successfully, False if any process  
        //  timed out.  
  
        result = WaitHandle.WaitAll(waitHandles, 60000, false);  
        if(result)  
        {  
            long rowCount1 =   
                command1.EndExecuteNonQuery(result1);  
            TextBox1.Text = "Completed " +  
                System.DateTime.Now.ToLongTimeString();  
            long rowCount2 =   
                command2.EndExecuteNonQuery(result2);  
            TextBox2.Text = "Completed " +  
                System.DateTime.Now.ToLongTimeString();  
  
            long rowCount3 =   
                command3.EndExecuteNonQuery(result3);  
            TextBox3.Text = "Completed " +  
                System.DateTime.Now.ToLongTimeString();  
        }  
        else  
        {  
            throw new Exception("Timeout");  
        }  
    }  
  
    catch (Exception ex)  
    {  
        TextBox4.Text = ex.ToString();  
    }  
    connection1.Close();  
    connection2.Close();  
    connection3.Close();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b15e-130">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5b15e-130">See also</span></span>

- [<span data-ttu-id="5b15e-131">Zaman Uyumsuz İşlemler</span><span class="sxs-lookup"><span data-stu-id="5b15e-131">Asynchronous Operations</span></span>](../../../../../docs/framework/data/adonet/sql/asynchronous-operations.md)
- [<span data-ttu-id="5b15e-132">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="5b15e-132">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
