---
title: -bağlantı (C# Derleyici Seçenekleri)
ms.date: 07/20/2015
helpviewer_keywords:
- /l compiler option [C#]
- /link compiler option [C#]
- -l compiler option [C#]
- EmbedInteropTypes
- l compiler option [C#]
- embed interop types [COM Interop]
- -link compiler option [C#]
- link compiler option [C#]
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
ms.openlocfilehash: 049d1ce7a27a812b58fb09802e1ce520e96ed925
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586024"
---
# <a name="-link-c-compiler-options"></a><span data-ttu-id="ac7bf-102">-bağlantı (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="ac7bf-102">-link (C# Compiler Options)</span></span>
<span data-ttu-id="ac7bf-103">Derleyici COM tür bilgilerini belirli derlemelerde şu anda derleme proje kullanılabilir hale getirmek neden olur.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac7bf-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ac7bf-104">Syntax</span></span>  
  
```console  
-link:fileList  
// -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac7bf-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="ac7bf-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="ac7bf-106">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-106">Required.</span></span> <span data-ttu-id="ac7bf-107">Derleme dosya adlarının virgülle ayrılmış liste.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-107">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="ac7bf-108">Dosya adı boşluk içeriyorsa adı tırnak içine alın.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-108">If the file name contains a space, enclose the name in quotation marks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac7bf-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ac7bf-109">Remarks</span></span>  
 <span data-ttu-id="ac7bf-110">`-link` Seçeneği, gömülü tür bilgileri içeren bir uygulama dağıtmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-110">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="ac7bf-111">Uygulama, daha sonra bir çalışma zamanı derlemesindeki gömülü tür bilgileri, çalışma zamanı derlemeye bir başvuruda gerek kalmadan uygulayan türler kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-111">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="ac7bf-112">Çeşitli çalışma zamanı derleme sürümleri yayımladıysanız, gömülü tür bilgileri içeren uygulama derlenmesi gerek kalmadan çeşitli sürümleriyle çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-112">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="ac7bf-113">Bir örnek için bkz [izlenecek yol: Yönetilen derlemeler türler katıştırma](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ac7bf-113">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md).</span></span>  
  
 <span data-ttu-id="ac7bf-114">Kullanarak `-link` COM birlikte çalışma ile çalışırken seçenek özellikle yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-114">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="ac7bf-115">Uygulamanız artık hedef bilgisayarda birincil birlikte çalışma derlemesi (PIA) gerektirmemesi için COM türlerini ekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-115">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="ac7bf-116">`-link` Başvurulan birlikte çalışma bütünleştirilmiş kod içine ortaya çıkan derlenmiş kodu COM tür bilgilerini katıştırma derleyici seçeneği bildirir.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-116">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="ac7bf-117">COM türü (GUID) CLSID değeri tarafından tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-117">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="ac7bf-118">Sonuç olarak, uygulamanızı aynı COM türlerini aynı CLSID değerlerle yüklü olduğu bir hedef bilgisayarda çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-118">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="ac7bf-119">Microsoft Office otomatikleştirmek uygulamaların iyi bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-119">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="ac7bf-120">Office gibi uygulamalarda, genellikle aynı CLSID değeri farklı sürümler arasında tutmak olduğundan, uygulamanızı başvurulan COM türlerini uzun olarak .NET Framework 4 veya daha sonra hedef bilgisayarda yüklü olduğundan ve yöntemler, özellikler, uygulamanızın kullandığı gibi kullanabilirsiniz veya Başvurulan COM türlerini dahil edilen olaylar.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-120">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="ac7bf-121">`-link` Seçeneği yalnızca arabirimleri, yapılar ve temsilciler ekler.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-121">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="ac7bf-122">COM sınıfları ekleme desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-122">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac7bf-123">Kodunuzda katıştırılmış bir COM türün örneğini oluşturduğunuzda, uygun arabirimini kullanarak örneği oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-123">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="ac7bf-124">Coclass'ı kullanarak katıştırılmış bir COM tür örneği oluşturulmaya çalışılırken bir hata oluşur.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-124">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="ac7bf-125">Ayarlanacak `-link` seçeneğini Visual Studio'da ve bir bütünleştirilmiş kod Başvurusu Ekle `Embed Interop Types` özelliğini **true**.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-125">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="ac7bf-126">İçin varsayılan `Embed Interop Types` özelliği **false**.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-126">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="ac7bf-127">Bir COM derlemesine (bütünleştirilmiş kod: A) bağlarsanız kendisi başka bir COM derlemesine (derleme B) başvuruda, aşağıdakilerden biri doğruysa, derleme B bağlamak de:</span><span class="sxs-lookup"><span data-stu-id="ac7bf-127">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
- <span data-ttu-id="ac7bf-128">Bir derlemeden bir tür bir tür tarafından devralındığında veya derleme B'deki bir arabirim uygular.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-128">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="ac7bf-129">Bir alan, özelliği, olay veya dönüş türü veya parametresi türü derleme b olan yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-129">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="ac7bf-130">Gibi [-başvuru](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) derleyici seçeneği `-link` derleyici seçeneği, sık kullanılan .NET Framework derlemelerine başvuran Csc.rsp yanıt dosyası kullanır.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-130">Like the [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option, the `-link` compiler option uses the Csc.rsp response file, which references frequently used .NET Framework assemblies.</span></span> <span data-ttu-id="ac7bf-131">Kullanma [- noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) Csc.rsp dosyasını kullanmak için derleyicinin istemiyorsanız derleyici seçeneği.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-131">Use the [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) compiler option if you do not want the compiler to use the Csc.rsp file.</span></span>  
  
 <span data-ttu-id="ac7bf-132">Kısa formunu da `-link` olduğu `-l`.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-132">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="ac7bf-133">Genel türler ve gömülü türleri</span><span class="sxs-lookup"><span data-stu-id="ac7bf-133">Generics and Embedded Types</span></span>  
 <span data-ttu-id="ac7bf-134">Aşağıdaki bölümlerde, genel türleri kullanarak birlikte çalışma türlerini katıştır uygulamalarda sınırlamaları açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-134">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="ac7bf-135">Genel Arabirimler</span><span class="sxs-lookup"><span data-stu-id="ac7bf-135">Generic Interfaces</span></span>  
 <span data-ttu-id="ac7bf-136">Gömülü birlikte çalışma derlemesi genel arabirimler kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-136">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="ac7bf-137">Bu, aşağıdaki örnekte gösterilir.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-137">This is shown in the following example.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#1)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="ac7bf-138">Genel parametre türleri</span><span class="sxs-lookup"><span data-stu-id="ac7bf-138">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="ac7bf-139">Genel parametre türü bir birlikte çalışma derlemesi katıştırılmış türleri, dış bütünleştirilmiş koddan tür olan kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-139">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="ac7bf-140">Bu kısıtlama, arabirimler için geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-140">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="ac7bf-141">Örneğin, düşünün <xref:Microsoft.Office.Interop.Excel.Range> tanımlanan arabirimi <xref:Microsoft.Office.Interop.Excel> derleme.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-141">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="ac7bf-142">Birlikte çalışma türleri bir kitaplığını katıştırır, <xref:Microsoft.Office.Interop.Excel> bütünleştirilmiş kod ve türü olan bir parametreye sahip genel bir tür döndüren bir yöntem sunarsa <xref:Microsoft.Office.Interop.Excel.Range> arabirim yöntemi aşağıdaki kod örneğinde gösterildiği gibi genel bir arabirim döndürmelidir.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-142">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs#2)]  
[!code-csharp[VbLinkCompilerCS#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs#3)]  
[!code-csharp[VbLinkCompilerCS#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs#4)]  
  
 <span data-ttu-id="ac7bf-143">Aşağıdaki örnekte, istemci kodu döndüren yöntem çağırabilirsiniz <xref:System.Collections.IList> hatasız genel arabirim.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-143">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#5)]  
  
## <a name="example"></a><span data-ttu-id="ac7bf-144">Örnek</span><span class="sxs-lookup"><span data-stu-id="ac7bf-144">Example</span></span>  
 <span data-ttu-id="ac7bf-145">Aşağıdaki kod, kaynak dosyasını derler `OfficeApp.cs` ve başvuru derlemeleri `COMData1.dll` ve `COMData2.dll` üretmek için `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-145">The following code compiles source file `OfficeApp.cs` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```csharp  
csc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac7bf-146">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ac7bf-146">See also</span></span>

- [<span data-ttu-id="ac7bf-147">C# Derleyici Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="ac7bf-147">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="ac7bf-148">İzlenecek yol: Yönetilen derlemelerden türler katıştırma</span><span class="sxs-lookup"><span data-stu-id="ac7bf-148">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)
- [<span data-ttu-id="ac7bf-149">-başvurusu (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="ac7bf-149">-reference (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)
- [<span data-ttu-id="ac7bf-150">-noconfig (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="ac7bf-150">-noconfig (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)
- [<span data-ttu-id="ac7bf-151">csc.exe Kullanarak Komut Satırı Derleme</span><span class="sxs-lookup"><span data-stu-id="ac7bf-151">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="ac7bf-152">Birlikte Çalışabilirliğe Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="ac7bf-152">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)
