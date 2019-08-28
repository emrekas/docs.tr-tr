---
title: 'Nasıl yapılır: Gelen Talepleri Dönüştürme'
ms.date: 03/30/2017
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
author: BrucePerlerMS
ms.openlocfilehash: ce99b97007bf7608856345d6da87cd9e422d2266
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041474"
---
# <a name="how-to-transform-incoming-claims"></a><span data-ttu-id="17111-102">Nasıl yapılır: Gelen Talepleri Dönüştürme</span><span class="sxs-lookup"><span data-stu-id="17111-102">How To: Transform Incoming Claims</span></span>

## <a name="applies-to"></a><span data-ttu-id="17111-103">Uygulanan Öğe</span><span class="sxs-lookup"><span data-stu-id="17111-103">Applies To</span></span>

- <span data-ttu-id="17111-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="17111-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>

- <span data-ttu-id="17111-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="17111-105">ASP.NET® Web Forms</span></span>

## <a name="summary"></a><span data-ttu-id="17111-106">Özet</span><span class="sxs-lookup"><span data-stu-id="17111-106">Summary</span></span>

<span data-ttu-id="17111-107">Bu nasıl yapılır, basit bir talep kullanan ASP.NET Web Forms uygulaması oluşturmak ve gelen talepleri dönüştürmek için ayrıntılı adım adım yordamlar sağlar.</span><span class="sxs-lookup"><span data-stu-id="17111-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application and transforming incoming claims.</span></span> <span data-ttu-id="17111-108">Ayrıca, uygulama çalıştırıldığında dönüştürülen taleplerin sunulduğunu doğrulamak üzere uygulamayı test etmek için yönergeler sağlar.</span><span class="sxs-lookup"><span data-stu-id="17111-108">It also provides instructions for how to test the application to verify that transformed claims are presented when the application is run.</span></span>

## <a name="contents"></a><span data-ttu-id="17111-109">İçindekiler</span><span class="sxs-lookup"><span data-stu-id="17111-109">Contents</span></span>

- <span data-ttu-id="17111-110">Amaçlar</span><span class="sxs-lookup"><span data-stu-id="17111-110">Objectives</span></span>

- <span data-ttu-id="17111-111">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="17111-111">Overview</span></span>

- <span data-ttu-id="17111-112">Adımların Özeti</span><span class="sxs-lookup"><span data-stu-id="17111-112">Summary of Steps</span></span>

- <span data-ttu-id="17111-113">1\. adım – basit bir ASP.NET Web Forms uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="17111-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

- <span data-ttu-id="17111-114">2\. Adım: özel bir ClaimsAuthenticationManager kullanarak talep dönüştürmeyi uygulama</span><span class="sxs-lookup"><span data-stu-id="17111-114">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>

- <span data-ttu-id="17111-115">3\. Adım – Çözümünüzü Test Etme</span><span class="sxs-lookup"><span data-stu-id="17111-115">Step 3 – Test Your Solution</span></span>

## <a name="objectives"></a><span data-ttu-id="17111-116">Amaçlar</span><span class="sxs-lookup"><span data-stu-id="17111-116">Objectives</span></span>

- <span data-ttu-id="17111-117">Talep tabanlı kimlik doğrulaması için bir ASP.NET Web Forms uygulaması yapılandırma</span><span class="sxs-lookup"><span data-stu-id="17111-117">Configure an ASP.NET Web Forms application for claims-based authentication</span></span>

- <span data-ttu-id="17111-118">Yönetici rolü talebi ekleyerek gelen talepleri dönüştürme</span><span class="sxs-lookup"><span data-stu-id="17111-118">Transform incoming claims by adding an Administrator role claim</span></span>

- <span data-ttu-id="17111-119">Düzgün çalışıp çalışmadığını görmek için ASP.NET Web Forms uygulamasını test etme</span><span class="sxs-lookup"><span data-stu-id="17111-119">Test the ASP.NET Web Forms application to see if it is working properly</span></span>

## <a name="overview"></a><span data-ttu-id="17111-120">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="17111-120">Overview</span></span>

<span data-ttu-id="17111-121">WIF, kullanıcıların bir bağlı <xref:System.Security.Claims.ClaimsAuthenticationManager> olan taraf (RP) uygulamasına sunulmadan önce talepleri değiştirmesine olanak tanıyan adlı bir sınıfı kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="17111-121">WIF exposes a class named <xref:System.Security.Claims.ClaimsAuthenticationManager> that enables users to modify claims before they are presented to a relying party (RP) application.</span></span> <span data-ttu-id="17111-122">, <xref:System.Security.Claims.ClaimsAuthenticationManager> Kimlik doğrulaması ve temel alınan uygulama kodu arasındaki kaygılara ayrılması yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="17111-122">The <xref:System.Security.Claims.ClaimsAuthenticationManager> is useful for separation of concerns between authentication and the underlying application code.</span></span> <span data-ttu-id="17111-123">Aşağıdaki örnekte, RP tarafından gerekebilecek, gelen <xref:System.Security.Claims.ClaimsPrincipal> taleplere nasıl rol ekleyeceğiniz gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="17111-123">The example below demonstrates how to add a role to the claims in the incoming <xref:System.Security.Claims.ClaimsPrincipal> that may be required by the RP.</span></span>

## <a name="summary-of-steps"></a><span data-ttu-id="17111-124">Adımların Özeti</span><span class="sxs-lookup"><span data-stu-id="17111-124">Summary of Steps</span></span>

- <span data-ttu-id="17111-125">1\. adım – basit bir ASP.NET Web Forms uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="17111-125">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

- <span data-ttu-id="17111-126">2\. Adım: özel bir ClaimsAuthenticationManager kullanarak talep dönüştürmeyi uygulama</span><span class="sxs-lookup"><span data-stu-id="17111-126">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>

- <span data-ttu-id="17111-127">3\. Adım – Çözümünüzü Test Etme</span><span class="sxs-lookup"><span data-stu-id="17111-127">Step 3 – Test Your Solution</span></span>

## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="17111-128">1\. adım – basit bir ASP.NET Web Forms uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="17111-128">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

<span data-ttu-id="17111-129">Bu adımda, yeni bir ASP.NET Web Forms uygulaması oluşturacaksınız.</span><span class="sxs-lookup"><span data-stu-id="17111-129">In this step, you will create a new ASP.NET Web Forms application.</span></span>

#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="17111-130">Basit bir ASP.NET uygulaması oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="17111-130">To create a simple ASP.NET application</span></span>

1. <span data-ttu-id="17111-131">Visual Studio'yu yönetici olarak yükseltilmiş modda başlatın.</span><span class="sxs-lookup"><span data-stu-id="17111-131">Start Visual Studio in elevated mode as administrator.</span></span>

2. <span data-ttu-id="17111-132">Visual Studio 'da **Dosya**' ya, **Yeni**' ye ve ardından **Proje**' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="17111-132">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>

3. <span data-ttu-id="17111-133">**Yeni proje** penceresinde, **ASP.NET Web Forms uygulama**' ya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="17111-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>

4. <span data-ttu-id="17111-134">**Ad**alanına girin `TestApp` ve **Tamam**' a basın.</span><span class="sxs-lookup"><span data-stu-id="17111-134">In **Name**, enter `TestApp` and press **OK**.</span></span>

5. <span data-ttu-id="17111-135">**Çözüm Gezgini**altında **TestApp** projesine sağ tıklayın **ve ardından kimlik ve erişim**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="17111-135">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>

6. <span data-ttu-id="17111-136">**Kimlik ve erişim** penceresi görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="17111-136">The **Identity and Access** window appears.</span></span> <span data-ttu-id="17111-137">**Sağlayıcılar**bölümünde, **yerel geliştirme sts 'Si Ile uygulamanızı test et**' i seçin ve **Uygula**' ya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="17111-137">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>

7. <span data-ttu-id="17111-138">*Default. aspx* dosyasında, varolan biçimlendirmeyi aşağıdaki kodla değiştirin, ardından dosyayı kaydedin:</span><span class="sxs-lookup"><span data-stu-id="17111-138">In the *Default.aspx* file, replace the existing markup with the following, then save the file:</span></span>

    ```aspx-csharp
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>

    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">
          <h3>Your Claims</h3>
        <p>
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">
                <AlternatingRowStyle BackColor="White" />
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />
            </asp:GridView>
        </p>
    </asp:Content>
    ```

8. <span data-ttu-id="17111-139">*Default.aspx.cs*adlı arka plan kod dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="17111-139">Open the code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="17111-140">Mevcut kodu aşağıdaki kodla değiştirin, ardından dosyayı kaydedin:</span><span class="sxs-lookup"><span data-stu-id="17111-140">Replace the existing code with the following, then save the file:</span></span>

    ```csharp
    using System;
    using System.Web.UI;
    using System.Security.Claims;

    namespace TestApp
    {
        public partial class _Default : Page
        {
            protected void Page_Load(object sender, EventArgs e)
            {
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;
                this.ClaimsGridView.DataBind();
            }
        }
    }
    ```

## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="17111-141">2\. Adım: özel bir ClaimsAuthenticationManager kullanarak talep dönüştürmeyi uygulama</span><span class="sxs-lookup"><span data-stu-id="17111-141">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>

<span data-ttu-id="17111-142">Bu adımda, gelen sorumluya bir yönetici rolü eklemek <xref:System.Security.Claims.ClaimsAuthenticationManager> için sınıfındaki varsayılan işlevselliği geçersiz kılacaksınız.</span><span class="sxs-lookup"><span data-stu-id="17111-142">In this step you will override default functionality in the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to add an Administrator role to the incoming Principal.</span></span>

#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="17111-143">Özel bir ClaimsAuthenticationManager kullanarak talep dönüşümünü uygulamak için</span><span class="sxs-lookup"><span data-stu-id="17111-143">To implement claims transformation using a custom ClaimsAuthenticationManager</span></span>

1. <span data-ttu-id="17111-144">Visual Studio 'da çözüme sağ tıklayın, **Ekle**' ye tıklayın ve ardından **Yeni proje**' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="17111-144">In Visual Studio, right-click the on the solution, click **Add**, and then click **New Project**.</span></span>

2. <span data-ttu-id="17111-145">**Yeni Proje Ekle** penceresinde,  **C# görsel** şablonlar listesinden **sınıf kitaplığı** ' nı seçin, yazın `ClaimsTransformation`ve ardından **Tamam**' a basın.</span><span class="sxs-lookup"><span data-stu-id="17111-145">In the **Add New Project** window, select **Class Library** from the **Visual C#** templates list, enter `ClaimsTransformation`, and then press **OK**.</span></span> <span data-ttu-id="17111-146">Yeni proje, çözüm klasörünüzde oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="17111-146">The new project will be created in your solution folder.</span></span>

3. <span data-ttu-id="17111-147">**Claimstrans,** proje kapsamındaki **Başvurular** ' a sağ tıklayın ve ardından **Başvuru Ekle**' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="17111-147">Right-click on **References** under the **ClaimsTransformation** project, and then click **Add Reference**.</span></span>

4. <span data-ttu-id="17111-148">**Başvuru Yöneticisi** penceresinde **System. IdentityModel**' i seçin ve ardından **Tamam**' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="17111-148">In the **Reference Manager** window, select **System.IdentityModel**, and then click **OK**.</span></span>

5. <span data-ttu-id="17111-149">**Class1.cs**açın veya yoksa, **Claimstransders**' e sağ tıklayın, **Ekle**' ye tıklayın, sonra **sınıf..** . öğesine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="17111-149">Open **Class1.cs**, or if it doesn’t exist, right-click **ClaimsTransformation**, click **Add**, then click **Class…**</span></span>

6. <span data-ttu-id="17111-150">Aşağıdaki using yönergelerini kod dosyasına ekleyin:</span><span class="sxs-lookup"><span data-stu-id="17111-150">Add the following using directives to the code file:</span></span>

    ```csharp
    using System.Security.Claims;
    using System.Security.Principal;
    ```

7. <span data-ttu-id="17111-151">Aşağıdaki sınıf ve yöntemi kod dosyasına ekleyin.</span><span class="sxs-lookup"><span data-stu-id="17111-151">Add the following class and method in the code file.</span></span>

    > [!WARNING]
    > <span data-ttu-id="17111-152">Aşağıdaki kod yalnızca tanıtım amaçlıdır. üretim kodunda amaçlanan izinlerinizi doğruladığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="17111-152">The following code is for demonstration purposes only; make sure that you verify your intended permissions in production code.</span></span>

    ```csharp
    public class ClaimsTransformationModule : ClaimsAuthenticationManager
    {
        public override ClaimsPrincipal Authenticate(string resourceName, ClaimsPrincipal incomingPrincipal)
        {
            if (incomingPrincipal != null && incomingPrincipal.Identity.IsAuthenticated == true)
            {
               ((ClaimsIdentity)incomingPrincipal.Identity).AddClaim(new Claim(ClaimTypes.Role, "Admin"));
            }

            return incomingPrincipal;
        }
    }
    ```

8. <span data-ttu-id="17111-153">Dosyayı kaydedin ve **Claimstransoluþturup** projesini derleyin.</span><span class="sxs-lookup"><span data-stu-id="17111-153">Save the file and build the **ClaimsTransformation** project.</span></span>

9. <span data-ttu-id="17111-154">**TestApp** ASP.net projenizde, başvurular ' a sağ tıklayın ve ardından **Başvuru Ekle**' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="17111-154">In your **TestApp** ASP.NET project, right-click on References, and then click **Add Reference**.</span></span>

10. <span data-ttu-id="17111-155">**Başvuru Yöneticisi** penceresinde, sol menüden **çözüm** ' i seçin, doldurulan seçeneklerden **claimstranssize** ' yı seçin ve ardından **Tamam**' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="17111-155">In the **Reference Manager** window, select **Solution** from the left menu, select **ClaimsTransformation** from the populated options, and then click **OK**.</span></span>

11. <span data-ttu-id="17111-156">Kök **Web. config** dosyasında  **\<System. IdentityModel >** girdisine gidin.</span><span class="sxs-lookup"><span data-stu-id="17111-156">In the root **Web.config** file, navigate to the **\<system.identityModel>** entry.</span></span> <span data-ttu-id="17111-157">IdentityConfiguration > öğeleri içinde aşağıdaki satırı ekleyin ve dosyayı kaydedin:  **\<**</span><span class="sxs-lookup"><span data-stu-id="17111-157">Within the **\<identityConfiguration>** elements, add the following line and save the file:</span></span>

    ```xml
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />
    ```

## <a name="step-3--test-your-solution"></a><span data-ttu-id="17111-158">3\. Adım – Çözümünüzü Test Etme</span><span class="sxs-lookup"><span data-stu-id="17111-158">Step 3 – Test Your Solution</span></span>

<span data-ttu-id="17111-159">Bu adımda, ASP.NET Web Forms uygulamanızı test edecek ve Kullanıcı form kimlik doğrulamasıyla oturum açtığında taleplerin sunulduğunu doğrulayacaksınız.</span><span class="sxs-lookup"><span data-stu-id="17111-159">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>

#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="17111-160">Forms kimlik doğrulaması kullanarak ASP.NET Web Forms uygulamanızı talepler için test etme</span><span class="sxs-lookup"><span data-stu-id="17111-160">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>

1. <span data-ttu-id="17111-161">Uygulamayı derlemek ve çalıştırmak için **F5** tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="17111-161">Press **F5** to build and run the application.</span></span> <span data-ttu-id="17111-162">*Default. aspx*ile sunulmalısınız.</span><span class="sxs-lookup"><span data-stu-id="17111-162">You should be presented with *Default.aspx*.</span></span>

2. <span data-ttu-id="17111-163">*Default. aspx* sayfasında, hesap hakkındaki **veren**, **OriginalIssuer**, **Type**, **Value**ve **ValueType** talep bilgilerini içeren **talep** başlığının altında bir tablo görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="17111-163">On the *Default.aspx* page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span> <span data-ttu-id="17111-164">Son satır aşağıdaki şekilde sunulmalıdır:</span><span class="sxs-lookup"><span data-stu-id="17111-164">The last row should be presented in the following way:</span></span>

    ||||||
    |-|-|-|-|-|
    |<span data-ttu-id="17111-165">YEREL YETKILI</span><span class="sxs-lookup"><span data-stu-id="17111-165">LOCAL AUTHORITY</span></span>|<span data-ttu-id="17111-166">YEREL YETKILI</span><span class="sxs-lookup"><span data-stu-id="17111-166">LOCAL AUTHORITY</span></span>|`http://schemas.microsoft.com/ws/2008/06/identity/claims/role`|<span data-ttu-id="17111-167">Yönetici</span><span class="sxs-lookup"><span data-stu-id="17111-167">Admin</span></span>|<https://www.w3.org/2001/XMLSchema#string>|
