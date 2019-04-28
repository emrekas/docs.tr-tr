---
title: Zaman Uyumsuz İstekler Yapma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, asynchronous access
- Networking
- asynchronous requests, Internet resources
- Network Resources
- WebRequest class, asynchronous access
ms.assetid: 735d3fce-f80c-437f-b02c-5c47f5739674
ms.openlocfilehash: b812db3259cbd2313cdf172950f51ab34679b460
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61642197"
---
# <a name="making-asynchronous-requests"></a><span data-ttu-id="9c051-102">Zaman Uyumsuz İstekler Yapma</span><span class="sxs-lookup"><span data-stu-id="9c051-102">Making Asynchronous Requests</span></span>
<span data-ttu-id="9c051-103"><xref:System.Net> Sınıfları, zaman uyumsuz Internet kaynaklarına erişim için .NET Framework'ün standart zaman uyumsuz programlama modeli kullanın.</span><span class="sxs-lookup"><span data-stu-id="9c051-103">The <xref:System.Net> classes use the .NET Framework's standard asynchronous programming model for asynchronous access to Internet resources.</span></span> <span data-ttu-id="9c051-104"><xref:System.Net.WebRequest.BeginGetResponse%2A> Ve <xref:System.Net.WebRequest.EndGetResponse%2A> yöntemlerinin <xref:System.Net.WebRequest> başlangıç ve tüm zaman uyumsuz istekler için bir Internet kaynağına sınıfı.</span><span class="sxs-lookup"><span data-stu-id="9c051-104">The <xref:System.Net.WebRequest.BeginGetResponse%2A> and <xref:System.Net.WebRequest.EndGetResponse%2A> methods of the <xref:System.Net.WebRequest> class start and complete asynchronous requests for an Internet resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c051-105">Zaman uyumsuz geri çağırma yöntemleri ciddi performans yaptırımlarla sonuçlanabilir, zaman uyumlu kullanarak çağırır.</span><span class="sxs-lookup"><span data-stu-id="9c051-105">Using synchronous calls in asynchronous callback methods can result in severe performance penalties.</span></span> <span data-ttu-id="9c051-106">Internet isteklerini yapılan **WebRequest** ve alt öğelerini kullanmalıdır <xref:System.IO.Stream.BeginRead%2A?displayProperty=nameWithType> tarafından döndürülen akışını okumak için <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="9c051-106">Internet requests made with **WebRequest** and its descendants must use <xref:System.IO.Stream.BeginRead%2A?displayProperty=nameWithType> to read the stream returned by the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="9c051-107">Aşağıdaki örnek kod ile zaman uyumsuz çağrıları nasıl yapılacağı açıklanır **WebRequest** sınıfı.</span><span class="sxs-lookup"><span data-stu-id="9c051-107">The following sample code demonstrates how to use asynchronous calls with the **WebRequest** class.</span></span> <span data-ttu-id="9c051-108">Komut satırından bir URI alır, kaynağın urı'sindeki ister ve ardından Internet'ten alınan verileri konsola yazdırır. bir konsol programı örnektir.</span><span class="sxs-lookup"><span data-stu-id="9c051-108">The sample is a console program that takes a URI from the command line, requests the resource at the URI, and then prints data to the console as it is received from the Internet.</span></span>  
  
 <span data-ttu-id="9c051-109">Program, kendi kullanımı için iki sınıf tanımlar **RequestState** verileri zaman uyumsuz çağrıları arasında geçen, sınıf ve **ClientGetAsync** için zaman uyumsuz istek uygulayan bir sınıf bir Internet kaynağıyla.</span><span class="sxs-lookup"><span data-stu-id="9c051-109">The program defines two classes for its own use, the **RequestState** class, which passes data across asynchronous calls, and the **ClientGetAsync** class, which implements the asynchronous request to an Internet resource.</span></span>  
  
 <span data-ttu-id="9c051-110">**RequestState** sınıfı, hizmet isteğini zaman uyumsuz yöntemleri çağrılar üzerinden isteğin durumu korur.</span><span class="sxs-lookup"><span data-stu-id="9c051-110">The **RequestState** class preserves the state of the request across calls to the asynchronous methods that service the request.</span></span> <span data-ttu-id="9c051-111">İçerdiği **WebRequest** ve <xref:System.IO.Stream> geçerli istek için kaynak ve yanıt, şu anda Internet kaynağının ve bir alınanverileriçerenbirarabelleğealınanakışaiçerenörnekler<xref:System.Text.StringBuilder> , tam yanıtı içerir.</span><span class="sxs-lookup"><span data-stu-id="9c051-111">It contains **WebRequest** and <xref:System.IO.Stream> instances that contain the current request to the resource and the stream received in response, a buffer that contains the data currently received from the Internet resource, and a <xref:System.Text.StringBuilder> that contains the complete response.</span></span> <span data-ttu-id="9c051-112">A **RequestState** olarak geçirilen *durumu* parametre olduğunda <xref:System.AsyncCallback> yöntemi ile kayıtlı **WebRequest.BeginGetResponse**.</span><span class="sxs-lookup"><span data-stu-id="9c051-112">A **RequestState** is passed as the *state* parameter when the <xref:System.AsyncCallback> method is registered with **WebRequest.BeginGetResponse**.</span></span>  
  
 <span data-ttu-id="9c051-113">**ClientGetAsync** sınıfı zaman uyumsuz isteği bir Internet kaynağına uygular ve sonuçta elde edilen yanıtı konsola yazar.</span><span class="sxs-lookup"><span data-stu-id="9c051-113">The **ClientGetAsync** class implements an asynchronous request to an Internet resource and writes the resulting response to the console.</span></span> <span data-ttu-id="9c051-114">Bunu, aşağıdaki listede açıklanan özellikler ve yöntemler içerir.</span><span class="sxs-lookup"><span data-stu-id="9c051-114">It contains the methods and properties described in the following list.</span></span>  
  
- <span data-ttu-id="9c051-115">`allDone` Özelliği içeren bir örneğini <xref:System.Threading.ManualResetEvent> isteğin tamamlandığını bildiren bir sınıf.</span><span class="sxs-lookup"><span data-stu-id="9c051-115">The `allDone` property contains an instance of the <xref:System.Threading.ManualResetEvent> class that signals the completion of the request.</span></span>  
  
- <span data-ttu-id="9c051-116">`Main()` Yöntemi komut satırını okur ve istek için belirtilen Internet kaynağıyla başlar.</span><span class="sxs-lookup"><span data-stu-id="9c051-116">The `Main()` method reads the command line and begins the request for the specified Internet resource.</span></span> <span data-ttu-id="9c051-117">Oluşturur **WebRequest** `wreq` ve **RequestState** `rs`, çağrıları **BeginGetResponse** isteği ve ardından aramaları işlemesi için `allDone.WaitOne()`yöntemi böylece geri çağırma işlemi tamamlanana kadar uygulamadan çıkın değil.</span><span class="sxs-lookup"><span data-stu-id="9c051-117">It creates the **WebRequest** `wreq` and the **RequestState** `rs`, calls **BeginGetResponse** to begin processing the request, and then calls the `allDone.WaitOne()`method so that the application will not exit until the callback is complete.</span></span> <span data-ttu-id="9c051-118">Yanıt, Internet kaynaktan okuduktan sonra `Main()` konsolu ve uygulama sona erer için yazar.</span><span class="sxs-lookup"><span data-stu-id="9c051-118">After the response is read from the Internet resource, `Main()` writes it to the console and the application ends.</span></span>  
  
- <span data-ttu-id="9c051-119">`showusage()` Yöntemi konsolda bir örnek komut satırı yazar.</span><span class="sxs-lookup"><span data-stu-id="9c051-119">The `showusage()` method writes an example command line on the console.</span></span> <span data-ttu-id="9c051-120">Tarafından çağrılır `Main()` hiçbir URI komut satırında sağlanan zaman.</span><span class="sxs-lookup"><span data-stu-id="9c051-120">It is called by `Main()` when no URI is provided on the command line.</span></span>  
  
- <span data-ttu-id="9c051-121">`RespCallBack()` Yöntemini uygulayan Internet istek için zaman uyumsuz geri çağırma yöntemi.</span><span class="sxs-lookup"><span data-stu-id="9c051-121">The `RespCallBack()` method implements the asynchronous callback method for the Internet request.</span></span> <span data-ttu-id="9c051-122">Oluşturur **WebResponse** Internet kaynağının yanıtı içeren örnek yanıt akışı alır ve ardından verileri akıştan zaman uyumsuz olarak okuma başlatır.</span><span class="sxs-lookup"><span data-stu-id="9c051-122">It creates the **WebResponse** instance containing the response from the Internet resource, gets the response stream, and then starts reading the data from the stream asynchronously.</span></span>  
  
- <span data-ttu-id="9c051-123">`ReadCallBack()` Yöntemini uygulayan yanıt akışına okumak için zaman uyumsuz geri çağırma yöntemi.</span><span class="sxs-lookup"><span data-stu-id="9c051-123">The `ReadCallBack()` method implements the asynchronous callback method for reading the response stream.</span></span> <span data-ttu-id="9c051-124">Internet kaynağına alınan veri aktarımları **ResponseData** özelliği **RequestState** örneği ve ardından başka bir zaman uyumsuz okuma yanıt akışı başka veri yok olana kadar başlatır döndürdü.</span><span class="sxs-lookup"><span data-stu-id="9c051-124">It transfers data received from the Internet resource into the **ResponseData** property of the **RequestState** instance, then starts another asynchronous read of the response stream until no more data is returned.</span></span> <span data-ttu-id="9c051-125">Tüm verileri okuduktan sonra `ReadCallBack()` çağırır ve yanıt akışı kapatır `allDone.Set()` yanıtın tamamını mevcut olduğunu belirtmek için yöntemi **ResponseData**.</span><span class="sxs-lookup"><span data-stu-id="9c051-125">Once all the data has been read, `ReadCallBack()` closes the response stream and calls the `allDone.Set()` method to indicate that the entire response is present in **ResponseData**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c051-126">Tüm ağ akışlarına kapalı olduğundan önemlidir.</span><span class="sxs-lookup"><span data-stu-id="9c051-126">It is critical that all network streams are closed.</span></span> <span data-ttu-id="9c051-127">Her istek ve yanıt akışı kapatmazsanız, uygulamanızın bağlantılar dışında sunucuya çalıştırın ve ek istekleri işleyemiyor.</span><span class="sxs-lookup"><span data-stu-id="9c051-127">If you do not close each request and response stream, your application will run out of connections to the server and be unable to process additional requests.</span></span>  
  
```csharp  
using System;  
using System.Net;  
using System.Threading;  
using System.Text;  
using System.IO;  
  
// The RequestState class passes data across async calls.  
public class RequestState  
{  
   const int BufferSize = 1024;  
   public StringBuilder RequestData;  
   public byte[] BufferRead;  
   public WebRequest Request;  
   public Stream ResponseStream;  
   // Create Decoder for appropriate enconding type.  
   public Decoder StreamDecode = Encoding.UTF8.GetDecoder();  
  
   public RequestState()  
   {  
      BufferRead = new byte[BufferSize];  
      RequestData = new StringBuilder(String.Empty);  
      Request = null;  
      ResponseStream = null;  
   }       
}  
  
// ClientGetAsync issues the async request.  
class ClientGetAsync   
{  
   public static ManualResetEvent allDone = new ManualResetEvent(false);  
   const int BUFFER_SIZE = 1024;  
  
   public static void Main(string[] args)   
   {  
      if (args.Length < 1)   
      {  
         showusage();  
         return;  
      }  
  
      // Get the URI from the command line.  
      Uri httpSite = new Uri(args[0]);  
  
      // Create the request object.  
      WebRequest wreq = WebRequest.Create(httpSite);  
  
      // Create the state object.  
      RequestState rs = new RequestState();  
  
      // Put the request into the state object so it can be passed around.  
      rs.Request = wreq;  
  
      // Issue the async request.  
      IAsyncResult r = (IAsyncResult) wreq.BeginGetResponse(  
         new AsyncCallback(RespCallback), rs);  
  
      // Wait until the ManualResetEvent is set so that the application   
      // does not exit until after the callback is called.  
      allDone.WaitOne();  
  
      Console.WriteLine(rs.RequestData.ToString());  
   }  
  
   public static void showusage() {  
      Console.WriteLine("Attempts to GET a URL");  
      Console.WriteLine("\r\nUsage:");  
      Console.WriteLine("   ClientGetAsync URL");  
      Console.WriteLine("   Example:");  
      Console.WriteLine("      ClientGetAsync http://www.contoso.com/");  
   }  
  
   private static void RespCallback(IAsyncResult ar)  
   {  
      // Get the RequestState object from the async result.  
      RequestState rs = (RequestState) ar.AsyncState;  
  
      // Get the WebRequest from RequestState.  
      WebRequest req = rs.Request;  
  
      // Call EndGetResponse, which produces the WebResponse object  
      //  that came from the request issued above.  
      WebResponse resp = req.EndGetResponse(ar);           
  
      //  Start reading data from the response stream.  
      Stream ResponseStream = resp.GetResponseStream();  
  
      // Store the response stream in RequestState to read   
      // the stream asynchronously.  
      rs.ResponseStream = ResponseStream;  
  
      //  Pass rs.BufferRead to BeginRead. Read data into rs.BufferRead  
      IAsyncResult iarRead = ResponseStream.BeginRead(rs.BufferRead, 0,   
         BUFFER_SIZE, new AsyncCallback(ReadCallBack), rs);   
   }  
  
   private static void ReadCallBack(IAsyncResult asyncResult)  
   {  
      // Get the RequestState object from AsyncResult.  
      RequestState rs = (RequestState)asyncResult.AsyncState;  
  
      // Retrieve the ResponseStream that was set in RespCallback.   
      Stream responseStream = rs.ResponseStream;  
  
      // Read rs.BufferRead to verify that it contains data.   
      int read = responseStream.EndRead( asyncResult );  
      if (read > 0)  
      {  
         // Prepare a Char array buffer for converting to Unicode.  
         Char[] charBuffer = new Char[BUFFER_SIZE];  
  
         // Convert byte stream to Char array and then to String.  
         // len contains the number of characters converted to Unicode.  
      int len =   
         rs.StreamDecode.GetChars(rs.BufferRead, 0, read, charBuffer, 0);  
  
         String str = new String(charBuffer, 0, len);  
  
         // Append the recently read data to the RequestData stringbuilder  
         // object contained in RequestState.  
         rs.RequestData.Append(  
            Encoding.ASCII.GetString(rs.BufferRead, 0, read));           
  
         // Continue reading data until   
         // responseStream.EndRead returns –1.  
         IAsyncResult ar = responseStream.BeginRead(   
            rs.BufferRead, 0, BUFFER_SIZE,   
            new AsyncCallback(ReadCallBack), rs);  
      }  
      else  
      {  
         if(rs.RequestData.Length>0)  
         {  
            //  Display data to the console.  
            string strContent;                    
            strContent = rs.RequestData.ToString();  
         }  
         // Close down the response stream.  
         responseStream.Close();           
         // Set the ManualResetEvent so the main thread can exit.  
         allDone.Set();                             
      }  
      return;  
   }      
}  
```  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Threading  
Imports System.Text  
Imports System.IO  
  
' The RequestState class passes data across async calls.  
Public Class RequestState  
  
      Public RequestData As New StringBuilder("")  
      Public BufferRead(1024) As Byte  
      Public Request As HttpWebRequest  
      Public ResponseStream As Stream  
      ' Create Decoder for appropriate encoding type.  
      Public StreamDecode As Decoder = Encoding.UTF8.GetDecoder()  
  
      Public Sub New  
         Request = Nothing  
         ResponseStream = Nothing  
      End Sub  
End Class  
  
' ClientGetAsync issues the async request.  
Class ClientGetAsync  
   Shared allDone As New ManualResetEvent(False)  
      Const BUFFER_SIZE As Integer = 1024  
  
    Shared Sub Main()  
        Dim Args As String() = Environment.GetCommandLineArgs()  
  
        If Args.Length < 2 Then  
            ShowUsage()  
            Return  
        End If  
  
      ' Get the URI from the command line.  
        Dim HttpSite As Uri = New Uri(Args(1))  
  
      ' Create the request object.  
        Dim wreq As HttpWebRequest = _  
           CType(WebRequest.Create(HttpSite), HttpWebRequest)  
  
      ' Create the state object.  
      Dim rs As RequestState = New RequestState()  
  
      ' Put the request into the state so it can be passed around.  
      rs.Request = wreq  
  
      ' Issue the async request.  
        Dim r As IAsyncResult = _  
           CType(wreq.BeginGetResponse( _  
           New AsyncCallback(AddressOf RespCallback), rs), IAsyncResult)  
  
      ' Wait until the ManualResetEvent is set so that the application  
      ' does not exit until after the callback is called.  
        allDone.WaitOne()  
    End Sub  
  
    Shared Sub ShowUsage()  
        Console.WriteLine("Attempts to GET a URI")  
        Console.WriteLine()  
        Console.WriteLine("Usage:")  
        Console.WriteLine("ClientGetAsync URI")  
        Console.WriteLine("Examples:")  
        Console.WriteLine("ClientGetAsync http://www.contoso.com/")  
    End Sub  
  
    Shared Sub RespCallback(ar As IAsyncResult)  
       ' Get the RequestState object from the async result.  
       Dim rs As RequestState = CType(ar.AsyncState, RequestState)  
  
       ' Get the HttpWebRequest from RequestState.  
       Dim req As HttpWebRequest= rs.Request  
  
       ' Call EndGetResponse, which returns the HttpWebResponse object  
       ' that came from the request issued above.  
       Dim resp As HttpWebResponse = _  
           CType(req.EndGetResponse(ar), HttpWebResponse)  
  
       ' Start reading data from the respons stream.  
       Dim ResponseStream As Stream = resp.GetResponseStream()  
  
       ' Store the reponse stream in RequestState to read  
       ' the stream asynchronously.  
       rs.ResponseStream = ResponseStream  
  
       ' Pass rs.BufferRead to BeginRead. Read data into rs.BufferRead.  
       Dim iarRead As IAsyncResult = _  
          ResponseStream.BeginRead(rs.BufferRead, 0, BUFFER_SIZE, _  
          New AsyncCallback(AddressOf ReadCallBack), rs)  
    End Sub  
  
   Shared Sub ReadCallBack(asyncResult As IAsyncResult)  
      ' Get the RequestState object from the AsyncResult.  
      Dim rs As RequestState = CType(asyncResult.AsyncState, RequestState)  
  
      ' Retrieve the ResponseStream that was set in RespCallback.  
      Dim responseStream As Stream = rs.ResponseStream  
  
      ' Read rs.BufferRead to verify that it contains data.  
      Dim read As Integer = responseStream.EndRead( asyncResult )  
      If read > 0 Then  
         ' Prepare a Char array buffer for converting to Unicode.  
         Dim charBuffer(1024) As Char  
  
         ' Convert byte stream to Char array and then String.  
         ' len contains the number of characters converted to Unicode.  
         Dim len As Integer = _  
           rs.StreamDecode.GetChars(rs.BufferRead, 0, read, charBuffer, 0)  
         Dim str As String = new String(charBuffer, 0, len)      
  
         ' Append the recently read data to the RequestData stringbuilder   
         ' object contained in RequestState.  
         rs.RequestData.Append( _  
            Encoding.ASCII.GetString(rs.BufferRead, 0, read))  
  
         ' Continue reading data until responseStream.EndRead  
         ' returns –1.  
         Dim ar As IAsyncResult = _  
            responseStream.BeginRead(rs.BufferRead, 0, BUFFER_SIZE, _  
            New AsyncCallback(AddressOf ReadCallBack), rs)  
      Else  
          If rs.RequestData.Length > 1 Then  
            ' Display data to the console.  
            Dim strContent As String  
            strContent = rs.RequestData.ToString()  
            Console.WriteLine(strContent)  
         End If  
  
         ' Close down the response stream.  
         responseStream.Close()  
  
         ' Set the ManualResetEvent so the main thread can exit.  
         allDone.Set()  
      End If  
  
      Return  
   End Sub  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c051-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9c051-128">See also</span></span>

- [<span data-ttu-id="9c051-129">Veri İsteme</span><span class="sxs-lookup"><span data-stu-id="9c051-129">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
