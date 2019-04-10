---
title: WCF ve Uluslararası Hale Getirilmiş Etki Alanı Adları
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: c53c22e388ec352b1275018c0b945c9608565084
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335387"
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="6aa96-102">WCF ve Uluslararası Hale Getirilmiş Etki Alanı Adları</span><span class="sxs-lookup"><span data-stu-id="6aa96-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="6aa96-103">WCF hizmetleri Uluslararası yapılan etki alanı adı (IDN) ile izin vermek için destek eklendi.</span><span class="sxs-lookup"><span data-stu-id="6aa96-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="6aa96-104">Bir Uluslararası yapılan etki alanı adı, ASCII olmayan karakterler içeren bir etki alanı adı değil.</span><span class="sxs-lookup"><span data-stu-id="6aa96-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="6aa96-105">Bir WCF istemcisi IDN adı ile bir web hizmeti konuşabilir bir IDN adı ile bir WCF Hizmeti barındırma her iki özelliği destekler.</span><span class="sxs-lookup"><span data-stu-id="6aa96-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="6aa96-106">System.Uri ve IDN</span><span class="sxs-lookup"><span data-stu-id="6aa96-106">System.Uri and IDN</span></span>  
 <xref:System.Uri> <span data-ttu-id="6aa96-107">iki özelliğe sahiptir <xref:System.Uri.Host%2A> ve <xref:System.Uri.DnsSafeHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="6aa96-107">has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="6aa96-108">Bu özellikler, IDN yapılandırma ayarlarına bağlı olarak, Unicode veya Punycode değerleri içerir.</span><span class="sxs-lookup"><span data-stu-id="6aa96-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="6aa96-109">Bir uygulamanın yapılandırma dosyasında aşağıdaki XML kullanarak IDN etkin</span><span class="sxs-lookup"><span data-stu-id="6aa96-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="6aa96-110">\<IDN > öğesi içerir etkin özniteliği şu değerlerden birine ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="6aa96-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1. <span data-ttu-id="6aa96-111">"None"</span><span class="sxs-lookup"><span data-stu-id="6aa96-111">"None"</span></span>  
  
2. <span data-ttu-id="6aa96-112">"AllExceptIntranet"</span><span class="sxs-lookup"><span data-stu-id="6aa96-112">"AllExceptIntranet"</span></span>  
  
3. <span data-ttu-id="6aa96-113">"Tüm"</span><span class="sxs-lookup"><span data-stu-id="6aa96-113">"All"</span></span>  
  
 <span data-ttu-id="6aa96-114">IDN ayarını "Yok" olarak ayarlandığında, hiçbir dönüştürmeler Uri.Host veya Uri.DnsSafeHost tarafından gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="6aa96-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="6aa96-115">Ne zaman IDN ayarı "Tümü", URI ayarlanır. Konak, Unicode ve URI kalır. DnsSafeHost kodlar, zayıf koda dönüştürülür.</span><span class="sxs-lookup"><span data-stu-id="6aa96-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="6aa96-116">Ne zaman IDN ayarı "AllExceptIntranet için", URI ayarlanır. DnsSafeHost internet adresleri için kodlar, zayıf koda dönüştürülür ve Unicode için intranet adresleri kalır.</span><span class="sxs-lookup"><span data-stu-id="6aa96-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="6aa96-117">Bu ayar, doğru DNS ad çözümlemesi için önemlidir.</span><span class="sxs-lookup"><span data-stu-id="6aa96-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="6aa96-118">Bu ayar Windows 8 ve daha yeni sürümleri için yapılandırılması için gerekli olmayan unutmayın.</span><span class="sxs-lookup"><span data-stu-id="6aa96-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6aa96-119">Hiçbir sabit kodlu gereken zayıf kod kullanarak bir adres.</span><span class="sxs-lookup"><span data-stu-id="6aa96-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="6aa96-120">WCF uyguladığınız yapılandırma ayarlarına göre bunu dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="6aa96-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6aa96-121">Unicode karakterler için applicationHost.exe.config eklerken, UTF-8 kodlaması kullanarak dosyayı kaydedin.</span><span class="sxs-lookup"><span data-stu-id="6aa96-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa96-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6aa96-122">See also</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
