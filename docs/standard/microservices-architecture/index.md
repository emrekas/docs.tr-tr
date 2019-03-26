---
title: .NET mikro Hizmetleri. Kapsayıcılı .NET uygulamaları mimarisi
description: 'Kapsayıcılı .NET uygulamaları için .NET mikro hizmet mimarisi | Mikro hizmetler, modüler ve bağımsız bir şekilde dağıtılabilen hizmetleridir. Docker kapsayıcıları (için Linux ve Windows), dağıtım ve bir hizmeti ve bağımlılıklarını ardından yalıtılmış bir ortamda çalıştırılır tek bir birim halinde paketleme tarafından test basitleştirin.'
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
---
# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="9b0af-105">.NET mikro Hizmetleri: Kapsayıcılı .NET uygulamaları mimarisi</span><span class="sxs-lookup"><span data-stu-id="9b0af-105">.NET Microservices: Architecture for Containerized .NET Applications</span></span>

![Kitap kapsar](./media/cover-small.png)

<span data-ttu-id="9b0af-107">**Sürüm v2.2.00** - ASP.NET core'a 2.2 güncelleştirildi</span><span class="sxs-lookup"><span data-stu-id="9b0af-107">**EDITION v2.2.00** - Updated to ASP.NET Core 2.2</span></span>

<span data-ttu-id="9b0af-108">Mikro hizmet tabanlı uygulamaları geliştirmek ve bunları yönetmek için giriş niteliğindeki bu kılavuzda, kapsayıcıları kullanma.</span><span class="sxs-lookup"><span data-stu-id="9b0af-108">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="9b0af-109">Mimari Tasarım açıklar ve .NET Core ve Docker kapsayıcılarını kullanarak uygulama yaklaşıyor.</span><span class="sxs-lookup"><span data-stu-id="9b0af-109">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> 

<span data-ttu-id="9b0af-110">Başlama daha kolay hale getirmek için bir kapsayıcıya alınmış başvuru ve keşfedebilirsiniz mikro hizmet tabanlı uygulama Kılavuzu odaklanır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-110">To make it easier to get started, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="9b0af-111">Başvuru uygulama kullanılabilir [hizmetine](https://github.com/dotnet-architecture/eShopOnContainers) GitHub deposu.</span><span class="sxs-lookup"><span data-stu-id="9b0af-111">The reference application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

## <a name="action-links"></a><span data-ttu-id="9b0af-112">Eylem bağlantıları</span><span class="sxs-lookup"><span data-stu-id="9b0af-112">Action links</span></span>

* <span data-ttu-id="9b0af-113">Tercih ettiğiniz biçimdeki bu e-kitabı indirin: | [PDF](https://aka.ms/microservicesebook) | [MOBI](https://www.microsoft.com/net/download/thank-you/microservices-architecture-ebook-mobi) | [EPUB](https://www.microsoft.com/net/download/thank-you/microservices-architecture-ebook-epub) |</span><span class="sxs-lookup"><span data-stu-id="9b0af-113">Download this eBook in your format of choice: | [PDF](https://aka.ms/microservicesebook) | [MOBI](https://www.microsoft.com/net/download/thank-you/microservices-architecture-ebook-mobi) | [EPUB](https://www.microsoft.com/net/download/thank-you/microservices-architecture-ebook-epub) |</span></span>

* <span data-ttu-id="9b0af-114">Kopyalama/çatal başvurusu [hizmetine github'da](https://github.com/dotnet-architecture/eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="9b0af-114">Clone/Fork the reference application [eShopOnContainers on GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span></span>
 
* <span data-ttu-id="9b0af-115">İzleme [tanıtım videosunu Channel 9](https://aka.ms/microservices-video)</span><span class="sxs-lookup"><span data-stu-id="9b0af-115">Watch the [introductory video on Channel 9](https://aka.ms/microservices-video)</span></span>

* <span data-ttu-id="9b0af-116">Tanıyalım [mikro hizmet mimarisi](https://aka.ms/MicroservicesArchitecture) hemen</span><span class="sxs-lookup"><span data-stu-id="9b0af-116">Get to know the [Microservices Architecture](https://aka.ms/MicroservicesArchitecture) right away</span></span>

## <a name="introduction"></a><span data-ttu-id="9b0af-117">Giriş</span><span class="sxs-lookup"><span data-stu-id="9b0af-117">Introduction</span></span>

<span data-ttu-id="9b0af-118">Kuruluşların giderek daha fazla maliyet tasarrufu taahhüdünü gerçekleştirmeye dağıtım sorunlarını giderme ve kapsayıcıları kullanarak DevOps ve üretim işlemleri iyileştirme.</span><span class="sxs-lookup"><span data-stu-id="9b0af-118">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="9b0af-119">Microsoft Windows ve Linux kapsayıcı yenilikten Azure Container Service ve Azure Service Fabric gibi ürünleri oluşturarak ve Docker, Mesosphere ve Kubernetes gibi sektör öncüleri ile işbirliği yapan mıt'li serbest.</span><span class="sxs-lookup"><span data-stu-id="9b0af-119">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Container Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="9b0af-120">Bu ürünler, bulut hızı ve ölçeği, hangi uygulamaları derlemeye ve dağıtmaya şirketlerin yardımcı kapsayıcı çözümler sunmak kendi seçtiğiniz platform veya araçları.</span><span class="sxs-lookup"><span data-stu-id="9b0af-120">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="9b0af-121">Docker kapsayıcı sektördeki en önemli Windows ve Linux eko satıcılar tarafından desteklenen, pratikte bir standart hale gelmektedir.</span><span class="sxs-lookup"><span data-stu-id="9b0af-121">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="9b0af-122">(Microsoft, Docker'ı destekleyen temel bulut satıcıları biridir.) Gelecekte, Docker büyük olasılıkla bulutta veya şirket içinde herhangi bir veri merkezinde bulunabilen olacaktır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-122">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="9b0af-123">Ayrıca, [mikro Hizmetler](https://martinfowler.com/articles/microservices.html) mimarisi Gelişmekte olan dağıtılmış görev açısından kritik uygulamalar için önemli bir yaklaşım.</span><span class="sxs-lookup"><span data-stu-id="9b0af-123">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="9b0af-124">Mikro hizmet tabanlı bir mimaride, uygulama koleksiyonu, test edilmiş, dağıtılan ve tutulan bağımsız olarak geliştirilebilir hizmetleri üzerinde oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="9b0af-124">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="9b0af-125">Bu kılavuz hakkında</span><span class="sxs-lookup"><span data-stu-id="9b0af-125">About this guide</span></span>

<span data-ttu-id="9b0af-126">Mikro hizmet tabanlı uygulamaları geliştirmek ve bunları yönetmek için giriş niteliğindeki bu kılavuzda, kapsayıcıları kullanma.</span><span class="sxs-lookup"><span data-stu-id="9b0af-126">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="9b0af-127">Mimari Tasarım açıklar ve .NET Core ve Docker kapsayıcılarını kullanarak uygulama yaklaşıyor.</span><span class="sxs-lookup"><span data-stu-id="9b0af-127">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> <span data-ttu-id="9b0af-128">Kapsayıcılar ve mikro hizmetler kullanmaya başlama daha kolay hale getirmek için bir kapsayıcıya alınmış başvuru ve keşfedebilirsiniz mikro hizmet tabanlı uygulama Kılavuzu odaklanır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-128">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="9b0af-129">Örnek uygulamayı kullanılabilir [hizmetine](https://github.com/dotnet-architecture/eShopOnContainers) GitHub deposu.</span><span class="sxs-lookup"><span data-stu-id="9b0af-129">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="9b0af-130">Bu kılavuz iki teknoloji odaklanan temel geliştirme ve öncelikli olarak geliştirme ortamı düzeyde mimari rehberlik sağlar: Docker ve .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9b0af-130">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET Core.</span></span> <span data-ttu-id="9b0af-131">Bizim engellemekse altyapıya üretim ortamınızın (Bulut veya şirket içi) odaklanmadan uygulama tasarımınızı düşünürken, bu kılavuzu okumadan ' dir.</span><span class="sxs-lookup"><span data-stu-id="9b0af-131">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="9b0af-132">Üretime hazır uygulamalar oluşturduğunuzda, altyapı konusunda kararlar daha sonra yapar.</span><span class="sxs-lookup"><span data-stu-id="9b0af-132">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="9b0af-133">Bu nedenle, bu kılavuz dilden bağımsız ve daha fazla geliştirme ortamı-merkezli altyapı olması amaçlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-133">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="9b0af-134">Bu kılavuzda eğitim sonra Microsoft Azure üzerinde üretime hazır mikro hizmetler hakkında bilgi edinmek için sonraki adımınız olacaktır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-134">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="version"></a><span data-ttu-id="9b0af-135">Sürüm</span><span class="sxs-lookup"><span data-stu-id="9b0af-135">Version</span></span>

<span data-ttu-id="9b0af-136">Bu kılavuzda kaplayacak şekilde yeniden düzenlendi **.NET Core 2.2** yanı sıra birçok ek güncelleştirme sürümü ilgili aynı "(yani. wave" teknolojileri</span><span class="sxs-lookup"><span data-stu-id="9b0af-136">This guide has been revised to cover **.NET Core 2.2** version plus many additional updates related to the same “wave” of technologies (that is.</span></span> <span data-ttu-id="9b0af-137">Azure ve ek 3. taraf teknolojileri) ile .NET Core 2.2 zamanlı durdurulmasıyla.</span><span class="sxs-lookup"><span data-stu-id="9b0af-137">Azure and additional 3rd party technologies) coinciding in time with .NET Core 2.2.</span></span> <span data-ttu-id="9b0af-138">İşte bu kitap sürümü de sürümüne güncelleştirildi **2.2**.</span><span class="sxs-lookup"><span data-stu-id="9b0af-138">That’s why the book version has also been updated to version **2.2**.</span></span> 

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="9b0af-139">Ne bu kılavuzda ele alınmamaktadır</span><span class="sxs-lookup"><span data-stu-id="9b0af-139">What this guide does not cover</span></span>

<span data-ttu-id="9b0af-140">Bu kılavuz, uygulama yaşam döngüsü üzerinde DevOps, CI/CD işlem hatları, odaklı değildir veya takım iş.</span><span class="sxs-lookup"><span data-stu-id="9b0af-140">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="9b0af-141">Tamamlayıcı Kılavuzu [kapsayıcılı Docker uygulaması yaşam döngüsü Microsoft Platformu ve araçları ile](https://aka.ms/dockerlifecycleebook) Bu konu üzerinde odaklanır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-141">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="9b0af-142">Geçerli Kılavuz ayrıca uygulama ayrıntıları gibi belirli düzenleyicileri bilgi Azure altyapı sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="9b0af-142">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9b0af-143">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="9b0af-143">Additional resources</span></span>

-   <span data-ttu-id="9b0af-144">**Docker uygulaması yaşam döngüsü Microsoft Platformu ve araçları ile kapsayıcılı hale** (indirilebilir e-kitap)</span><span class="sxs-lookup"><span data-stu-id="9b0af-144">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book)</span></span>  
    [https://aka.ms/dockerlifecycleebook](https://aka.ms/dockerlifecycleebook)

## <a name="who-should-use-this-guide"></a><span data-ttu-id="9b0af-145">Bu kılavuzda kullanan</span><span class="sxs-lookup"><span data-stu-id="9b0af-145">Who should use this guide</span></span>

<span data-ttu-id="9b0af-146">Geliştiriciler ve Docker tabanlı uygulama geliştirmeyi ve mikro hizmet tabanlı mimari için yeni olan çözüm mimarları için bu kılavuzu yazdığımız.</span><span class="sxs-lookup"><span data-stu-id="9b0af-146">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="9b0af-147">Mimari hakkında bilgi edinmek isterseniz tasarlamanıza ve kavram kanıtı uygulamalarını (.NET Core odaklanmaktadır ile) Microsoft geliştirme teknolojileri ile uygulamak için bu kılavuzda sunulmaktadır ve Docker kapsayıcıları ile.</span><span class="sxs-lookup"><span data-stu-id="9b0af-147">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET Core) and with Docker containers.</span></span>

<span data-ttu-id="9b0af-148">Ayrıca bu kılavuzun yararlı bir mimari isteyen bir kuruluş Mimarı'gibi bir teknik karar mercii olan ve teknoloji genel bakış, önce karar verirseniz dağıtılmış uygulamalar yeni ve modern seçmek için hangi yaklaşımı hakkında bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b0af-148">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="9b0af-149">Bu kılavuz nasıl kullanılır?</span><span class="sxs-lookup"><span data-stu-id="9b0af-149">How to use this guide</span></span>

<span data-ttu-id="9b0af-150">Bu kılavuzun ilk bölümü Docker kapsayıcıları sunar, .NET Core ve geliştirme framework .NET Framework arasında seçim anlatılmaktadır ve mikro hizmetler için genel bir bakış sağlar.</span><span class="sxs-lookup"><span data-stu-id="9b0af-150">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="9b0af-151">Bu içerik mimarları ve genel bir bakış istiyor ancak kod uygulaması ayrıntılara odaklanmak gerekmez teknik karar verenler içindir.</span><span class="sxs-lookup"><span data-stu-id="9b0af-151">This content is for architects and technical decision makers who want an overview but don't need to focus on code implementation details.</span></span>

<span data-ttu-id="9b0af-152">İle başlayan Kılavuzu ikinci bölümü [geliştirme süreci için Docker tabanlı uygulamalar](./docker-application-development-process/index.md) bölümü.</span><span class="sxs-lookup"><span data-stu-id="9b0af-152">The second part of the guide starts with the [Development process for Docker based applications](./docker-application-development-process/index.md) section.</span></span> <span data-ttu-id="9b0af-153">.NET Core ve Docker kullanan uygulamalar, uygulama geliştirme ve mikro hizmet desenleri odaklanır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-153">It focuses on development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="9b0af-154">Bu bölümde, geliştiricilere ve mimarlara desenleri ve uygulama ayrıntılarını ve kod üzerinde odaklanmak isteyen çoğu ilgi olacaktır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-154">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="9b0af-155">Mikro hizmet ve kapsayıcı tabanlı başvuru uygulaması ilgili: hizmetine</span><span class="sxs-lookup"><span data-stu-id="9b0af-155">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="9b0af-156">.NET Core ve Docker kapsayıcılarını kullanarak dağıtılması için tasarlanmış bir mikro hizmetler için açık kaynak başvuru uygulama hizmetine uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-156">The eShopOnContainers application is an open-source reference app for .NET Core and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="9b0af-157">Uygulama birden çok e-store UI ön uçlar (bir MVC Web uygulaması, Web SPA ve yerel bir mobil uygulama) dahil olmak üzere birden çok alt oluşur.</span><span class="sxs-lookup"><span data-stu-id="9b0af-157">The application consists of multiple subsystems, including several e-store UI front ends (a Web MVC app, a Web SPA, and a native mobile app).</span></span> <span data-ttu-id="9b0af-158">Ayrıca arka uç mikro hizmetler ve kapsayıcılar için gerekli tüm sunucu tarafı işlemleri içerir.</span><span class="sxs-lookup"><span data-stu-id="9b0af-158">It also includes the back-end microservices and containers for all required server-side operations.</span></span> 

<span data-ttu-id="9b0af-159">Mimari desenleri göstermek için uygulama amacı olan.</span><span class="sxs-lookup"><span data-stu-id="9b0af-159">The purpose of the application is to showcase architectural patterns.</span></span> <span data-ttu-id="9b0af-160">**BT değil bir ÜRETİME hazır şablonu** gerçek uygulamaları başlatmak için.</span><span class="sxs-lookup"><span data-stu-id="9b0af-160">**IT IS NOT A PRODUCTION-READY TEMPLATE** to start real-world applications.</span></span> <span data-ttu-id="9b0af-161">Ayrıca bunlar gösterildiği gibi yeni ilginç olabilecek teknolojileri test etmek için kullanılır, uygulama bir kalıcı beta durumda aynıdır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-161">In fact, the application is in a permanent beta state, as it’s also used to test new potentially interesting technologies as they show up.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="9b0af-162">Bize geri bildirim gönderin!</span><span class="sxs-lookup"><span data-stu-id="9b0af-162">Send us your feedback!</span></span>

<span data-ttu-id="9b0af-163">Kapsayıcılı uygulamaları ve .NET içinde mikro hizmetler mimarisi anlamanıza yardımcı olması için bu kılavuzu yazdığımız.</span><span class="sxs-lookup"><span data-stu-id="9b0af-163">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="9b0af-164">Bildirimleriniz bizim için değerli şekilde Kılavuzu ve ilgili başvuru uygulaması, gelişen!</span><span class="sxs-lookup"><span data-stu-id="9b0af-164">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="9b0af-165">Bu kılavuz nasıl geliştirilebilir hakkında açıklamalar varsa, Lütfen bunları gönderin:</span><span class="sxs-lookup"><span data-stu-id="9b0af-165">If you have comments about how this guide can be improved, please send them to:</span></span>

[dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com)

## <a name="credits"></a><span data-ttu-id="9b0af-166">Jenerik</span><span class="sxs-lookup"><span data-stu-id="9b0af-166">Credits</span></span>

<span data-ttu-id="9b0af-167">Ortak yazarlar:</span><span class="sxs-lookup"><span data-stu-id="9b0af-167">Co-Authors:</span></span>

> <span data-ttu-id="9b0af-168">**Cesar de la Torre**, üst düzey PM, .NET ürün ekibi, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="9b0af-168">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="9b0af-169">**Fatura Wagner**, üst düzey içerik geliştirici, C + E, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="9b0af-169">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="9b0af-170">**Mike Rousos**, baş yazılım mühendisi, Devdiv'e CAT ekibi, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b0af-170">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="9b0af-171">Düzenleyiciler:</span><span class="sxs-lookup"><span data-stu-id="9b0af-171">Editors:</span></span>

> <span data-ttu-id="9b0af-172">**Mike Pope**</span><span class="sxs-lookup"><span data-stu-id="9b0af-172">**Mike Pope**</span></span>
>
> <span data-ttu-id="9b0af-173">**Steve Hoag**</span><span class="sxs-lookup"><span data-stu-id="9b0af-173">**Steve Hoag**</span></span>

<span data-ttu-id="9b0af-174">Katılımcılar ve gözden geçirenler:</span><span class="sxs-lookup"><span data-stu-id="9b0af-174">Participants and reviewers:</span></span>

> <span data-ttu-id="9b0af-175">**Jeffrey Richter**, iş ortağı yazılım Mühendisliği, Azure ekibi, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b0af-175">**Jeffrey Richter**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="9b0af-176">**Jimmy Bogard**, Headspring, baş Mimar</span><span class="sxs-lookup"><span data-stu-id="9b0af-176">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="9b0af-177">**UDI Dahan**, kurucu ve CEO, belirli yazılım</span><span class="sxs-lookup"><span data-stu-id="9b0af-177">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="9b0af-178">**Jimmy Nilsson**, ortak kurucu ve CEO, Factor10</span><span class="sxs-lookup"><span data-stu-id="9b0af-178">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="9b0af-179">**Glenn Condron**, üst düzey Program Yöneticisi, ASP.NET takımı</span><span class="sxs-lookup"><span data-stu-id="9b0af-179">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="9b0af-180">**İşareti Fussell**, asıl PM lideri, Microsoft Azure Service Fabric ekibi</span><span class="sxs-lookup"><span data-stu-id="9b0af-180">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="9b0af-181">**Diego Vega**, PM lideri, Entity Framework takım, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b0af-181">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="9b0af-182">**Barry Dorrans**, üst düzey güvenlik Program Yöneticisi</span><span class="sxs-lookup"><span data-stu-id="9b0af-182">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="9b0af-183">**Rowan Miller**, üst düzey Program Yöneticisi, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b0af-183">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="9b0af-184">**Ankit Asthana**, baş PM Yöneticisi, Microsoft .NET ekibi</span><span class="sxs-lookup"><span data-stu-id="9b0af-184">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="9b0af-185">**Scott Hunter**, .NET ekibi, Microsoft iş ortağı Direktörü PM</span><span class="sxs-lookup"><span data-stu-id="9b0af-185">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="9b0af-186">**Nish Anil**, üst düzey Program Yöneticisi, Microsoft .NET ekibi</span><span class="sxs-lookup"><span data-stu-id="9b0af-186">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="9b0af-187">**Dylan Reisenberger**, Mimar ve Polly Bykov'un geliştirme</span><span class="sxs-lookup"><span data-stu-id="9b0af-187">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="9b0af-188">**Steve Smith**, yazılım mesleğini geliştirme & ASPSmith Ltd., eğitmen</span><span class="sxs-lookup"><span data-stu-id="9b0af-188">**Steve Smith**, Software Craftsman & Trainer at ASPSmith Ltd.</span></span>
>
> <span data-ttu-id="9b0af-189">**Ian Cooper**, kodlama mimari en parlak</span><span class="sxs-lookup"><span data-stu-id="9b0af-189">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="9b0af-190">**Unai Zorrilla**, mimari ve geliştirme Bykov'un düz kavramları</span><span class="sxs-lookup"><span data-stu-id="9b0af-190">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="9b0af-191">**Eduard Tomas**, geliştirme Bykov'un düz kavramları</span><span class="sxs-lookup"><span data-stu-id="9b0af-191">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="9b0af-192">**Ramon Tomas**, düz kavramları geliştiricisi</span><span class="sxs-lookup"><span data-stu-id="9b0af-192">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="9b0af-193">**David Sanz**, düz kavramları geliştiricisi</span><span class="sxs-lookup"><span data-stu-id="9b0af-193">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="9b0af-194">**Javier Valero**, Enformasyon Müdürü Grupo çözümleri işletim</span><span class="sxs-lookup"><span data-stu-id="9b0af-194">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="9b0af-195">**Pierre Millet**, üst düzey Danışman, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b0af-195">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="9b0af-196">**Michael Friis**, ürün Yöneticisi, Docker Inc.</span><span class="sxs-lookup"><span data-stu-id="9b0af-196">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="9b0af-197">**Charles Lowell**, yazılım mühendisi, VS CAT ekibi, Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b0af-197">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>
>
> <span data-ttu-id="9b0af-198">**Miguel Veloso**, Turing sınama en üst düzey Danışman</span><span class="sxs-lookup"><span data-stu-id="9b0af-198">**Miguel Veloso**, Sr. Consultant at Turing Challenge</span></span>

## <a name="copyright"></a><span data-ttu-id="9b0af-199">Telif Hakkı</span><span class="sxs-lookup"><span data-stu-id="9b0af-199">Copyright</span></span>

<span data-ttu-id="9b0af-200">İNDİRME bulunabilir: <https://aka.ms/microservicesebook></span><span class="sxs-lookup"><span data-stu-id="9b0af-200">DOWNLOAD available at: <https://aka.ms/microservicesebook></span></span>

<span data-ttu-id="9b0af-201">TARAFINDAN YAYIMLANAN</span><span class="sxs-lookup"><span data-stu-id="9b0af-201">PUBLISHED BY</span></span>

<span data-ttu-id="9b0af-202">Microsoft Geliştirici bölme, .NET ve Visual Studio ürün takımları</span><span class="sxs-lookup"><span data-stu-id="9b0af-202">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="9b0af-203">Microsoft Corporation'ın bir bölme</span><span class="sxs-lookup"><span data-stu-id="9b0af-203">A division of Microsoft Corporation</span></span>

<span data-ttu-id="9b0af-204">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="9b0af-204">One Microsoft Way</span></span>

<span data-ttu-id="9b0af-205">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="9b0af-205">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="9b0af-206">Telif Hakkı © 2018 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="9b0af-206">Copyright © 2018 by Microsoft Corporation</span></span>

<span data-ttu-id="9b0af-207">Tüm hakları saklıdır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-207">All rights reserved.</span></span> <span data-ttu-id="9b0af-208">Bu kitap içeriğini bir parçası çoğaltılamaz veya herhangi bir araçla yayımcı yazılı izni olmadan herhangi bir biçimdeki aktarılamaz.</span><span class="sxs-lookup"><span data-stu-id="9b0af-208">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="9b0af-209">Bu kitap sağlanan "olarak-olduğunu" ve yazarın görünümleri ve düşünceleri son derece ifade eder.</span><span class="sxs-lookup"><span data-stu-id="9b0af-209">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="9b0af-210">Görünümleri ve düşünceleri son derece bilgi URL ve diğer Internet Web sitesi referansları da dahil olmak üzere bu kitap, ifade verilmeksizin değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="9b0af-210">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="9b0af-211">Burada açıklanan bazı örnekler yalnızca çizim için sağlanmıştır ve bu kurgusaldır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-211">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="9b0af-212">Gerçek bir ilişki veya bağlantı amaçlanmamıştır veya çıkarılmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-212">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="9b0af-213">Microsoft ve adresinde listelenmiş ticari <https://www.microsoft.com> "Ticari" Web sayfasında Microsoft şirketler grubunun ticari markalarıdır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-213">Microsoft and the trademarks listed at <https://www.microsoft.com> on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="9b0af-214">Mac ve macOS Apple Inc.'in ticari markalarıdır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-214">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="9b0af-215">Docker whale logosu, Docker, Inc.'in kayıtlı ticari markasıdır. İzni tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="9b0af-215">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="9b0af-216">Diğer tüm işaretleri ve logoları sahiplerinin özelliği var.</span><span class="sxs-lookup"><span data-stu-id="9b0af-216">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="9b0af-217">Next</span><span class="sxs-lookup"><span data-stu-id="9b0af-217">Next</span></span>](container-docker-introduction/index.md)
