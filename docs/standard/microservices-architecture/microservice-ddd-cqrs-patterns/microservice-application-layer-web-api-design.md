---
title: Mikro hizmet uygulama katmanı ve Web API’sini tasarlama
description: Kapsayıcılı .NET uygulamaları için .NET mikro hizmet mimarisi | Uygulama katmanı tasarlamaya yönelik KATI ilkeler, kısa bir Bahsetme.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/08/2018
ms.openlocfilehash: 9177ac9a79afaea01f0ec21b0a64bad5a94e9966
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612244"
---
# <a name="design-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="f7935-103">Mikro hizmet uygulama katmanı ve Web API'sini tasarlama</span><span class="sxs-lookup"><span data-stu-id="f7935-103">Design the microservice application layer and Web API</span></span>

## <a name="use-solid-principles-and-dependency-injection"></a><span data-ttu-id="f7935-104">KATI ilkeler ve bağımlılık ekleme</span><span class="sxs-lookup"><span data-stu-id="f7935-104">Use SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="f7935-105">KATI ilkeler DDD deseni ile bir mikro hizmet geliştirme gibi modern ve görev açısından kritik bir uygulamada, kullanılacak kritik tekniklerle aynıdır.</span><span class="sxs-lookup"><span data-stu-id="f7935-105">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="f7935-106">DÜZ bir kısaltma bu grupları beş temel ilkeler verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="f7935-106">SOLID is an acronym that groups five fundamental principles:</span></span>

- <span data-ttu-id="f7935-107">Tek sorumluluk İlkesi</span><span class="sxs-lookup"><span data-stu-id="f7935-107">Single Responsibility principle</span></span>

- <span data-ttu-id="f7935-108">İlke açık/kapalı</span><span class="sxs-lookup"><span data-stu-id="f7935-108">Open/closed principle</span></span>

- <span data-ttu-id="f7935-109">Liskov değiştirme İlkesi</span><span class="sxs-lookup"><span data-stu-id="f7935-109">Liskov substitution principle</span></span>

- <span data-ttu-id="f7935-110">Ayırma ilkesini arabirimi</span><span class="sxs-lookup"><span data-stu-id="f7935-110">Interface Segregation principle</span></span>

- <span data-ttu-id="f7935-111">Bağımlılık tersine çevirme ilkesi</span><span class="sxs-lookup"><span data-stu-id="f7935-111">Dependency Inversion principle</span></span>

<span data-ttu-id="f7935-112">DÜZ, uygulamanızın veya iç mikro hizmet katmanları nasıl tasarlayacağınızı ve aralarındaki bağımlılıkları ayırma hakkında daha fazla.</span><span class="sxs-lookup"><span data-stu-id="f7935-112">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="f7935-113">Bu etki alanı, ancak uygulamanın teknik tasarım ilişkili değil.</span><span class="sxs-lookup"><span data-stu-id="f7935-113">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="f7935-114">Son ilke, bağımlılık tersine çevirme ilkesine DDD katmanların bir daha iyi ayrılmış uygulama sağlayan diğer katmanların altyapı katmanını ayırmak sağlar.</span><span class="sxs-lookup"><span data-stu-id="f7935-114">The final principle, the Dependency Inversion principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="f7935-115">Bağımlılık ekleme (dı) bağımlılık tersine çevirme ilkesini uygulamak için bir yoludur.</span><span class="sxs-lookup"><span data-stu-id="f7935-115">Dependency Injection (DI) is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="f7935-116">Bu nesneleri ve bunların bağımlılıklarını arasındaki bu sıkı bağ elde etmek için kullanabileceğiniz bir tekniktir.</span><span class="sxs-lookup"><span data-stu-id="f7935-116">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="f7935-117">Doğrudan ortak çalışanlar örnekleme veya (kullanan yeni...) statik başvuruları kullanma yerine, bir sınıf eylemlerini gerçekleştirmek için gereken nesneleri için sağlanan (veya "içine eklenen") sınıfı.</span><span class="sxs-lookup"><span data-stu-id="f7935-117">Rather than directly instantiating collaborators, or using static references (that is, using new…), the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="f7935-118">Çoğunlukla sınıfları, bunları özel bağımlılıklar ilkesini izlemek izin verme oluşturucularına aracılığıyla bunların bağımlılıklarını bildirir.</span><span class="sxs-lookup"><span data-stu-id="f7935-118">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="f7935-119">Bağımlılık ekleme, genellikle belirli bir denetimi tersine çevirme (IOC) kapsayıcı üzerinde temel alır.</span><span class="sxs-lookup"><span data-stu-id="f7935-119">Dependency Injection is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="f7935-120">Basit bir yerleşik IOC kapsayıcısında ASP.NET Core sağlar, ancak Autofac veya Ninject gibi sık kullanılan, IOC kapsayıcı de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f7935-120">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="f7935-121">KATI ilkeler uygulayarak, sınıflarınızı doğal olarak küçük, katsayıları iyi belirlenmiş ve kolayca test edilmiş olma eğilimindedir.</span><span class="sxs-lookup"><span data-stu-id="f7935-121">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="f7935-122">Ancak çok fazla bağımlılıkları, sınıflara eklenmiş olmadığını nasıl bilebilirsiniz?</span><span class="sxs-lookup"><span data-stu-id="f7935-122">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="f7935-123">Oluşturucusu DI kullanırsanız, yalnızca güvenlik denetimini atladığından için parametre sayısı bakarak algılayan kolay olacaktır.</span><span class="sxs-lookup"><span data-stu-id="f7935-123">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="f7935-124">Çok fazla bağımlılıkları varsa, bu, genellikle bir oturum. (bir [kod kokusu](https://deviq.com/code-smells/)) sınıfınıza çok yapmak çalışıyor ve büyük olasılıkla tek sorumluluk ilkesini ihlal.</span><span class="sxs-lookup"><span data-stu-id="f7935-124">If there are too many dependencies, this is generally a sign (a [code smell](https://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="f7935-125">Bunu başka bir kılavuz DÜZ ayrıntılı olarak ele alır.</span><span class="sxs-lookup"><span data-stu-id="f7935-125">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="f7935-126">Bu nedenle, bu kılavuzda Bu konu için en az bir bilgiye sahip gerektirir.</span><span class="sxs-lookup"><span data-stu-id="f7935-126">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="f7935-127">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="f7935-127">Additional resources</span></span>

- <span data-ttu-id="f7935-128">**DÜZ: Temel OOP ilkeleri** \\</span><span class="sxs-lookup"><span data-stu-id="f7935-128">**SOLID: Fundamental OOP Principles** \\</span></span>
  <https://deviq.com/solid/>

- <span data-ttu-id="f7935-129">**Tersine çevirme denetimi kapsayıcıları ve bağımlılık ekleme deseni** \\</span><span class="sxs-lookup"><span data-stu-id="f7935-129">**Inversion of Control Containers and the Dependency Injection pattern** \\</span></span>
  <https://martinfowler.com/articles/injection.html>

- <span data-ttu-id="f7935-130">**Steve Smith. Birleştirici yenilikler** \\</span><span class="sxs-lookup"><span data-stu-id="f7935-130">**Steve Smith. New is Glue** \\</span></span>
  <https://ardalis.com/new-is-glue>

> [!div class="step-by-step"]
> <span data-ttu-id="f7935-131">[Önceki](nosql-database-persistence-infrastructure.md)
> [İleri](microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="f7935-131">[Previous](nosql-database-persistence-infrastructure.md)
[Next](microservice-application-layer-implementation-web-api.md)</span></span>
