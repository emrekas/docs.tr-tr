---
ms.openlocfilehash: d48519443aeee05617538cf2cc12bea49ad3e16d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858473"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="21b83-101">Artık .NET sertifika olduğunda işleyemiyor X509Certificate2.ToString(Boolean) oluşturmaz</span><span class="sxs-lookup"><span data-stu-id="21b83-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

|   |   |
|---|---|
|<span data-ttu-id="21b83-102">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="21b83-102">Details</span></span>|<span data-ttu-id="21b83-103">.NET Framework 4.5.2 ve önceki sürümlerinde, bu yöntem, alanlarına <code>true</code> ayrıntılı parametresi için geçirilen ve yüklü olan ve .NET Framework tarafından desteklenen olmayan sertifikalar.</span><span class="sxs-lookup"><span data-stu-id="21b83-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="21b83-104">Şimdi, yöntem başarılı ve sertifika erişilemez kısımlarını atlayarak geçerli bir dize döndürür.</span><span class="sxs-lookup"><span data-stu-id="21b83-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>|
|<span data-ttu-id="21b83-105">Öneri</span><span class="sxs-lookup"><span data-stu-id="21b83-105">Suggestion</span></span>|<span data-ttu-id="21b83-106">Bağlı herhangi bir kod <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> döndürülen dizeyi bazı sertifika verilerini (örneğin, ortak anahtar, özel anahtarı ve Uzantılar) hariç tutabilir, API daha önce oluşturulan bazı durumlarda beklediğiniz şekilde güncelleştirilmesi.</span><span class="sxs-lookup"><span data-stu-id="21b83-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>|
|<span data-ttu-id="21b83-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="21b83-107">Scope</span></span>|<span data-ttu-id="21b83-108">Kenar</span><span class="sxs-lookup"><span data-stu-id="21b83-108">Edge</span></span>|
|<span data-ttu-id="21b83-109">Version</span><span class="sxs-lookup"><span data-stu-id="21b83-109">Version</span></span>|<span data-ttu-id="21b83-110">4.6</span><span class="sxs-lookup"><span data-stu-id="21b83-110">4.6</span></span>|
|<span data-ttu-id="21b83-111">Type</span><span class="sxs-lookup"><span data-stu-id="21b83-111">Type</span></span>|<span data-ttu-id="21b83-112">Çalışma zamanı</span><span class="sxs-lookup"><span data-stu-id="21b83-112">Runtime</span></span>|
|<span data-ttu-id="21b83-113">Etkilenen API’ler</span><span class="sxs-lookup"><span data-stu-id="21b83-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

