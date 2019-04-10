---
title: 'Nasıl yapılır: IIS Tarafından Barındırılan Bir WCF Hizmetini SSL ile Yapılandırma'
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 336c3800fc033cc12bd9c3fe168ae219b72cab91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214124"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="647ed-102">Nasıl yapılır: IIS Tarafından Barındırılan Bir WCF Hizmetini SSL ile Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="647ed-102">How to: Configure an IIS-hosted WCF service with SSL</span></span>
<span data-ttu-id="647ed-103">Bu konu, HTTP aktarım güvenliği kullanılacak bir IIS barındırılan WCF hizmeti kurmak açıklar.</span><span class="sxs-lookup"><span data-stu-id="647ed-103">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="647ed-104">HTTP aktarım güvenliği bir SSL sertifikası, IIS ile kayıtlı olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="647ed-104">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="647ed-105">Bir SSL sertifikası yoksa, IIS bir test sertifikası oluşturmak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="647ed-105">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="647ed-106">Sonraki web sitesine bir SSL bağlaması ekleyin ve web sitesinin kimlik doğrulaması özelliklerini yapılandırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="647ed-106">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="647ed-107">Son olarak, WCF hizmetini HTTPS kullanacak şekilde yapılandırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="647ed-107">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="647ed-108">Otomatik olarak imzalanan sertifika oluşturma</span><span class="sxs-lookup"><span data-stu-id="647ed-108">Creating a Self-Signed Certificate</span></span>  
  
1.  <span data-ttu-id="647ed-109">Internet Information Services Manager (inetmgr.exe) açın ve sol taraftaki ağaç görünümü'nde, bilgisayar adını seçin.</span><span class="sxs-lookup"><span data-stu-id="647ed-109">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="647ed-110">Ekranın sağ tarafında sunucu sertifikası seç</span><span class="sxs-lookup"><span data-stu-id="647ed-110">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="647ed-111">![IIS Manager giriş ekranı](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="647ed-111">![IIS Manager Home Screen](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2.  <span data-ttu-id="647ed-112">Sunucu sertifikaları pencerede **otomatik olarak imzalanan sertifika oluştur...**</span><span class="sxs-lookup"><span data-stu-id="647ed-112">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="647ed-113">bağlantı.</span><span class="sxs-lookup"><span data-stu-id="647ed-113">Link.</span></span>  
  
     <span data-ttu-id="647ed-114">![Bir kendi kendini oluşturma&#45;IIS sertifikayla imzalanan](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="647ed-114">![Creating a self&#45;signed certificate with IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3.  <span data-ttu-id="647ed-115">Otomatik olarak imzalanan sertifika için bir kolay ad girin ve tıklayın **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="647ed-115">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="647ed-116">![Kendi kendine oluşturmak&#45;imzalı sertifika iletişim kutusu](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="647ed-116">![Create Self&#45;Signed Certificate Dialog](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="647ed-117">Yeni oluşturulan kendinden imzalı bir sertifika ayrıntılarını artık gösterilen **sunucu sertifikaları** penceresi.</span><span class="sxs-lookup"><span data-stu-id="647ed-117">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="647ed-118">![Sunucu sertifikası penceresi](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="647ed-118">![Server Certificate Window](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="647ed-119">Oluşturulan sertifika, güvenilen kök sertifika yetkilileri deposunda yüklü depolayın.</span><span class="sxs-lookup"><span data-stu-id="647ed-119">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="647ed-120">SSL bağlaması Ekle</span><span class="sxs-lookup"><span data-stu-id="647ed-120">Add SSL Binding</span></span>  
  
1.  <span data-ttu-id="647ed-121">Hala Internet Bilgi Hizmetleri Yöneticisi'nde genişletin **siteleri** klasörünü ve ardından **varsayılan Web sitesi** ekranın sol tarafındaki ağaç görünümünde klasörü.</span><span class="sxs-lookup"><span data-stu-id="647ed-121">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2.  <span data-ttu-id="647ed-122">Tıklayın **bağlamaları...**</span><span class="sxs-lookup"><span data-stu-id="647ed-122">Click the **Bindings….**</span></span> <span data-ttu-id="647ed-123">Bağlantısını **eylemleri** pencerenin sağ üst taraftaki bölümünde bölümünde.</span><span class="sxs-lookup"><span data-stu-id="647ed-123">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="647ed-124">![Bir SSL bağlaması ekleniyor](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="647ed-124">![Adding an SSL binding](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3.  <span data-ttu-id="647ed-125">Site bağlamaları pencerede **Ekle** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="647ed-125">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="647ed-126">![Site bağlamaları iletişim](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="647ed-126">![Site Bindings Dialog](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4.  <span data-ttu-id="647ed-127">İçinde **Site bağlaması Ekle** türü ve kolay adı, tam otomatik olarak imzalanan sertifika için select https iletişim kutusunda, oluşturulan.</span><span class="sxs-lookup"><span data-stu-id="647ed-127">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="647ed-128">![Site bağlama örnek](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="647ed-128">![Site binding example](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="647ed-129">SSL için sanal dizin Yapılandır</span><span class="sxs-lookup"><span data-stu-id="647ed-129">Configure Virtual Directory for SSL</span></span>  
  
1.  <span data-ttu-id="647ed-130">Hala Internet Bilgi Hizmetleri Yöneticisi'nde güvenli WCF hizmetinizi içeren sanal dizini seçin.</span><span class="sxs-lookup"><span data-stu-id="647ed-130">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2.  <span data-ttu-id="647ed-131">Pencerenin Orta bölmede seçin **SSL ayarları** IIS bölümünde.</span><span class="sxs-lookup"><span data-stu-id="647ed-131">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="647ed-132">![Sanal dizin için SSL ayarları](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="647ed-132">![SSL Settings for virtual directory](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3.  <span data-ttu-id="647ed-133">SSL ayarları bölmesinde seçin **SSL iste** onay kutusunu tıklatıp **Uygula** bağlantısını **eylemleri** ekranın sağ tarafındaki bölümü.</span><span class="sxs-lookup"><span data-stu-id="647ed-133">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="647ed-134">![Sanal dizin SSL ayarları](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="647ed-134">![Virtual directory SSL settings](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="647ed-135">HTTP aktarım güvenliği için WCF hizmetini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="647ed-135">Configure WCF Service for HTTP Transport Security</span></span>  
  
1.  <span data-ttu-id="647ed-136">WCF'de hizmetin web.config aşağıdaki XML'de gösterildiği aktarım güvenliği kullanılacak HTTP bağlama yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="647ed-136">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
    ```xml  
    <bindings>  
          <basicHttpBinding>  
            <binding name="secureHttpBinding">  
              <security mode="Transport">  
                <transport clientCredentialType="None"/>  
              </security>  
            </binding>  
          </basicHttpBinding>  
    </bindings>  
    ```  
  
2.  <span data-ttu-id="647ed-137">Aşağıdaki XML dosyasında gösterildiği gibi hizmet ve hizmet uç noktası belirtin.</span><span class="sxs-lookup"><span data-stu-id="647ed-137">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
    ```xml  
    <services>  
          <service name="MySecureWCFService.Service1">  
            <endpoint address=""  
                      binding="basicHttpBinding"  
                      bindingConfiguration="secureHttpBinding"  
                      contract="MySecureWCFService.IService1"/>  
  
            <endpoint address="mex"  
                      binding="mexHttpsBinding"  
                      contract="IMetadataExchange" />  
          </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="647ed-138">Örnek</span><span class="sxs-lookup"><span data-stu-id="647ed-138">Example</span></span>  
 <span data-ttu-id="647ed-139">HTTP aktarım güvenliği kullanarak bir WCF hizmeti için web.config dosyasının tam bir örnek verilmiştir</span><span class="sxs-lookup"><span data-stu-id="647ed-139">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <services>  
      <service name="MySecureWCFService.Service1">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="secureHttpBinding"  
                  contract="MySecureWCFService.IService1"/>  
  
        <endpoint address="mex"  
                  binding="mexHttpsBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="secureHttpBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <!-- To avoid disclosing metadata information, set the value below to false and remove the metadata endpoint above before deployment -->  
          <serviceMetadata httpsGetEnabled="true"/>  
          <!-- To receive exception details in faults for debugging purposes, set the value below to true.  Set to false before deployment to avoid disclosing exception information -->  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
  </system.serviceModel>  
  <system.webServer>  
    <modules runAllManagedModulesForAllRequests="true"/>  
  </system.webServer>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="647ed-140">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="647ed-140">See also</span></span>

- [<span data-ttu-id="647ed-141">Internet Information Services'te Barındırma</span><span class="sxs-lookup"><span data-stu-id="647ed-141">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [<span data-ttu-id="647ed-142">Internet Information Service Barındırma Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="647ed-142">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
- [<span data-ttu-id="647ed-143">Internet Information Services Barındırma En İyi Uygulamaları</span><span class="sxs-lookup"><span data-stu-id="647ed-143">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [<span data-ttu-id="647ed-144">Satır İçi Kod Kullanarak IIS Barındırma</span><span class="sxs-lookup"><span data-stu-id="647ed-144">IIS Hosting Using Inline Code</span></span>](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)
