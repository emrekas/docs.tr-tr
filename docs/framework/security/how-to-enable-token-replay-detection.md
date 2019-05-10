---
title: 'Nasıl yapılır: Belirteç Yeniden Yürütme Algılamasını Etkinleştirme'
ms.date: 03/30/2017
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
author: BrucePerlerMS
ms.openlocfilehash: 0149bf424751a0c95337743b02465629826d9686
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625847"
---
# <a name="how-to-enable-token-replay-detection"></a><span data-ttu-id="3e3e1-102">Nasıl yapılır: Belirteç Yeniden Yürütme Algılamasını Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="3e3e1-102">How To: Enable Token Replay Detection</span></span>
## <a name="applies-to"></a><span data-ttu-id="3e3e1-103">Uygulanan Öğe</span><span class="sxs-lookup"><span data-stu-id="3e3e1-103">Applies To</span></span>  
  
- <span data-ttu-id="3e3e1-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="3e3e1-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="3e3e1-105">ASP.NET® Web formları</span><span class="sxs-lookup"><span data-stu-id="3e3e1-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="3e3e1-106">Özet</span><span class="sxs-lookup"><span data-stu-id="3e3e1-106">Summary</span></span>  
 <span data-ttu-id="3e3e1-107">Bu nasıl yapılır, WIF kullanan ASP.NET uygulamasında belirteç yeniden yürütme algılaması etkinleştirmek için adım adım ayrıntılı yordamları sağlar.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-107">This How-To provides detailed step-by-step procedures for enabling token replay detection in an ASP.NET application that uses WIF.</span></span> <span data-ttu-id="3e3e1-108">Ayrıca, belirteç yeniden yürütme algılaması etkin olduğunu doğrulamak için uygulamayı test etme için yönergeler sağlar.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-108">It also provides instructions for how to test the application to verify that token replay detection is enabled.</span></span> <span data-ttu-id="3e3e1-109">Bu 'Nasıl Yapılır' konusunda bir Güvenlik Belirteci Hizmeti (STS) oluşturmaya yönelik ayrıntılı yönergeler yer almaz ve bunun yerine Kimlik ve Erişim aracı ile birlikte gelen Geliştirme STS'si kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="3e3e1-110">Geliştirme STS'si gerçek kimlik doğrulaması yapmaz ve yalnızca test amaçlarına yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="3e3e1-111">Bu 'Nasıl Yapılır' konusunu tamamlamak için Kimlik ve Erişim aracını yüklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="3e3e1-112">Şu konumdan indirilebilir: [Kimlik ve erişim aracı](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="3e3e1-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="3e3e1-113">İçindekiler</span><span class="sxs-lookup"><span data-stu-id="3e3e1-113">Contents</span></span>  
  
- <span data-ttu-id="3e3e1-114">Amaçlar</span><span class="sxs-lookup"><span data-stu-id="3e3e1-114">Objectives</span></span>  
  
- <span data-ttu-id="3e3e1-115">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="3e3e1-115">Overview</span></span>  
  
- <span data-ttu-id="3e3e1-116">Adımların Özeti</span><span class="sxs-lookup"><span data-stu-id="3e3e1-116">Summary of Steps</span></span>  
  
- <span data-ttu-id="3e3e1-117">1. adım – basit bir ASP.NET Web Forms uygulaması oluşturun ve yeniden yürütme algılamayı etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="3e3e1-117">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
- <span data-ttu-id="3e3e1-118">2. adım – çözümünüzü test etme</span><span class="sxs-lookup"><span data-stu-id="3e3e1-118">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="3e3e1-119">Amaçlar</span><span class="sxs-lookup"><span data-stu-id="3e3e1-119">Objectives</span></span>  
  
- <span data-ttu-id="3e3e1-120">WIF ve kimlik ve erişim aracı geliştirme STS'sini kullanan basit bir ASP.NET uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="3e3e1-120">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
- <span data-ttu-id="3e3e1-121">Belirteç yeniden yürütme algılamayı etkinleştirme ve çalışır durumda olduğunu doğrulayın</span><span class="sxs-lookup"><span data-stu-id="3e3e1-121">Enable token replay detection and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="3e3e1-122">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="3e3e1-122">Overview</span></span>  
 <span data-ttu-id="3e3e1-123">Yeniden yürütme saldırı, bir istemci istemcinin zaten kullanmış olduğu bir STS belirteci ile bağlı olan taraf için kimlik doğrulama girişiminde bulunduğunda oluşur.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-123">A replay attack occurs when a client attempts to authenticate to a relying party with an STS token that the client has already used.</span></span> <span data-ttu-id="3e3e1-124">Bu saldırı önlemeye yardımcı olmak için önceden kullanılmış STS belirteç yeniden yürütme algılama önbelleğini WIF içerir.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-124">To help prevent this attack, WIF contains a replay detection cache of previously used STS tokens.</span></span> <span data-ttu-id="3e3e1-125">Etkin olduğunda, yeniden yürütme algılaması gelen istek belirtecini denetler ve belirteci daha önce kullanılan olup olmadığını doğrular.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-125">When enabled, replay detection checks the token of the incoming request and verifies whether or not the token has been previously used.</span></span> <span data-ttu-id="3e3e1-126">Belirteç zaten kullanılıyor, istek reddedildi ve <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> özel durumu oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-126">If the token has been used already, the request is refused and a <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> exception is thrown.</span></span>  
  
 <span data-ttu-id="3e3e1-127">Aşağıdaki adımlarda, yeniden yürütme algılamayı etkinleştirmek için gereken yapılandırma değişikliklerini gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-127">The following steps demonstrate the configuration changes required to enable replay detection.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="3e3e1-128">Adımların Özeti</span><span class="sxs-lookup"><span data-stu-id="3e3e1-128">Summary of Steps</span></span>  
  
- <span data-ttu-id="3e3e1-129">1. adım – basit bir ASP.NET Web Forms uygulaması oluşturun ve yeniden yürütme algılamayı etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="3e3e1-129">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
- <span data-ttu-id="3e3e1-130">2. adım – çözümünüzü test etme</span><span class="sxs-lookup"><span data-stu-id="3e3e1-130">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-replay-detection"></a><span data-ttu-id="3e3e1-131">1. adım – basit bir ASP.NET Web Forms uygulaması oluşturun ve yeniden yürütme algılamayı etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="3e3e1-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
 <span data-ttu-id="3e3e1-132">Bu adımda, yeni bir ASP.NET Web Forms uygulaması oluşturacak ve değiştirme *Web.config* yeniden yürütme algılamayı etkinleştirmek için dosya.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-132">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable replay detection.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="3e3e1-133">Basit bir ASP.NET uygulaması oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="3e3e1-133">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="3e3e1-134">Visual Studio'yu başlatın ve tıklayın **dosya**, **yeni**, ardından **proje**.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-134">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2. <span data-ttu-id="3e3e1-135">İçinde **yeni proje** penceresinde tıklayın **ASP.NET Web Forms uygulaması**.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-135">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3. <span data-ttu-id="3e3e1-136">İçinde **adı**, girin `TestApp` basın **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-136">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4. <span data-ttu-id="3e3e1-137">Sağ **TestApp** altındaki proje **Çözüm Gezgini**, ardından **kimlik ve erişim**.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-137">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5. <span data-ttu-id="3e3e1-138">**Kimlik ve erişim** penceresi görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-138">The **Identity and Access** window appears.</span></span> <span data-ttu-id="3e3e1-139">Altında **sağlayıcıları**seçin **uygulamanızı yerel geliştirme STS'si ile Test**, ardından **Uygula**.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-139">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6. <span data-ttu-id="3e3e1-140">Aşağıdaki  **\<tokenReplayDetection >** öğesine *Web.config* hemen yapılandırma dosyası  **\<System.IdentityModel >** ve  **\<identityConfiguration >** gibi öğeler, gösterilen:</span><span class="sxs-lookup"><span data-stu-id="3e3e1-140">Add the following **\<tokenReplayDetection>** element to the *Web.config* configuration file immediately following the **\<system.identityModel>** and **\<identityConfiguration>** elements, like shown:</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled="true"/>  
    ```  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="3e3e1-141">2. adım – çözümünüzü test etme</span><span class="sxs-lookup"><span data-stu-id="3e3e1-141">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="3e3e1-142">Bu adımda, WIF özelliği etkinleştirilmiş ASP.NET uygulamanızı yeniden yürütme algılaması etkin olduğunu doğrulamak için test eder.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-142">In this step, you will test your WIF-enabled ASP.NET application to verify that replay detection has been enabled.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-replay-detection"></a><span data-ttu-id="3e3e1-143">Yeniden yürütme algılaması için WIF özelliği etkinleştirilmiş ASP.NET uygulamanızı test etmek için</span><span class="sxs-lookup"><span data-stu-id="3e3e1-143">To test your WIF-enabled ASP.NET application for replay detection</span></span>  
  
1. <span data-ttu-id="3e3e1-144">Tuşlarına basarak çözümü çalıştırın **F5** anahtarı.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-144">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="3e3e1-145">Verilecek varsayılan ASP.NET ana sayfası gösterilir ve otomatik olarak kullanıcı adıyla kimlik doğrulaması *Terry*, geliştirme STS tarafından döndürülen varsayılan kullanıcı olduğu.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-145">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2. <span data-ttu-id="3e3e1-146">Tarayıcının basın **geri** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-146">Press the browser’s **Back** button.</span></span> <span data-ttu-id="3e3e1-147">İle sunulan bir **'/' uygulamasında sunucu hatası** şu açıklama ile sayfası: *ID1062: Yeniden yürütme için algılandı: belirteci: 'System.IdentityModel.Tokens.SamlSecurityToken'* ve ardından bir *onaylama kimliği* ve *veren*.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-147">You should be presented with a **Server Error in ‘/’ Application** page with the following description: *ID1062: Replay has been detected for: Token: 'System.IdentityModel.Tokens.SamlSecurityToken'*, followed by an *AssertionId* and an *Issuer*.</span></span>  
  
     <span data-ttu-id="3e3e1-148">Bu hata sayfası için görüyorsunuz türünde bir özel durum <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> belirteç yeniden yürütme algılandığında oluşturuldu.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-148">You are seeing this error page because an exception of type <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> was thrown when the token replay was detected.</span></span> <span data-ttu-id="3e3e1-149">Belirtecin ilk yansıtılırken ilk POST isteği yeniden göndermek denediğinizden bu hata oluşur.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-149">This error occurs because you are attempting to re-send the initial POST request when the token was first presented.</span></span> <span data-ttu-id="3e3e1-150">**Geri** düğmesi değil neden bu davranışı sunucuya sonraki isteklerde.</span><span class="sxs-lookup"><span data-stu-id="3e3e1-150">The **Back** button will not cause this behavior on subsequent requests to the server.</span></span>
