---
title: "Nasıl yapılır: .NET Framework 3.5'in Yüklü Olup Olmadığını Algılama"
ms.date: 03/30/2017
helpviewer_keywords:
- verifying whether.NET Framework 3.5 is installed [WPF]
- detecting .NET Framework 3.5 installation [WPF]
- detecting whether.NET Framework 3.5 is installed [WPF]
- determining whether.NET Framework 3.5 is installed [WPF]
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
ms.openlocfilehash: 69dfa0eb8d9ad9b780d258a874d255484f270cfe
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690440"
---
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a><span data-ttu-id="601ee-102">Nasıl yapılır: .NET Framework 3.5'in Yüklü Olup Olmadığını Algılama</span><span class="sxs-lookup"><span data-stu-id="601ee-102">How to: Detect Whether the .NET Framework 3.5 Is Installed</span></span>
<span data-ttu-id="601ee-103">Yöneticiler, .NET Framework 3. 5'i hedefleyen bir sistemde Windows Presentation Foundation (WPF) uygulamaları dağıtmadan önce ilk olarak, .NET Framework 3.5 çalışma zamanı mevcut olduğunu onaylamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="601ee-103">Before administrators can deploy Windows Presentation Foundation (WPF) applications on a system that targets the .NET Framework 3.5, they must first confirm that the .NET Framework 3.5 runtime is present.</span></span> <span data-ttu-id="601ee-104">Bu konu, HTML/JavaScript dilinde yazılmış bir komut dosyası sağlar. Yöneticiler, .NET Framework 3.5 bir sistemde mevcut olup olmadığını belirlemek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="601ee-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the .NET Framework 3.5 is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="601ee-105">Yükleme hakkında daha ayrıntılı bilgi için bkz: dağıtma ve .NET Framework'ü algılama [geliştiriciler için .NET Framework yükleme](../../install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="601ee-105">For more detailed information on installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="601ee-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="601ee-106">Example</span></span>  
 <span data-ttu-id="601ee-107">.NET Framework 3.5 yüklendiğinde, MSI ".NET CLR" ve sürüm numarasını UserAgent dizesi olarak ekler.</span><span class="sxs-lookup"><span data-stu-id="601ee-107">When the .NET Framework 3.5 is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="601ee-108">Aşağıdaki örnek, basit bir HTML sayfasında yerleşik bir komut dosyası gösterir.</span><span class="sxs-lookup"><span data-stu-id="601ee-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="601ee-109">Komut dosyası, .NET Framework 3.5 yüklenir ve arama sonuçlarını temel durum iletisini görüntüler olup olmadığını belirlemek için UserAgent dizesi arar.</span><span class="sxs-lookup"><span data-stu-id="601ee-109">The script searches the UserAgent string to determine whether the .NET Framework 3.5 is installed, and displays a status message on the results of the search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="601ee-110">Bu betik, Internet Explorer için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="601ee-110">This script is designed for Internet Explorer.</span></span> <span data-ttu-id="601ee-111">Diğer tarayıcılarda UserAgent dizesi içinde .NET CLR bilgileri içermeyebilir.</span><span class="sxs-lookup"><span data-stu-id="601ee-111">Other browsers may not include .NET CLR information in the UserAgent string.</span></span>  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.5</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.5.0.0";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.5."  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.5." +  
          " The required version is v" + dotNETRuntimeVersion + ".";  
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
  
 <span data-ttu-id="601ee-112">".NET CLR" sürümü için arama başarılı olursa, aşağıdaki türde durum iletisi görüntülenir:</span><span class="sxs-lookup"><span data-stu-id="601ee-112">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 <span data-ttu-id="601ee-113">Aksi takdirde, aşağıdaki türde durum iletisi görüntülenir:</span><span class="sxs-lookup"><span data-stu-id="601ee-113">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a><span data-ttu-id="601ee-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="601ee-114">See also</span></span>

- [<span data-ttu-id="601ee-115">.NET Framework 3.0'ın Yüklü Olup Olmadığını Algılama</span><span class="sxs-lookup"><span data-stu-id="601ee-115">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
