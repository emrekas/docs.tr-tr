---
title: "Nasıl yapılır: .NET Framework 3.0'in Yüklü Olup Olmadığını Algılama"
ms.date: 03/30/2017
helpviewer_keywords:
- WinFX Runtime user-agent string
- presence of WPT [WPF], detecting
- detecting WPF presence [WPF]
ms.assetid: 7f71d652-1749-4379-945a-aa2e3994cb43
ms.openlocfilehash: 27f856b895f48dc2365a1721dbc90294269899c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947829"
---
# <a name="how-to-detect-whether-the-net-framework-30-is-installed"></a><span data-ttu-id="3d88f-102">Nasıl yapılır: .NET Framework 3.0'in Yüklü Olup Olmadığını Algılama</span><span class="sxs-lookup"><span data-stu-id="3d88f-102">How to: Detect Whether the .NET Framework 3.0 Is Installed</span></span>
<span data-ttu-id="3d88f-103">Yöneticiler bir sistemde Microsoft .NET Framework uygulamaları dağıtmadan önce ilk olarak, .NET Framework çalışma zamanı mevcut olduğunu onaylamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="3d88f-103">Before administrators can deploy Microsoft .NET Framework applications on a system, they must first confirm that the .NET Framework runtime is present.</span></span> <span data-ttu-id="3d88f-104">Bu konu, HTML/JavaScript dilinde yazılmış bir komut dosyası sağlar. Yöneticiler, .NET Framework bir sistemde mevcut olup olmadığını belirlemek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d88f-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the .NET Framework is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d88f-105">Yükleme hakkında daha ayrıntılı bilgi için dağıtma ve Microsoft .NET Framework algılama içindeki tartışmalara bakın [dağıtma Microsoft .NET Framework sürüm 3.0](https://go.microsoft.com/fwlink/?LinkId=96739).</span><span class="sxs-lookup"><span data-stu-id="3d88f-105">For more detailed information on installing, deploying, and detecting the Microsoft .NET Framework, see the discussion in [Deploying Microsoft .NET Framework Version 3.0](https://go.microsoft.com/fwlink/?LinkId=96739).</span></span>  
  
<a name="content_expiration"></a>   
## <a name="detect-the-net-clr-user-agent-string"></a><span data-ttu-id="3d88f-106">".NET CLR" kullanıcı aracısı dizesi algılama</span><span class="sxs-lookup"><span data-stu-id="3d88f-106">Detect the ".NET CLR" User-Agent String</span></span>  
 <span data-ttu-id="3d88f-107">.NET Framework yüklendiğinde, MSI ".NET CLR" ve sürüm numarasını UserAgent dizesi olarak ekler.</span><span class="sxs-lookup"><span data-stu-id="3d88f-107">When .NET Framework is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="3d88f-108">Aşağıdaki örnek, basit bir HTML sayfasında yerleşik bir komut dosyası gösterir.</span><span class="sxs-lookup"><span data-stu-id="3d88f-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="3d88f-109">Komut dosyası, .NET Framework yüklü ve arama sonuçlarını temel durum iletisini görüntüler olup olmadığını belirlemek için UserAgent dizesi arar.</span><span class="sxs-lookup"><span data-stu-id="3d88f-109">The script searches the UserAgent string to determine whether .NET Framework is installed, and displays a status message on the results of the search.</span></span>  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.0</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.0.04425.00";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.0: "   
          + dotNETRuntimeVersion  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.0."  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 <span data-ttu-id="3d88f-110">".NET CLR" sürümü için arama başarılı olursa, aşağıdaki türde durum iletisi görüntülenir:</span><span class="sxs-lookup"><span data-stu-id="3d88f-110">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.0: 3.0.04425.00`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727; .NET CLR 3.0.04425.00).`  
  
 <span data-ttu-id="3d88f-111">Aksi takdirde, aşağıdaki türde durum iletisi görüntülenir:</span><span class="sxs-lookup"><span data-stu-id="3d88f-111">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have correct version of the .NET Framework 3.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727).`
