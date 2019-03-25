---
title: Özel yaşam süresi
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: be6013d568e3625c5eac7e0c145db7df1c6917e3
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410387"
---
# <a name="custom-lifetime"></a><span data-ttu-id="dfdfb-102">Özel yaşam süresi</span><span class="sxs-lookup"><span data-stu-id="dfdfb-102">Custom lifetime</span></span>

<span data-ttu-id="dfdfb-103">Bu örnek nasıl paylaşılan WCF hizmet örneklerine yönelik özel yaşam süresi hizmetleri sağlamak için bir Windows Communication Foundation (WCF) uzantısı yazılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>

> [!NOTE]
> <span data-ttu-id="dfdfb-104">Bu örnek için Kurulum yordamı ve derleme yönergeleri bu makalenin sonunda yer alır.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>

## <a name="shared-instancing"></a><span data-ttu-id="dfdfb-105">Paylaşılan örnek oluşturma</span><span class="sxs-lookup"><span data-stu-id="dfdfb-105">Shared instancing</span></span>

<span data-ttu-id="dfdfb-106">WCF hizmet örnekleriniz için birden çok örneklemesini modları sunar.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="dfdfb-107">Bu makalede ele alınan paylaşılan örneklemesini modu, bir hizmet örneği birden çok kanalda arasında paylaşmak için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-107">The shared instancing mode covered in this article provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="dfdfb-108">İstemciler, bir Üreteç yöntemi hizmetinde başvurun ve iletişim başlatmak için yeni bir kanal oluşturmak.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-108">Clients can contact a factory method in the service and create a new channel to start communication.</span></span> <span data-ttu-id="dfdfb-109">Aşağıdaki kod parçacığı bir istemci uygulamanın yeni bir kanal var olan bir hizmet örneğine nasıl oluşturduğunu gösterir:</span><span class="sxs-lookup"><span data-stu-id="dfdfb-109">The following code snippet shows how a client application creates a new channel to an existing service instance:</span></span>

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

<span data-ttu-id="dfdfb-110">Örneklemesini modlardan, paylaşılan örneklemesini modu hizmet örnekleri serbest benzersiz bir yolu yoktur.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-110">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="dfdfb-111">İçin tüm kanalları kapatıldığında varsayılan olarak bir <xref:System.ServiceModel.InstanceContext>, WCF Hizmeti çalışma zamanı olup olmadığını denetler. hizmet <xref:System.ServiceModel.InstanceContextMode> yapılandırılır <xref:System.ServiceModel.InstanceContextMode.PerCall> veya <xref:System.ServiceModel.InstanceContextMode.PerSession>ve bu nedenle örneği serbest bırakır ve kaynak talepleri.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-111">By default, when all the channels are closed for an <xref:System.ServiceModel.InstanceContext>, the WCF service runtime checks to see if the service <xref:System.ServiceModel.InstanceContextMode> is configured to <xref:System.ServiceModel.InstanceContextMode.PerCall> or <xref:System.ServiceModel.InstanceContextMode.PerSession>, and if so releases the instance and claims the resources.</span></span> <span data-ttu-id="dfdfb-112">Özel durumunda <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> olan kullanılan, WCF çağırır <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> örneği serbest önce sağlayıcıyı uygulama yöntemi.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-112">If a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is being used, WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the provider implementation before releasing the instance.</span></span> <span data-ttu-id="dfdfb-113">Varsa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> döndürür `true` örneği, aksi takdirde serbest <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> uygulamasıdır bildirmek için sorumlu `Dispatcher` boşta durumuna geri çağırma yöntemi kullanarak.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-113">If <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> returns `true` the instance is released, otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span> <span data-ttu-id="dfdfb-114">Bu çağrılarak gerçekleştirilir <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> sağlayıcısının yöntemi.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-114">This is done by calling the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method of the provider.</span></span>

<span data-ttu-id="dfdfb-115">Bu örnek nasıl serbest erteleyebilirsiniz gösterir <xref:System.ServiceModel.InstanceContext> 20 saniyelik bir boşta zaman aşımı ile.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-115">This sample demonstrates how you can delay releasing the <xref:System.ServiceModel.InstanceContext> with an idle timeout of 20 seconds.</span></span>

## <a name="extending-the-instancecontext"></a><span data-ttu-id="dfdfb-116">InstanceContext genişletme</span><span class="sxs-lookup"><span data-stu-id="dfdfb-116">Extending the InstanceContext</span></span>

<span data-ttu-id="dfdfb-117">Wcf'de, <xref:System.ServiceModel.InstanceContext> hizmet örneği arasında bağlantı ve `Dispatcher`.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-117">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="dfdfb-118">WCF yeni durum ya da davranışı, Genişletilebilir nesne düzeni'ni kullanarak ekleyerek bu çalışma zamanı bileşeni genişletmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-118">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="dfdfb-119">Genişletilebilir nesne düzeni WCF'de ya da var olan çalışma zamanı sınıflar yeni işlevlerle genişletmek veya bir nesne için yeni durum özellikler eklemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-119">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="dfdfb-120">Genişletilebilir nesne modelinde üç arabirimi vardır: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, ve <xref:System.ServiceModel.IExtensionCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-120">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>

<span data-ttu-id="dfdfb-121"><xref:System.ServiceModel.IExtensibleObject%601> Arabirimi işlevleriyle özelleştirme uzantılarına izin vermek için nesneler tarafından uygulanır.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-121">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by objects to allow extensions that customize their functionality.</span></span>

<span data-ttu-id="dfdfb-122"><xref:System.ServiceModel.IExtension%601> Arabirimi sınıf türü uzantıları olabilir nesneleri tarafından uygulanan `T`.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-122">The <xref:System.ServiceModel.IExtension%601> interface is implemented by objects that can be extensions of classes of type `T`.</span></span>

<span data-ttu-id="dfdfb-123">Son olarak, <xref:System.ServiceModel.IExtensionCollection%601> arabirimidir koleksiyonu <xref:System.ServiceModel.IExtension%601> uygulaması almak için izin veren uygulamaları <xref:System.ServiceModel.IExtension%601> türüne göre.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-123">And finally, the <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of <xref:System.ServiceModel.IExtension%601> implementations that allows for retrieving an implementation of <xref:System.ServiceModel.IExtension%601> by their type.</span></span>

<span data-ttu-id="dfdfb-124">Bu nedenle, genişletebilmek için <xref:System.ServiceModel.InstanceContext>, uygulamanız gereken <xref:System.ServiceModel.IExtension%601> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-124">Therefore, in order to extend the <xref:System.ServiceModel.InstanceContext>, you must implement the <xref:System.ServiceModel.IExtension%601> interface.</span></span> <span data-ttu-id="dfdfb-125">Bu örnek projesinde `CustomLeaseExtension` sınıfı uygulaması içerir.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-125">In this sample project, the `CustomLeaseExtension` class contains this implementation.</span></span>

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

<span data-ttu-id="dfdfb-126"><xref:System.ServiceModel.IExtension%601> Arabirimi iki yöntem vardır <xref:System.ServiceModel.IExtension%601.Attach%2A> ve <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-126">The <xref:System.ServiceModel.IExtension%601> interface has two methods <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span> <span data-ttu-id="dfdfb-127">Adlarını da ifade ettiği şekilde çalışma zamanı ekler ve uzantısı örneğine ayırır bu iki yöntem de çağrıldığında <xref:System.ServiceModel.InstanceContext> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-127">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="dfdfb-128">Bu örnekte `Attach` yöntemi izlemek için kullanılan <xref:System.ServiceModel.InstanceContext> uzantı geçerli örneğine ait nesne.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-128">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

<span data-ttu-id="dfdfb-129">Ayrıca, gerekli uygulama genişletilmiş ömrü desteği sağlamak için uzantıya eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-129">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="dfdfb-130">Bu nedenle, `ICustomLease` arabirimi istenen yöntemleri ile bildirilir ve uygulanan `CustomLeaseExtension` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-130">Therefore, the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

<span data-ttu-id="dfdfb-131">Ne zaman WCF çağırır <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> yönteminde <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> uygulaması, bu çağrı için yönlendirilir <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> yöntemi `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-131">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation, this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="dfdfb-132">Ardından, `CustomLeaseExtension` özel durumunu görmek için denetler olmadığını <xref:System.ServiceModel.InstanceContext> boştadır.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-132">Then, the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="dfdfb-133">Eğer boş ise, döndürür `true`.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-133">If it is idle, it returns `true`.</span></span> <span data-ttu-id="dfdfb-134">Aksi takdirde, genişletilmiş yaşam süresi belirtilen bir miktarı için bir süreölçer başlatır.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-134">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>

```csharp
public bool IsIdle
{
  get
  {
    lock (thisLock)
    {
      if (isIdle)
      {
        return true;
      }
      else
      {
        StartTimer();
        return false;
      }
    }
  }
}
```

<span data-ttu-id="dfdfb-135">Zamanlayıcının içinde `Elapsed` olay dağıtıcısı içindeki geri arama işlevi başka bir temizleme döngüsü başlatmak için çağrılır.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-135">In the timer’s `Elapsed` event, the callback function in the Dispatcher is called in order to start another clean-up cycle.</span></span>

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

<span data-ttu-id="dfdfb-136">Boşta durumuna taşınan örneği için yeni bir ileti geldiğinde çalışan Zamanlayıcı yenilemek için hiçbir yolu yoktur.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-136">There's no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>

<span data-ttu-id="dfdfb-137">Örnek uygulayan <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> çağrıları izlemesine <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> yöntemi ve rota onları `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-137">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="dfdfb-138"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> Uygulama kapsanıyorsa `CustomLifetimeLease` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-138">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="dfdfb-139"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> WCF hizmet örneği hakkında yayımlamayı olduğunda yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-139">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="dfdfb-140">Ancak, belirli bir yalnızca bir örneğini yoktur `ISharedSessionInstance` ServiceBehavior'ın uygulamasında <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-140">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="dfdfb-141">Bu biri olduğunu bilerek bir yolu yoktur anlamına gelir <xref:System.ServiceModel.InstanceContext> WCF denetler zaman kapalı <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-141">This means there's no way of knowing if the <xref:System.ServiceModel.InstanceContext> is closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="dfdfb-142">Bu nedenle, bu örnek isteklerine seri hale getirmek için iş parçacığı kullanan <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-142">Therefore, this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfdfb-143">Serileştirme uygulamanızın performansını önemli ölçüde etkileyebilir çünkü iş parçacığı kilitleme kullanmak önerilen bir yaklaşım değildir.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-143">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>

<span data-ttu-id="dfdfb-144">Özel üye alanı kullanılır `CustomLifetimeLease` boşta durumunu izlemek için sınıf ve tarafından döndürülen <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-144">A private member field is used in the `CustomLifetimeLease` class to track the idle state and is returned by the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="dfdfb-145">Her zaman <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> yöntemi çağrıldığında `isIdle` alan döndürdü ve sıfırlama `false`.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-145">Each time the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is called, the `isIdle` field is returned and reset to `false`.</span></span>  <span data-ttu-id="dfdfb-146">Bu değeri ayarlamak için gerekli `false` dağıtıcı çağrıları emin olmak için <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-146">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

<span data-ttu-id="dfdfb-147">Varsa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> yöntemi döndürür `false`, dağıtıcı kullanarak bir geri çağırma işlevini kaydeder <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-147">If the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> method returns `false`, the Dispatcher registers a callback function by using the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span> <span data-ttu-id="dfdfb-148">Bu yöntem bir başvuru alır <xref:System.ServiceModel.InstanceContext> serbest bırakılıyor.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-148">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="dfdfb-149">Bu nedenle, örnek kod sorgulayabilirsiniz `ICustomLease` uzantısı yazın ve kontrol `ICustomLease.IsIdle` Genişletilmiş durum özelliğini.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-149">Therefore, the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>

```csharp
public void NotifyIdle(InstanceContextIdleCallback callback,
            InstanceContext instanceContext)
{
    lock (thisLock)
    {
       ICustomLease customLease =
           instanceContext.Extensions.Find<ICustomLease>();
       customLease.Callback = callback;
       isIdle = customLease.IsIdle;
       if (isIdle)
       {
             callback(instanceContext);
       }
    }
}
```

<span data-ttu-id="dfdfb-150">Önce `ICustomLease.IsIdle` işaretli özelliği, geri çağırma özelliği için gerekli olduğundan ayarlanması gerekir `CustomLeaseExtension` boşta kaldığında göndereni bilgilendirmek için.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-150">Before the `ICustomLease.IsIdle` property is checked, the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="dfdfb-151">Varsa `ICustomLease.IsIdle` döndürür `true`, `isIdle` özel üye ayarlamanız yeterlidir `CustomLifetimeLease` için `true` ve geri çağırma yöntemini çağırır.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-151">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="dfdfb-152">Kod bir kilit tuttuğunda olduğundan, diğer iş parçacıkları bu özel üye değerini değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-152">Because the code holds a lock, other threads can't change the value of this private member.</span></span> <span data-ttu-id="dfdfb-153">Ve dağıtıcı arar sonraki açışınızda <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, döndürür `true` ve dağıtıcı örneği serbest olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-153">And the next time Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, it returns `true` and lets Dispatcher release the instance.</span></span>

<span data-ttu-id="dfdfb-154">Özel uzantı kavuşacak tamamlandı, hizmet modeli ölçekledikçe gerekmez.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-154">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="dfdfb-155">Bağlama için `CustomLeaseExtension` uygulamasına <xref:System.ServiceModel.InstanceContext>, WCF sağlar <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> , önyükleme gerçekleştirmek için arabirimi <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-155">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="dfdfb-156">Örnekte, `CustomLeaseInitializer` sınıfı bu arabirimi uygulayan ve bir örneğini ekler `CustomLeaseExtension` için <xref:System.ServiceModel.InstanceContext.Extensions%2A> koleksiyondan tek yöntemi başlatma.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-156">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="dfdfb-157">Bu yöntem tarafından dağıtıcısı başlatılırken çağrılır <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-157">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 <span data-ttu-id="dfdfb-158">Son olarak <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> uygulaması ölçekledikçe hizmet modeli kullanarak <xref:System.ServiceModel.Description.IServiceBehavior> uygulaması.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-158">Finally the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="dfdfb-159">Bu uygulama yerleştirilir `CustomLeaseTimeAttribute` sınıfı ve ayrıca türetilen <xref:System.Attribute> temel sınıfı, bu davranışı bir öznitelik olarak kullanıma sunmak için.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-159">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the <xref:System.Attribute> base class to expose this behavior as an attribute.</span></span>

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

<span data-ttu-id="dfdfb-160">Bu davranışı için örnek bir hizmet sınıfı ile açıklama eklenebilir `CustomLeaseTime` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-160">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

<span data-ttu-id="dfdfb-161">Örneği çalıştırdığınızda, işlem isteklerini ve yanıtlarını hem hizmet hem de istemci konsol pencerelerinde görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-161">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="dfdfb-162">Her konsol penceresi hizmet ve istemci kapatmak için ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-162">Press ENTER in each console window to shut down the service and client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dfdfb-163">Ayarlamak için derleme ve örneği çalıştırma</span><span class="sxs-lookup"><span data-stu-id="dfdfb-163">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="dfdfb-164">Gerçekleştirdiğiniz emin olun [Windows Communication Foundation örnekleri için bir kerelik Kurulum yordamı](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dfdfb-164">Ensure that you've performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="dfdfb-165">Çözüm C# veya Visual Basic .NET sürümünü oluşturmak için yönergeleri izleyin. [Windows Communication Foundation örnekleri derleme](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dfdfb-165">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="dfdfb-166">Tek veya çapraz makine yapılandırmasında örneği çalıştırmak için yönergeleri izleyin. [Windows Communication Foundation örneklerini çalıştırma](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dfdfb-166">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfdfb-167">Örnekler, makinenizde zaten yüklü.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dfdfb-168">Devam etmeden önce şu (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-168">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="dfdfb-169">Bu dizin mevcut değilse Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnekleri](https://go.microsoft.com/fwlink/?LinkId=150780) tüm Windows Communication Foundation (WCF) indirmek için ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dfdfb-170">Bu örnek, şu dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="dfdfb-170">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
