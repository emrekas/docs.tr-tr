---
title: Certmgr.exe (Sertifika Yönetim Aracı)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14dc09ff8ceaa5e754c2a8ee64846fbcac55e37f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779944"
---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="6ecc7-102">Certmgr.exe (Sertifika Yönetim Aracı)</span><span class="sxs-lookup"><span data-stu-id="6ecc7-102">Certmgr.exe (Certificate Manager Tool)</span></span>
<span data-ttu-id="6ecc7-103">Sertifika Yöneticisi aracı (Certmgr.exe) sertifikaları, sertifika güven listelerini (CTL) ve sertifika iptal listelerini (CRL) yönetir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-103">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="6ecc7-104">Sertifika Yöneticisi Visual Studio ile birlikte otomatik olarak yüklenir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-104">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="6ecc7-105">Aracı'nı başlatmak için [komut istemleri](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="6ecc7-105">To start the tool, use the [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ecc7-106">Sertifika Yöneticisi aracı (Certmgr.exe) bir komut satırı aracıyken, Sertifikalar (Certmgr.msc) bir Microsoft Yönetim Konsolu (MMC) ek bileşenidir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-106">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="6ecc7-107">Certmgr.msc genellikle Windows sistem dizininde bulduğundan girme `certmgr` Visual Studio için geliştirici komut istemi açmış olsanız bile sertifikalar MMC ek bileşenini komut satırında yükleyebilir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-107">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="6ecc7-108">Bu, PATH ortam değişkeninde ek bileşene olan yol Sertifika Yöneticisi aracına olan yoldan önce geldiği için gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-108">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="6ecc7-109">Eğer bu sorunla karşılaşırsanız, çalıştırılabilir öğenin yolunu belirterek Certmgr.exe komutlarını yürütebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-109">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>  
  
 <span data-ttu-id="6ecc7-110">Bu araç, Visual Studio ile birlikte otomatik olarak yüklenir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="6ecc7-111">Aracı çalıştırmak için Visual Studio (veya Windows 7'de Visual Studio komut istemi) için geliştirici Komut İstemi'ni kullanın.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-111">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="6ecc7-112">Daha fazla bilgi için [komut istemleri](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="6ecc7-112">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="6ecc7-113">X.509 sertifikalarına genel bakış için bkz. [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6ecc7-113">For an overview of X.509 certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="6ecc7-114">Komut satırına şunu yazın:</span><span class="sxs-lookup"><span data-stu-id="6ecc7-114">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ecc7-115">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6ecc7-115">Syntax</span></span>  
  
```  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ecc7-116">Parametreler</span><span class="sxs-lookup"><span data-stu-id="6ecc7-116">Parameters</span></span>  
  
|<span data-ttu-id="6ecc7-117">Bağımsız Değişken</span><span class="sxs-lookup"><span data-stu-id="6ecc7-117">Argument</span></span>|<span data-ttu-id="6ecc7-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6ecc7-118">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6ecc7-119">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="6ecc7-119">*sourceStorename*</span></span>|<span data-ttu-id="6ecc7-120">Eklenecek, silinecek, kaydedilecek veya görüntülenecek varolan sertifikaları, CTL'leri veya CRL'leri içeren sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-120">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="6ecc7-121">Bu bir depo dosyası veya sistem deposu olabilir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-121">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="6ecc7-122">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="6ecc7-122">*destinationStorename*</span></span>|<span data-ttu-id="6ecc7-123">Çıktı sertifika deposu veya dosyası.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-123">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="6ecc7-124">Seçenek</span><span class="sxs-lookup"><span data-stu-id="6ecc7-124">Option</span></span>|<span data-ttu-id="6ecc7-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6ecc7-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6ecc7-126">**/ add**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-126">**/add**</span></span>|<span data-ttu-id="6ecc7-127">Bir sertifika deposuna sertifikalar, CTL'ler ve CRL'ler ekler.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-127">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="6ecc7-128">**/ all**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-128">**/all**</span></span>|<span data-ttu-id="6ecc7-129">İle kullanıldığında tüm girdileri ekler **/ add**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-129">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="6ecc7-130">İle kullanıldığında tüm girdileri siler **/del**. Olmadan kullanıldığında tüm girdileri görüntüler **/ add** veya **/del** seçenekleri.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-130">Deletes all entries when used with **/del**. Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="6ecc7-131">**/All** seçeneği ile kullanılamaz **/put**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-131">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="6ecc7-132">**/c**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-132">**/c**</span></span>|<span data-ttu-id="6ecc7-133">İle kullanıldığında sertifikaları ekler **/ add**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-133">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="6ecc7-134">İle kullanıldığında sertifikaları siler **/del**. İle kullanıldığında sertifikaları kaydeder **/put**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-134">Deletes certificates when used with **/del**. Saves certificates when used with **/put**.</span></span> <span data-ttu-id="6ecc7-135">Görüntüler olmadan kullanıldığında sertifikaları **/ add**, **/del**, veya **/put** seçeneği.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-135">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="6ecc7-136">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-136">**/CRL**</span></span>|<span data-ttu-id="6ecc7-137">İle kullanıldığında CRL'leri ekler **/ add**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-137">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="6ecc7-138">İle kullanıldığında CRL'leri siler **/del**. İle kullanıldığında CRL'leri kaydeder **/put**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-138">Deletes CRLs when used with **/del**. Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="6ecc7-139">Görüntüler olmadan kullanıldığında CRL'leri **/ add**, **/del**, veya **/put** seçeneği.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-139">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="6ecc7-140">**/ CTL**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-140">**/CTL**</span></span>|<span data-ttu-id="6ecc7-141">İle kullanıldığında CTL'leri ekler **/ add**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-141">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="6ecc7-142">İle kullanıldığında CTL'leri siler **/del**. İle kullanıldığında CTL'leri kaydeder **/put**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-142">Deletes CTLs when used with **/del**. Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="6ecc7-143">Görüntüler olmadan kullanıldığında CTL'leri **/ add**, **/del**, veya **/put** seçeneği.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-143">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="6ecc7-144">**/ DEL**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-144">**/del**</span></span>|<span data-ttu-id="6ecc7-145">Bir sertifika deposundan sertifikaları, CTL'leri ve CRL'leri siler.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-145">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="6ecc7-146">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="6ecc7-146">**/e** *encodingType*</span></span>|<span data-ttu-id="6ecc7-147">Sertifika kodlama türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-147">Specifies the certificate encoding type.</span></span> <span data-ttu-id="6ecc7-148">Varsayılan, `X509_ASN_ENCODING` değeridir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-148">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="6ecc7-149">**/f** *CertOpenStore*</span><span class="sxs-lookup"><span data-stu-id="6ecc7-149">**/f** *dwFlags*</span></span>|<span data-ttu-id="6ecc7-150">Depo açık bayrağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-150">Specifies the store open flag.</span></span> <span data-ttu-id="6ecc7-151">Bu *CertOpenStore* geçirilen **Dwflags**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-151">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="6ecc7-152">Varsayılan değer CERT_SYSTEM_STORE_CURRENT_USER değeridir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-152">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="6ecc7-153">Bu seçenek yalnızca değerlendirilir **/y** seçeneği kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-153">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="6ecc7-154">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="6ecc7-154">**/h**[**elp**]</span></span>|<span data-ttu-id="6ecc7-155">Araç için komut sözdizimini ve seçenekleri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-155">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="6ecc7-156">**/n** *adı*</span><span class="sxs-lookup"><span data-stu-id="6ecc7-156">**/n** *nam*</span></span>|<span data-ttu-id="6ecc7-157">Eklenecek, silinecek veya kaydedilecek sertifika için ortak adı belirtir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-157">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="6ecc7-158">Bu seçenek yalnızca sertifikalarla kullanılabilir; CTL'ler veya CRL'ler ile kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-158">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="6ecc7-159">**/ put**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-159">**/put**</span></span>|<span data-ttu-id="6ecc7-160">Bir sertifika deposundan bir X.509 sertifikasını, CTL'yi veya CRL'yi dosyaya kaydeder.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-160">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="6ecc7-161">Dosya X.509 biçiminde kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-161">The file is saved in X.509 format.</span></span> <span data-ttu-id="6ecc7-162">Kullanabileceğiniz **/7** seçeneğini **/put** dosyayı PKCS #7 biçiminde kaydetmek için seçeneği.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-162">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="6ecc7-163">**/Put** seçeneği tarafından gelmelidir **/c**, **/CTL**, veya **/CRL**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-163">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="6ecc7-164">**/All** seçeneği ile kullanılamaz **/put**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-164">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="6ecc7-165">**/r** *konumu*</span><span class="sxs-lookup"><span data-stu-id="6ecc7-165">**/r** *location*</span></span>|<span data-ttu-id="6ecc7-166">Sistem deposu için kayıt defteri konumunu tanımlar.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-166">Identifies the registry location of the system store.</span></span> <span data-ttu-id="6ecc7-167">Bu seçenek yalnızca belirtirseniz değerlendirilir **/s** seçeneği.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-167">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="6ecc7-168">*Konum* aşağıdakilerden biri olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="6ecc7-168">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="6ecc7-169">-   `currentUser` Sertifika deposunun HKEY_CURRENT_USER anahtarı altında olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-169">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="6ecc7-170">Bu varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-170">This is the default.</span></span><br /><span data-ttu-id="6ecc7-171">-   `localMachine` Sertifika deposunun HKEY_LOCAL_MACHINE anahtarı altında olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-171">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="6ecc7-172">**/s**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-172">**/s**</span></span>|<span data-ttu-id="6ecc7-173">Sertifika deposunun bir sistem deposu olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-173">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="6ecc7-174">Bu seçeneği belirtmezseniz, depo olarak kabul edilir bir **StoreFile**.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-174">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="6ecc7-175">**{1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="6ecc7-175">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="6ecc7-176">Eklenecek, silinecek veya kaydedilecek sertifikanın, CTL'nin veya CRL'nin SHA1 karmasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-176">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="6ecc7-177">**/v**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-177">**/v**</span></span>|<span data-ttu-id="6ecc7-178">Ayrıntılı modu belirtir; sertifikalar, CTL'ler ve CRL'ler hakkında ayrıntılı bilgi görüntüler.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-178">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="6ecc7-179">Bu seçenek kullanılamaz **/ add**, **/del**, veya **/put** seçenekleri.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-179">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="6ecc7-180">**/y** *sağlayıcısı*</span><span class="sxs-lookup"><span data-stu-id="6ecc7-180">**/y** *provider*</span></span>|<span data-ttu-id="6ecc7-181">Depo sağlayıcısı adını sağlar.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-181">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="6ecc7-182">**/7**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-182">**/7**</span></span>|<span data-ttu-id="6ecc7-183">Hedef depoyu bir PKCS #7 nesnesi olarak kaydeder.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-183">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="6ecc7-184">**/?**</span><span class="sxs-lookup"><span data-stu-id="6ecc7-184">**/?**</span></span>|<span data-ttu-id="6ecc7-185">Araç için komut sözdizimini ve seçenekleri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-185">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ecc7-186">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6ecc7-186">Remarks</span></span>  
 <span data-ttu-id="6ecc7-187">Certmgr.exe aşağıdaki temel işlevleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="6ecc7-187">Certmgr.exe performs the following basic functions:</span></span>  
  
- <span data-ttu-id="6ecc7-188">Sertifikaları, CTL'leri ve CRL'leri konsolda görüntüler.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-188">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
- <span data-ttu-id="6ecc7-189">Bir sertifika deposuna sertifikalar, CTL'ler ve CRL'ler ekler.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-189">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
- <span data-ttu-id="6ecc7-190">Bir sertifika deposundan sertifikaları, CTL'leri ve CRL'leri siler.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-190">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
- <span data-ttu-id="6ecc7-191">Bir sertifika deposundan bir X.509 sertifikasını, CTL'yi veya CRL'yi dosyaya kaydeder.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-191">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="6ecc7-192">Certmgr.exe iki tür sertifika ile çalışır: **StoreFile** ve sistem deposu.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-192">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="6ecc7-193">Sertifika deposu türünü belirtmek gerekli değildir: Certmgr.exe depo türünü tanımlayarak uygun işlemleri gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-193">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="6ecc7-194">Certmgr.exe'yi hiçbir seçenek olmadan belirtmek, komut satırından kullanılabilen sertifika yönetim görevlerine yardımcı olan bir GUI'ye sahip certmgr.msc ek bileşenini yönetir.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-194">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="6ecc7-195">GUI; sertifikaları, CTL'leri ve CRL'leri diskinizden bir sertifika deposuna kopyalayan bir içeri aktarma sihirbazı sağlar.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-195">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="6ecc7-196">İçin X509Certificate depolarının adlarını bulabilirsiniz `sourceStorename` ve `destinationStorename` derleyerek ve aşağıdaki kodu çalıştırarak parametreleri.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-196">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 <span data-ttu-id="6ecc7-197">Sertifikalar hakkında daha fazla bilgi için bkz. [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6ecc7-197">For more information about certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6ecc7-198">Örnekler</span><span class="sxs-lookup"><span data-stu-id="6ecc7-198">Examples</span></span>  
 <span data-ttu-id="6ecc7-199">Aşağıdaki komut adı verilen bir varsayılan sistem deposunu görüntüler `my` ayrıntılı çıktıyla.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-199">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```  
certmgr /v /s my  
```  
  
 <span data-ttu-id="6ecc7-200">Aşağıdaki komut, tüm sertifikaları adlı bir dosyaya ekler. `myFile.ext` adlı yeni bir dosyaya `newFile.ext`.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-200">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="6ecc7-201">Aşağıdaki komut, adlı dosyadaki sertifikayı ekler `testcert.cer` için `my` sistem deposu.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-201">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="6ecc7-202">Aşağıdaki komut, adlı dosyadaki sertifikayı ekler `TrustedCert.cer` kök sertifika deposuna.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-202">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="6ecc7-203">Aşağıdaki komut ortak adına sahip bir sertifika kaydeder `myCert` içinde `my` adlı bir dosyaya sistem deposu `newCert.cer`.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-203">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="6ecc7-204">Aşağıdaki komut, tüm CTL'leri siler `my` sistem deposu ve adlı bir dosya elde edilen depoyu kaydeder `newStore.str`.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-204">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="6ecc7-205">Aşağıdaki komutu bir sertifikada kaydeder `my` sistem deposu dosyasındaki `newFile`.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-205">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="6ecc7-206">Sertifika numarasını girmeniz istenir `my` yerleştirmek için `newFile`.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-206">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ecc7-207">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6ecc7-207">See also</span></span>

- [<span data-ttu-id="6ecc7-208">Araçlar</span><span class="sxs-lookup"><span data-stu-id="6ecc7-208">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="6ecc7-209">MakeCert.exe (sertifika oluşturma aracı)</span><span class="sxs-lookup"><span data-stu-id="6ecc7-209">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="6ecc7-210">Komut İstemleri</span><span class="sxs-lookup"><span data-stu-id="6ecc7-210">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
