---
title: 'Nasıl yapılır: FTP ile dizin içeriğini listeleme'
description: Bu makalede, FTP sunucusunda dizin içeriğini listeleme bir örneği gösterilmektedir.
ms.date: 06/26/2018
dev_langs:
- csharp
- vb
ms.assetid: 130c64c9-7b7f-4672-9b3b-d946bd2616c5
ms.openlocfilehash: 924e6731ce585f127af319fdbfbdc8c12e61c46d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61642626"
---
# <a name="how-to-list-directory-contents-with-ftp"></a><span data-ttu-id="d138d-103">Nasıl yapılır: FTP ile dizin içeriğini listeleme</span><span class="sxs-lookup"><span data-stu-id="d138d-103">How to: List directory contents with FTP</span></span>

<span data-ttu-id="d138d-104">Bu örnek, bir FTP sunucusuna dizin içeriğini listeleme gösterir.</span><span class="sxs-lookup"><span data-stu-id="d138d-104">This sample shows how to list the directory contents of an FTP server.</span></span>

## <a name="example"></a><span data-ttu-id="d138d-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="d138d-105">Example</span></span>

```csharp
using System;
using System.IO;
using System.Net;

namespace Examples.System.Net
{
    public class WebRequestGetExample
    {
        public static void Main ()
        {
            // Get the object used to communicate with the server.
            FtpWebRequest request = (FtpWebRequest)WebRequest.Create("ftp://www.contoso.com/");
            request.Method = WebRequestMethods.Ftp.ListDirectoryDetails;

            // This example assumes the FTP site uses anonymous logon.
            request.Credentials = new NetworkCredential ("anonymous","janeDoe@contoso.com");

            FtpWebResponse response = (FtpWebResponse)request.GetResponse();

            Stream responseStream = response.GetResponseStream();
            StreamReader reader = new StreamReader(responseStream);
            Console.WriteLine(reader.ReadToEnd());

            Console.WriteLine($"Directory List Complete, status {response.StatusDescription}");

            reader.Close();
            response.Close();
        }
    }
}
```

```vb
Imports System.IO
Imports System.Net

Namespace Examples.System.Net
    Public Module WebRequestGetExample
        Public Sub Main()
            ' Get the object used to communicate with the server.
            Dim request As FtpWebRequest = CType(WebRequest.Create("ftp://www.contoso.com/"), FtpWebRequest)
            request.Method = WebRequestMethods.Ftp.ListDirectoryDetails

            ' This example assumes the FTP site uses anonymous logon.
            request.Credentials = New NetworkCredential("anonymous", "janeDoe@contoso.com")

            Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)

            Dim responseStream As Stream = response.GetResponseStream()
            Dim reader As StreamReader = New StreamReader(responseStream)
            Console.WriteLine(reader.ReadToEnd())

            Console.WriteLine($"Directory List Complete, status {response.StatusDescription}")

            reader.Close()
            response.Close()
        End Sub
    End Module
End Namespace
```

<span data-ttu-id="d138d-106">Belirli bir dizin listesi gerekiyorsa, yalnızca dizin, kullanmakta olduğunuz URI'nin sonuna Ekle <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> yöntemi:</span><span class="sxs-lookup"><span data-stu-id="d138d-106">If you need to list a specific directory, just add the directory to the end of the URI you're using in the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method:</span></span>

```csharp
FtpWebRequest request = (FtpWebRequest)WebRequest.Create("ftp://www.contoso.com/your_preferred_directory");
```

```vb
Dim request As FtpWebRequest = CType(WebRequest.Create("ftp://www.contoso.com/your_preferred_directory"), FtpWebRequest)
```
