---
title: COM Aranabilir Sarmalayıcısı
ms.date: 10/23/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CCW
- COM interop, COM wrappers
- COM wrappers
- callable wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: d04be3b5-27b9-4f5b-8469-a44149fabf78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e62d115292edc7b75ff782ac2c9161d942077333
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655341"
---
# <a name="com-callable-wrapper"></a><span data-ttu-id="e9bd5-102">COM Aranabilir Sarmalayıcısı</span><span class="sxs-lookup"><span data-stu-id="e9bd5-102">COM Callable Wrapper</span></span>
<span data-ttu-id="e9bd5-103">Bir COM istemcisi bir .NET nesnesini çağırdığında, ortak dil çalışma zamanı yönetilen nesneyi ve nesne için bir COM çağrılabilir sarmalayıcı (CCW) oluşturur.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-103">When a COM client calls a .NET object, the common language runtime creates the managed object and a COM callable wrapper (CCW) for the object.</span></span> <span data-ttu-id="e9bd5-104">Başvuru bir .NET nesnesini doğrudan COM istemcileri CCW bir proxy olarak yönetilen bir nesne için kullanın.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-104">Unable to reference a .NET object directly, COM clients use the CCW as a proxy for the managed object.</span></span>  
  
 <span data-ttu-id="e9bd5-105">Çalışma zamanı hizmetlerinin isteyen COM istemcileri sayısından bağımsız olarak yönetilen bir nesne için tam olarak bir saat oluşturur.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-105">The runtime creates exactly one CCW for a managed object, regardless of the number of COM clients requesting its services.</span></span> <span data-ttu-id="e9bd5-106">Aşağıdaki çizimde gösterildiği gibi birden çok COM istemcileri INew arabirimi kullanıma sunan CCW başvuru barındırabilir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-106">As the following illustration shows, multiple COM clients can hold a reference to the CCW that exposes the INew interface.</span></span> <span data-ttu-id="e9bd5-107">CCW sırayla arabirimi uygulayan yönetilen bir nesne için tek bir başvuru içerir ve atık olarak toplanmış.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-107">The CCW, in turn, holds a single reference to the managed object that implements the interface and is garbage collected.</span></span> <span data-ttu-id="e9bd5-108">COM hem .NET istemcileri, istekleri için aynı anda aynı yönetilen nesne üzerinde hale getirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-108">Both COM and .NET clients can make requests on the same managed object simultaneously.</span></span>  
  
 <span data-ttu-id="e9bd5-109">![COM çağrılabilir sarmalayıcısı](./media/ccw.gif "ccw")</span><span class="sxs-lookup"><span data-stu-id="e9bd5-109">![COM callable wrapper](./media/ccw.gif "ccw")</span></span>  
<span data-ttu-id="e9bd5-110">COM çağrılabilir sarmalayıcı .NET nesnelerini erişme</span><span class="sxs-lookup"><span data-stu-id="e9bd5-110">Accessing .NET objects through COM callable wrapper</span></span>  
  
 <span data-ttu-id="e9bd5-111">COM aranabilir sarmalayıcılar, .NET Framework içinde çalışan diğer sınıflar için görünmez.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-111">COM callable wrappers are invisible to other classes running within the .NET Framework.</span></span> <span data-ttu-id="e9bd5-112">Birincil amaçları, yönetilen ve yönetilmeyen kod arasındaki çağrıların sıralamanız sağlamaktır; Ancak, CCWs nesne kimliğini ve nesne yaşam süresi bunlar kaydırma yönetilen nesnelerin yönetin.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-112">Their primary purpose is to marshal calls between managed and unmanaged code; however, CCWs also manage the object identity and object lifetime of the managed objects they wrap.</span></span>  
  
## <a name="object-identity"></a><span data-ttu-id="e9bd5-113">Nesne Kimliği</span><span class="sxs-lookup"><span data-stu-id="e9bd5-113">Object Identity</span></span>  
 <span data-ttu-id="e9bd5-114">Çalışma zamanı, nesne bellekte gerektiği gibi hareket etmek çalışma zamanı sağlayan kendi atık olarak toplanmış yığınla, gelen .NET nesne için bellek ayırır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-114">The runtime allocates memory for the .NET object from its garbage-collected heap, which enables the runtime to move the object around in memory as necessary.</span></span> <span data-ttu-id="e9bd5-115">Buna karşılık, çalışma zamanı sarmalayıcı doğrudan başvurmak COM istemcileri için çözmelerine noncollected yığın, gelen CCW için bellek ayırır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-115">In contrast, the runtime allocates memory for the CCW from a noncollected heap, making it possible for COM clients to reference the wrapper directly.</span></span>  
  
## <a name="object-lifetime"></a><span data-ttu-id="e9bd5-116">Nesne ömrü</span><span class="sxs-lookup"><span data-stu-id="e9bd5-116">Object Lifetime</span></span>  
 <span data-ttu-id="e9bd5-117">.NET istemci sarmaladığı CCW başvuru-geleneksel COM biçiminde sayılır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-117">Unlike the .NET client it wraps, the CCW is reference-counted in traditional COM fashion.</span></span> <span data-ttu-id="e9bd5-118">Sarmalayıcı CCW başvuru sayısını sıfır ulaştığında, yönetilen nesne üzerinde onun başvuru serbest bırakır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-118">When the reference count on the CCW reaches zero, the wrapper releases its reference on the managed object.</span></span> <span data-ttu-id="e9bd5-119">Kalan başvuru ile yönetilen bir nesnenin sonraki çöp toplama döngüsü sırasında toplanır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-119">A managed object with no remaining references is collected during the next garbage-collection cycle.</span></span>  
  
## <a name="simulating-com-interfaces"></a><span data-ttu-id="e9bd5-120">COM arabirimlerinin benzetimi</span><span class="sxs-lookup"><span data-stu-id="e9bd5-120">Simulating COM interfaces</span></span>

<span data-ttu-id="e9bd5-121">SAAT, tüm genel, COM görünebilir arabirimler, veri türleri ve dönüş değerleri ile etkileşim arabirimi tabanlı COM'ın zorlama tutarlı bir şekilde COM istemcilerine kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-121">CCW exposes all public, COM-visible interfaces, data types, and return values to COM clients in a manner that is consistent with COM's enforcement of interface-based interaction.</span></span> <span data-ttu-id="e9bd5-122">Bir COM istemcisi için bir .NET Framework nesnesi yöntemleri çağrılırken bir COM nesnesi üzerinde yöntemleri çağırmak için aynıdır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-122">For a COM client, invoking methods on a .NET Framework object is identical to invoking methods on a COM object.</span></span>  
  
 <span data-ttu-id="e9bd5-123">Bu sorunsuz yaklaşım oluşturmak için CCW geleneksel COM arabirimleri gibi üreten **IUnknown** ve **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-123">To create this seamless approach, the CCW manufactures traditional COM interfaces, such as **IUnknown** and **IDispatch**.</span></span> <span data-ttu-id="e9bd5-124">Aşağıdaki çizimde gösterildiği gibi saatin tersi YÖNDE sarmaladığı .NET nesne üzerinde tek bir başvuru tutar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-124">As the following illustration shows, the CCW maintains a single reference on the .NET object that it wraps.</span></span> <span data-ttu-id="e9bd5-125">COM istemcisi ve .NET nesne CCW. proxy ve saplama yapımı birbiriyle etkileşim</span><span class="sxs-lookup"><span data-stu-id="e9bd5-125">Both the COM client and .NET object interact with each other through the proxy and stub construction of the CCW.</span></span>  
  
 <span data-ttu-id="e9bd5-126">![COM arabirimleri](./media/ccwwithinterfaces.gif "ccwwithinterfaces")</span><span class="sxs-lookup"><span data-stu-id="e9bd5-126">![COM interfaces](./media/ccwwithinterfaces.gif "ccwwithinterfaces")</span></span>  
<span data-ttu-id="e9bd5-127">COM arabirimlerinde ve COM çağrılabilir sarmalayıcısı</span><span class="sxs-lookup"><span data-stu-id="e9bd5-127">COM interfaces and the COM callable wrapper</span></span>  
  
 <span data-ttu-id="e9bd5-128">Açıkça yönetilen bir ortamda bir sınıf tarafından uygulanan arabirimler gösterme ek olarak, .NET Framework uygulamaları nesne adına aşağıdaki tabloda listelenen COM arabirimleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-128">In addition to exposing the interfaces that are explicitly implemented by a class in the managed environment, the .NET Framework supplies implementations of the COM interfaces listed in the following table on behalf of the object.</span></span> <span data-ttu-id="e9bd5-129">Bir .NET sınıf kendi uygulaması bu arabirimlerin sağlayarak varsayılan davranışı geçersiz kılabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-129">A .NET class can override the default behavior by providing its own implementation of these interfaces.</span></span> <span data-ttu-id="e9bd5-130">Ancak, çalışma zamanının uygulamasını her zaman sağlar **IUnknown** ve **IDispatch** arabirimleri.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-130">However, the runtime always provides the implementation for the **IUnknown** and **IDispatch** interfaces.</span></span>  
  
|<span data-ttu-id="e9bd5-131">Arabirim</span><span class="sxs-lookup"><span data-stu-id="e9bd5-131">Interface</span></span>|<span data-ttu-id="e9bd5-132">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e9bd5-132">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9bd5-133">**IDispatch**</span><span class="sxs-lookup"><span data-stu-id="e9bd5-133">**Idispatch**</span></span>|<span data-ttu-id="e9bd5-134">Geç bağlama türü bir mekanizma sağlar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-134">Provides a mechanism for late binding to type.</span></span>|  
|<span data-ttu-id="e9bd5-135">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="e9bd5-135">**IerrorInfo**</span></span>|<span data-ttu-id="e9bd5-136">Hata, kaynağı, bir Yardım dosyası, Yardım bağlamı ve hata tanımlı arabiriminin GUID'si değerinin metinsel bir açıklaması verilmiştir (her zaman **GUID_NULL** .NET sınıfları için).</span><span class="sxs-lookup"><span data-stu-id="e9bd5-136">Provides a textual description of the error, its source, a Help file, Help context, and the GUID of the interface that defined the error (always **GUID_NULL** for .NET classes).</span></span>|  
|<span data-ttu-id="e9bd5-137">**IprovideClassInfo**</span><span class="sxs-lookup"><span data-stu-id="e9bd5-137">**IprovideClassInfo**</span></span>|<span data-ttu-id="e9bd5-138">Erişim elde etmek COM istemcileri etkinleştirir **ITypeInfo** yönetilen bir sınıf tarafından uygulanan arabirimi.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-138">Enables COM clients to gain access to the **ITypeInfo** interface implemented by a managed class.</span></span>|  
|<span data-ttu-id="e9bd5-139">**IsupportErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="e9bd5-139">**IsupportErrorInfo**</span></span>|<span data-ttu-id="e9bd5-140">Yönetilen Nesne destekleyip desteklemediğini belirlemek üzere bir COM istemcisi sağlayan **IErrorInfo** arabirimi.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-140">Enables a COM client to determine whether the managed object supports the **IErrorInfo** interface.</span></span> <span data-ttu-id="e9bd5-141">Bu durumda, istemcinin en son özel durum nesnesine bir işaretçi alma sağlar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-141">If so, enables the client to obtain a pointer to the latest exception object.</span></span> <span data-ttu-id="e9bd5-142">Tüm yönetilen türleri desteği **IErrorInfo** arabirimi.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-142">All managed types support the **IErrorInfo** interface.</span></span>|  
|<span data-ttu-id="e9bd5-143">**ITypeInfo**</span><span class="sxs-lookup"><span data-stu-id="e9bd5-143">**ItypeInfo**</span></span>|<span data-ttu-id="e9bd5-144">Tlbexp.exe tarafından üretilen tür bilgilerini tam olarak aynıdır bir sınıf için tür bilgisini sağlar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-144">Provides type information for a class that is exactly the same as the type information produced by Tlbexp.exe.</span></span>|  
|<span data-ttu-id="e9bd5-145">**IUnknown**</span><span class="sxs-lookup"><span data-stu-id="e9bd5-145">**Iunknown**</span></span>|<span data-ttu-id="e9bd5-146">Standart uygulamasını sağlar **IUnknown** arabirimi hangi COM istemcisi CCW ömrünü yönetir ve türü zorlama sağlar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-146">Provides the standard implementation of the **IUnknown** interface with which the COM client manages the lifetime of the CCW and provides type coercion.</span></span>|  
  
 <span data-ttu-id="e9bd5-147">Yönetilen bir sınıf ayrıca aşağıdaki tabloda açıklanan COM arabirimleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-147">A managed class can also provide the COM interfaces described in the following table.</span></span>  
  
|<span data-ttu-id="e9bd5-148">Arabirim</span><span class="sxs-lookup"><span data-stu-id="e9bd5-148">Interface</span></span>|<span data-ttu-id="e9bd5-149">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e9bd5-149">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9bd5-150">(\_*Classname*) sınıf arabirimi</span><span class="sxs-lookup"><span data-stu-id="e9bd5-150">The (\_*classname*) class interface</span></span>|<span data-ttu-id="e9bd5-151">Çalışma zamanı tarafından kullanıma sunulan ve açıkça tanımlanmış, arabirim, tüm ortak arabirimler, yöntemler, özellikler ve yönetilen bir nesne üzerinde açıkça gösterilen alanlar kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-151">Interface, exposed by the runtime and not explicitly defined, that exposes all public interfaces, methods, properties, and fields that are explicitly exposed on a managed object.</span></span>|  
|<span data-ttu-id="e9bd5-152">**IConnectionPoint** ve **IConnectionPointContainer**</span><span class="sxs-lookup"><span data-stu-id="e9bd5-152">**IConnectionPoint** and **IConnectionPointContainer**</span></span>|<span data-ttu-id="e9bd5-153">Temsilci tabanlı olay (etkinlik abonelerinden kaydetmek için bir arabirimi) kaynak nesneleri için arabirim.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-153">Interface for objects that source delegate-based events (an interface for registering event subscribers).</span></span>|  
|<span data-ttu-id="e9bd5-154">**Idispatchex**</span><span class="sxs-lookup"><span data-stu-id="e9bd5-154">**IdispatchEx**</span></span>|<span data-ttu-id="e9bd5-155">Arabirim sınıfı kullanılıyorsa çalışma zamanı tarafından sağlanan **IExpando**.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-155">Interface supplied by the runtime if the class implements **IExpando**.</span></span> <span data-ttu-id="e9bd5-156">**Idispatchex** arabirimi uzantısıdır **IDispatch** aksine, arabirim **IDispatch**, numaralandırma, ekleme, silme, sağlar ve büyük/küçük harfe üyeleri çağırma.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-156">The **IDispatchEx** interface is an extension of the **IDispatch** interface that, unlike **IDispatch**, enables enumeration, addition, deletion, and case-sensitive calling of members.</span></span>|  
|<span data-ttu-id="e9bd5-157">**IEnumVARIANT**</span><span class="sxs-lookup"><span data-stu-id="e9bd5-157">**IEnumVARIANT**</span></span>|<span data-ttu-id="e9bd5-158">Arabirim için koleksiyon türü sınıflar, sınıf uyguluyorsa, koleksiyondaki nesneleri numaralandırır **IEnumerable**.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-158">Interface for collection-type classes, which enumerates the objects in the collection if the class implements **IEnumerable**.</span></span>|  
  
## <a name="introducing-the-class-interface"></a><span data-ttu-id="e9bd5-159">Sınıf arabirimine giriş</span><span class="sxs-lookup"><span data-stu-id="e9bd5-159">Introducing the class interface</span></span>  
 <span data-ttu-id="e9bd5-160">Açıkça yönetilen kodda tanımlı değil, sınıf arabirimi tüm genel yöntemler, özellikler, alanlar ve .NET nesne üzerinde açık olayları ortaya koyan bir arabirimdir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-160">The class interface, which is not explicitly defined in managed code, is an interface that exposes all public methods, properties, fields, and events that are explicitly exposed on the .NET object.</span></span> <span data-ttu-id="e9bd5-161">Bu arabirim, bir çift veya yalnızca gönderme arabirimi olabilir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-161">This interface can be a dual or dispatch-only interface.</span></span> <span data-ttu-id="e9bd5-162">Sınıf arabirimine bir alt çizgi öncesinde .NET sınıfın kendisi adını alır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-162">The class interface receives the name of the .NET class itself, preceded by an underscore.</span></span> <span data-ttu-id="e9bd5-163">Örneğin, sınıf Mammal sınıfı arabirimidir \_Mammal.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-163">For example, for class Mammal, the class interface is \_Mammal.</span></span>  
  
 <span data-ttu-id="e9bd5-164">Türetilen sınıflar için sınıf arabirimi tüm genel yöntemler, özellikler ve alanları temel sınıfın sunar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-164">For derived classes, the class interface also exposes all public methods, properties, and fields of the base class.</span></span> <span data-ttu-id="e9bd5-165">Türetilmiş sınıf ayrıca her bir temel sınıf için bir sınıf arabirimi kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-165">The derived class also exposes a class interface for each base class.</span></span> <span data-ttu-id="e9bd5-166">Örneğin, sınıf Mammal sınıfı MammalSuperclass geçerse, kendisi System.Object genişletir, COM istemcilerinin .NET nesne çıkarır üç adlı arabirimleri sınıf \_Mammal, \_MammalSuperclass, ve \_nesne.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-166">For example, if class Mammal extends class MammalSuperclass, which itself extends System.Object, the .NET object exposes to COM clients three class interfaces named \_Mammal, \_MammalSuperclass, and \_Object.</span></span>  
  
 <span data-ttu-id="e9bd5-167">Örneğin, aşağıdaki .NET sınıf göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="e9bd5-167">For example, consider the following .NET class:</span></span>  
  
```vb  
' Applies the ClassInterfaceAttribute to set the interface to dual.  
<ClassInterface(ClassInterfaceType.AutoDual)> _  
' Implicitly extends System.Object.  
Public Class Mammal  
    Sub Eat()  
    Sub Breathe()  
    Sub Sleep()  
End Class  
```  
  
```csharp
// Applies the ClassInterfaceAttribute to set the interface to dual.
[ClassInterface(ClassInterfaceType.AutoDual)]
// Implicitly extends System.Object.
public class Mammal
{
    public void Eat() {}
    public void Breathe() {}
    public void Sleep() {}
}
```
  
 <span data-ttu-id="e9bd5-168">COM istemcisi adlı bir sınıf arabirimi için bir işaretçi edinebilirsiniz `_Mammal`, Tür Kitaplığı'nda açıklanan, [tür kitaplığı dışarı Aktarıcı (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) aracı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-168">The COM client can obtain a pointer to a class interface named `_Mammal`, which is described in the type library that the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) tool generates.</span></span> <span data-ttu-id="e9bd5-169">Varsa `Mammal` sınıfı bir veya daha fazla arabirim uygulandı, arabirimler coclass'ı altında görünür.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-169">If the `Mammal` class implemented one or more interfaces, the interfaces would appear under the coclass.</span></span>  
  
```  
[odl, uuid(…), hidden, dual, nonextensible, oleautomation]  
interface _Mammal : IDispatch  
{  
    [id(0x00000000), propget] HRESULT ToString([out, retval] BSTR*  
        pRetVal);  
    [id(0x60020001)] HRESULT Equals([in] VARIANT obj, [out, retval]  
        VARIANT_BOOL* pRetVal);  
    [id(0x60020002)] HRESULT GetHashCode([out, retval] short* pRetVal);  
    [id(0x60020003)] HRESULT GetType([out, retval] _Type** pRetVal);  
    [id(0x6002000d)] HRESULT Eat();  
    [id(0x6002000e)] HRESULT Breathe();  
    [id(0x6002000f)] HRESULT Sleep();  
}  
[uuid(…)]  
coclass Mammal   
{  
    [default] interface _Mammal;  
}  
```  
  
 <span data-ttu-id="e9bd5-170">Sınıf arabirimi oluşturma isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-170">Generating the class interface is optional.</span></span> <span data-ttu-id="e9bd5-171">Varsayılan olarak, COM birlikte çalışma için bir tür kitaplığı dışarı her sınıf için bir salt arabirimi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-171">By default, COM interop generates a dispatch-only interface for each class you export to a type library.</span></span> <span data-ttu-id="e9bd5-172">Engelleyebilir veya uygulayarak bu arabirimi otomatik olarak oluşturulmasını değiştirme <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> sınıfınıza.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-172">You can prevent or modify the automatic creation of this interface by applying the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> to your class.</span></span> <span data-ttu-id="e9bd5-173">Sınıf arabirimi yönetilen sınıflar com'da gösterme görevini kolaylaştırabilir olsa da, kullanımları sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-173">Although the class interface can ease the task of exposing managed classes to COM, its uses are limited.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e9bd5-174">Sınıf arabirimi kullanarak açıkça kendi tanımlamak yerine yönetilen sınıfınızın gelecekteki sürüm karmaşık hale getirebilir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-174">Using the class interface, instead of explicitly defining your own, can complicate the future versioning of your managed class.</span></span> <span data-ttu-id="e9bd5-175">Sınıf arabirimi kullanmadan önce lütfen aşağıdaki yönergeleri okuyun.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-175">Please read the following guidelines before using the class interface.</span></span>  
  
### <a name="define-an-explicit-interface-for-com-clients-to-use-rather-than-generating-the-class-interface"></a><span data-ttu-id="e9bd5-176">COM istemcilerine sınıf arabirimi oluşturmak yerine kullanmak için açık bir arabirim tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-176">Define an explicit interface for COM clients to use rather than generating the class interface.</span></span>  
 <span data-ttu-id="e9bd5-177">COM birlikte çalışma sınıf arabirimi otomatik olarak oluşturduğundan, sınıfınıza sonrası sürüm değişikliklerini ortak dil çalışma zamanı tarafından kullanıma sunulan sınıf arabirimi düzenini değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-177">Because COM interop generates a class interface automatically, post-version changes to your class can alter the layout of the class interface exposed by the common language runtime.</span></span> <span data-ttu-id="e9bd5-178">COM istemcileri bir arabirimin düzen değişiklikleri işlemek genellikle hazırlıksız olduğundan, bunlar sınıf üye yerleşimini değiştirirseniz bölün.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-178">Since COM clients are typically unprepared to handle changes in the layout of an interface, they break if you change the member layout of the class.</span></span>  
  
 <span data-ttu-id="e9bd5-179">Bu kılavuz arabirimler COM istemcilerine maruz değiştirilemez kalması gereken kavram çalışacak şekilde güçlendirir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-179">This guideline reinforces the notion that interfaces exposed to COM clients must remain unchangeable.</span></span> <span data-ttu-id="e9bd5-180">COM istemcileri arabirimi düzenini yanlışlıkla yeniden sıralayarak bozucu riskini azaltmak için tüm değişiklikleri açıkça arabirimleri tanımlayarak sınıfa arabirimi düzenden yalıtın.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-180">To reduce the risk of breaking COM clients by inadvertently reordering the interface layout, isolate all changes to the class from the interface layout by explicitly defining interfaces.</span></span>  
  
 <span data-ttu-id="e9bd5-181">Kullanım **ClassInterfaceAttribute** sınıf arabirimi otomatik olarak oluşturulmasını disengage ve aşağıdaki kod parçasını gösterildiği gibi sınıfın açık bir arabirim uygulamak için:</span><span class="sxs-lookup"><span data-stu-id="e9bd5-181">Use the **ClassInterfaceAttribute** to disengage the automatic generation of the class interface and implement an explicit interface for the class, as the following code fragment shows:</span></span>  
  
```vb  
<ClassInterface(ClassInterfaceType.None)>Public Class LoanApp  
    Implements IExplicit  
    Sub M() Implements IExplicit.M  
…  
End Class  
```  
  
```csharp
[ClassInterface(ClassInterfaceType.None)]
public class LoanApp : IExplicit
{
    int IExplicit.M() { return 0; }
}
```
  
 <span data-ttu-id="e9bd5-182">**ClassInterfaceType.None** değer sınıfı meta veriler için bir tür kitaplığı dışarı aktarılırken oluşturulan sınıf arabirimi engeller.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-182">The **ClassInterfaceType.None** value prevents the class interface from being generated when the class metadata is exported to a type library.</span></span> <span data-ttu-id="e9bd5-183">Önceki örnekte, COM istemcileri erişebilir `LoanApp` aracılığıyla yalnızca sınıf `IExplicit` arabirimi.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-183">In the preceding example, COM clients can access the `LoanApp` class only through the `IExplicit` interface.</span></span>  
  
### <a name="avoid-caching-dispatch-identifiers-dispids"></a><span data-ttu-id="e9bd5-184">Gönderme tanımlayıcıları (DISPID değeri) önbelleğe alma kaçının</span><span class="sxs-lookup"><span data-stu-id="e9bd5-184">Avoid caching dispatch identifiers (DispIds)</span></span>
 <span data-ttu-id="e9bd5-185">Sınıf arabirimi kullanarak, betikleştirilmiş istemcileri, Microsoft Visual Basic 6.0 istemciler veya arabirim üyelerinin DISPID değeri önbelleğe alma herhangi bir geç bağlanan istemci için kabul edilebilir bir seçenektir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-185">Using the class interface is an acceptable option for scripted clients, Microsoft Visual Basic 6.0 clients, or any late-bound client that does not cache the DispIds of interface members.</span></span> <span data-ttu-id="e9bd5-186">DISPID değeri geç bağlama etkinleştirmek için arabirim üyeleri tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-186">DispIds identify interface members to enable late binding.</span></span>  
  
 <span data-ttu-id="e9bd5-187">Sınıf arabirimi için nesil DISPID değeri arabirimin üyesi konumunu temel alır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-187">For the class interface, generation of DispIds is based on the position of the member in the interface.</span></span> <span data-ttu-id="e9bd5-188">Üye sırasını değiştirmek ve sınıfı bir tür kitaplığına aktardığınızdan, sınıf arabirimi içinde oluşturulan DISPID değeri değiştirir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-188">If you change the order of the member and export the class to a type library, you will alter the DispIds generated in the class interface.</span></span>  
  
 <span data-ttu-id="e9bd5-189">Sınıf arabirimi kullanılırken geç bağlanan COM istemcilerini bozmayı önlemek için uygulama **ClassInterfaceAttribute** ile **ClassInterfaceType.AutoDispatch** değeri.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-189">To avoid breaking late-bound COM clients when using the class interface, apply the **ClassInterfaceAttribute** with the **ClassInterfaceType.AutoDispatch** value.</span></span> <span data-ttu-id="e9bd5-190">Bu değer yalnızca gönderme sınıf arabirimi uygular, ancak arabirim açıklaması tür kitaplığındaki atlar.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-190">This value implements a dispatch-only class interface, but omits the interface description from the type library.</span></span> <span data-ttu-id="e9bd5-191">Bir arabirim açıklaması istemciler DISPID değeri, derleme zamanı önbelleğine erişemiyor.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-191">Without an interface description, clients are unable to cache DispIds at compile time.</span></span> <span data-ttu-id="e9bd5-192">Bu sınıf arabirimi için varsayılan arabirim türü olsa da, öznitelik değeri açıkça uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-192">Although this is the default interface type for the class interface, you can apply the attribute value explicitly.</span></span>  
  
```vb  
<ClassInterface(ClassInterfaceType.AutoDispatch)> Public Class LoanApp  
    Implements IAnother  
    Sub M() Implements IAnother.M  
…  
End Class  
```  
  
```csharp
[ClassInterface(ClassInterfaceType.AutoDispatch)]
public class LoanApp
{
    public int M() { return 0; }
}
```
  
 <span data-ttu-id="e9bd5-193">DISPID arabirim üyesini çalışma zamanında almak için COM istemcileri çağırabilirsiniz **IDispatch.GetIdsOfNames**.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-193">To get the DispId of an interface member at run time, COM clients can call **IDispatch.GetIdsOfNames**.</span></span> <span data-ttu-id="e9bd5-194">Arabirimdeki bir yöntem çağırmak için bir bağımsız değişken olarak döndürülen DispId geçirmek **IDispatch.Invoke**.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-194">To invoke a method on the interface, pass the returned DispId as an argument to **IDispatch.Invoke**.</span></span>  
  
### <a name="restrict-using-the-dual-interface-option-for-the-class-interface"></a><span data-ttu-id="e9bd5-195">Sınıf arabirimi için çift arabirim seçeneğini kullanarak kısıtlayın.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-195">Restrict using the dual interface option for the class interface.</span></span>  
 <span data-ttu-id="e9bd5-196">Çift arabirimler COM istemcileri tarafından arabirim üyeleri erken ve geç bağlama etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-196">Dual interfaces enable early and late binding to interface members by COM clients.</span></span> <span data-ttu-id="e9bd5-197">Tasarım zamanında ve test sırasında sınıf arabirimi için çift ayarlamak yararlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-197">At design time and during testing, you might find it useful to set the class interface to dual.</span></span> <span data-ttu-id="e9bd5-198">Yönetilen bir sınıf (ve temel sınıfları) hiçbir zaman olacak değiştirilmiş, bu da kabul edilebilir bir seçenektir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-198">For a managed class (and its base classes) that will never be modified, this option is also acceptable.</span></span> <span data-ttu-id="e9bd5-199">Diğer tüm durumlarda, sınıf arabirimi çift ayarlamaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-199">In all other cases, avoid setting the class interface to dual.</span></span>  
  
 <span data-ttu-id="e9bd5-200">Otomatik olarak oluşturulan bir çift arabirim nadir durumlarda uygun olabilir; Ancak, daha sık bu sürümü ile ilgili karmaşıklığı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-200">An automatically generated dual interface might be appropriate in rare cases; however, more often it creates version-related complexity.</span></span> <span data-ttu-id="e9bd5-201">Örneğin, türetilmiş bir sınıfın sınıf arabirimi kullanarak COM istemcilerinde değişikliklerle kolayca temel sınıfa bozabilir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-201">For example, COM clients using the class interface of a derived class can easily break with changes to the base class.</span></span> <span data-ttu-id="e9bd5-202">Bir üçüncü taraf taban sınıfı sağlar, sınıf arabirimi düzenini denetiminiz dışında değildir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-202">When a third party provides the base class, the layout of the class interface is out of your control.</span></span> <span data-ttu-id="e9bd5-203">Daha fazla, yalnızca gönderme arabirimi çift arabirim (**ClassInterfaceType.AutoDual**) sınıf arabirimi dışarı aktarılan Tür Kitaplığı'nda bir açıklaması verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-203">Further, unlike a dispatch-only interface, a dual interface (**ClassInterfaceType.AutoDual**) provides a description of the class interface in the exported type library.</span></span> <span data-ttu-id="e9bd5-204">Böyle bir açıklamasını, çalışma zamanında önbelleğe DISPID değeri geç bağlanan istemciler teşvik eder.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-204">Such a description encourages late-bound clients to cache DispIds at run time.</span></span>  
  
### <a name="ensure-that-all-com-event-notifications-are-late-bound"></a><span data-ttu-id="e9bd5-205">Tüm COM olay bildirimleri geç bağlanan olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-205">Ensure that all COM event notifications are late-bound.</span></span>

<span data-ttu-id="e9bd5-206">Varsayılan olarak, COM tür bilgilerini doğrudan yönetilen derlemelere, birincil birlikte çalışma derlemeleri (PIA) gereksinimini ortadan kaldırır katıştırılır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-206">By default, COM type information is embedded directly into managed assemblies, which eliminates the need for primary interop assemblies (PIAs).</span></span> <span data-ttu-id="e9bd5-207">Ancak, gömülü tür bilgileri sınırlamaları, vtable erken bağlanan çağrılar tarafından COM olay notiifcations teslimini desteklenmiyor ancak yalnızca geç bağlanan destekler biridir `IDispatch::Invoke` çağırır.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-207">However, one of the limitations of embedded type information is that it does not supported delivery of COM event notiifcations by early-bound vtable calls, but only supports late-bound `IDispatch::Invoke` calls.</span></span>

<span data-ttu-id="e9bd5-208">Uygulamanıza erken bağlanan çağrılar COM olay arabirim yöntemleri için gerekiyorsa ayarlayabileceğiniz **birlikte çalışma türlerini katıştır** özelliği için Visual Studio'da `true`, veya proje dosyanızda aşağıdaki öğeyi ekleyin:</span><span class="sxs-lookup"><span data-stu-id="e9bd5-208">If your application requires early-bound calls to COM event interface methods, you can set the **Embed Interop Types** property in Visual Studio to `true`, or include the following element in your project file:</span></span>

```xml
<EmbedInteropTypes>True</EmbedInteropTypes>
```

## <a name="see-also"></a><span data-ttu-id="e9bd5-209">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e9bd5-209">See also</span></span>
- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="e9bd5-210">COM Sarmalayıcıları</span><span class="sxs-lookup"><span data-stu-id="e9bd5-210">COM Wrappers</span></span>](com-wrappers.md)
- [<span data-ttu-id="e9bd5-211">.NET Framework Bileşenlerini COM'da Gösterme</span><span class="sxs-lookup"><span data-stu-id="e9bd5-211">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="e9bd5-212">Birlikte Çalışma için .NET Türlerini Niteleme</span><span class="sxs-lookup"><span data-stu-id="e9bd5-212">Qualifying .NET Types for Interoperation</span></span>](qualifying-net-types-for-interoperation.md)
- [<span data-ttu-id="e9bd5-213">Çalışma Zamanında Çağrılabilir Sarmalayıcı</span><span class="sxs-lookup"><span data-stu-id="e9bd5-213">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
