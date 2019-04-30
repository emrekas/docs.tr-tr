---
title: 'İzlenecek yol: Kullanarak bir nesneyi kalıcı kılmaC#'
ms.date: 04/26/2018
ms.openlocfilehash: 85b58e93d667d39800538bb2c29d4ba69146e7f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61680590"
---
# <a name="walkthrough-persisting-an-object-using-c"></a><span data-ttu-id="64ddb-102">İzlenecek yol: C kullanarak bir nesneyi kalıcı kılma\#</span><span class="sxs-lookup"><span data-stu-id="64ddb-102">Walkthrough: persisting an object using C\#</span></span>

<span data-ttu-id="64ddb-103">Seri hale getirme, bir nesnenin veri değerleri depolamak ve bunları nesnesi örneği başlatıldığında almanıza imkan tanıyan örnekler arasında kalıcı hale getirmek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="64ddb-103">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>

<span data-ttu-id="64ddb-104">Bu kılavuzda, bir temel oluşturacak `Loan` nesne ve verileri bir dosyaya kalıcı.</span><span class="sxs-lookup"><span data-stu-id="64ddb-104">In this walkthrough, you will create a basic `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="64ddb-105">Nesne yeniden oluşturduğunuzda dosyadan verileri ardından alır.</span><span class="sxs-lookup"><span data-stu-id="64ddb-105">You will then retrieve the data from the file when you re-create the object.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64ddb-106">Bu örnek, bir dosya zaten mevcut değilse yeni bir dosya oluşturur.</span><span class="sxs-lookup"><span data-stu-id="64ddb-106">This example creates a new file if the file does not already exist.</span></span> <span data-ttu-id="64ddb-107">Bir uygulama bir dosya oluşturmanız gerekiyorsa, bu uygulamanın olmalıdır `Create` klasörüne izni.</span><span class="sxs-lookup"><span data-stu-id="64ddb-107">If an application must create a file, that application must have `Create` permission for the folder.</span></span> <span data-ttu-id="64ddb-108">İzinler, erişim denetim listeleri kullanılarak ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="64ddb-108">Permissions are set by using access control lists.</span></span> <span data-ttu-id="64ddb-109">Dosya zaten varsa, uygulamanın yalnızca ihtiyacı `Write` izin, daha düşük bir izni.</span><span class="sxs-lookup"><span data-stu-id="64ddb-109">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="64ddb-110">Mümkün olan yerlerde, dosyayı dağıtım sırasında oluşturmak ve yalnızca daha güvenli olan `Read` izinleri tek bir dosya (yerine bir klasörün izinlerini oluşturma).</span><span class="sxs-lookup"><span data-stu-id="64ddb-110">Where possible, it's more secure to create the file during deployment and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="64ddb-111">Ayrıca, kök klasöre veya Program dosyaları klasörüne kullanıcı klasörleri verileri yazmak amacıyla daha güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="64ddb-111">Also, it's more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64ddb-112">Bu örnek, verileri bir ikili biçimi dosyasında depolar.</span><span class="sxs-lookup"><span data-stu-id="64ddb-112">This example stores data in a binary format file.</span></span> <span data-ttu-id="64ddb-113">Bu biçimler, parolalar veya kredi kartı bilgileri gibi hassas veriler için kullanılmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="64ddb-113">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="64ddb-114">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="64ddb-114">Prerequisites</span></span>

* <span data-ttu-id="64ddb-115">Derlemek ve çalıştırmak için yükleme [.NET Core SDK'sı](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="64ddb-115">To build and run, install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="64ddb-116">Henüz yapmadıysanız, sık kullandığınız kod düzenleyicinize yükleyin.</span><span class="sxs-lookup"><span data-stu-id="64ddb-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="64ddb-117">Bir kod Düzenleyicisi'ni yüklemeniz gerekir?</span><span class="sxs-lookup"><span data-stu-id="64ddb-117">Need to install a code editor?</span></span> <span data-ttu-id="64ddb-118">Deneyin [Visual Studio](https://visualstudio.com/downloads)!</span><span class="sxs-lookup"><span data-stu-id="64ddb-118">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

* <span data-ttu-id="64ddb-119">Örnek C# 7.3 gerektirir.</span><span class="sxs-lookup"><span data-stu-id="64ddb-119">The example requires C# 7.3.</span></span> <span data-ttu-id="64ddb-120">Bkz: [C# dil sürümünü seçin](../../../language-reference/configure-language-version.md)</span><span class="sxs-lookup"><span data-stu-id="64ddb-120">See [Select the C# language version](../../../language-reference/configure-language-version.md)</span></span> 

<span data-ttu-id="64ddb-121">Örnek kodu inceleyebilirsiniz [.NET örnekleri GitHub deposunda](https://github.com/dotnet/samples/tree/master/csharp/serialization).</span><span class="sxs-lookup"><span data-stu-id="64ddb-121">You can examine the sample code online [at the .NET samples GitHub repository](https://github.com/dotnet/samples/tree/master/csharp/serialization).</span></span>

## <a name="creating-the-loan-object"></a><span data-ttu-id="64ddb-122">Kredi nesnesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="64ddb-122">Creating the loan object</span></span>

<span data-ttu-id="64ddb-123">İlk adım oluşturmaktır bir `Loan` sınıfı ve sınıfını kullanan bir konsol uygulaması:</span><span class="sxs-lookup"><span data-stu-id="64ddb-123">The first step is to create a `Loan` class and a console application that uses the class:</span></span>

1. <span data-ttu-id="64ddb-124">Yeni bir uygulama oluşturun.</span><span class="sxs-lookup"><span data-stu-id="64ddb-124">Create a new application.</span></span> <span data-ttu-id="64ddb-125">Tür `dotnet new console -o serialization` adlı bir alt dizinde yeni bir konsol uygulaması oluşturmak için `serialization`.</span><span class="sxs-lookup"><span data-stu-id="64ddb-125">Type `dotnet new console -o serialization` to create a new console application in a subdirectory named `serialization`.</span></span>
1. <span data-ttu-id="64ddb-126">Uygulama düzenleyicinizde açın ve adlı yeni bir sınıf ekleyin `Loan.cs`.</span><span class="sxs-lookup"><span data-stu-id="64ddb-126">Open the application in your editor, and add a new class named `Loan.cs`.</span></span>
1. <span data-ttu-id="64ddb-127">Aşağıdaki kodu ekleyin, `Loan` sınıfı:</span><span class="sxs-lookup"><span data-stu-id="64ddb-127">Add the following code to your `Loan` class:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/csharp/serialization/Loan.cs#1)]

<span data-ttu-id="64ddb-128">Ayrıca kullanan bir uygulama oluşturmanız gerekir `Loan` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="64ddb-128">You will also have to create an application that uses the `Loan` class.</span></span>

## <a name="serialize-the-loan-object"></a><span data-ttu-id="64ddb-129">Kredi nesne seri hale getirme</span><span class="sxs-lookup"><span data-stu-id="64ddb-129">Serialize the loan object</span></span>

1. <span data-ttu-id="64ddb-130">Açık `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="64ddb-130">Open `Program.cs`.</span></span> <span data-ttu-id="64ddb-131">Aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="64ddb-131">Add the following code:</span></span>

[!code-csharp[Create a loan object](../../../../../samples/csharp/serialization/Program.cs#1)]

<span data-ttu-id="64ddb-132">İçin bir olay işleyicisi ekleme `PropertyChanged` olay ve değiştirmek için birkaç satır kod `Loan` nesne ve değişiklikleri görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="64ddb-132">Add an event handler for the `PropertyChanged` event, and a few lines to modify the `Loan` object and display the changes.</span></span> <span data-ttu-id="64ddb-133">Aşağıdaki kodda eklemeleri görebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="64ddb-133">You can see the additions in the following code:</span></span>

[!code-csharp[Listening for the PropertyChanged event](../../../../../samples/csharp/serialization/Program.cs#2)]

<span data-ttu-id="64ddb-134">Bu noktada, kodu çalıştırmak ve geçerli bir çıktı görürsünüz:</span><span class="sxs-lookup"><span data-stu-id="64ddb-134">At this point, you can run the code, and see the current output:</span></span>

```console
New customer value: Henry Clay
7.5
7.1
```

<span data-ttu-id="64ddb-135">Art arda her zaman bu uygulamayı çalıştıran değerlerine yazar.</span><span class="sxs-lookup"><span data-stu-id="64ddb-135">Running this application repeatedly always writes the same values.</span></span> <span data-ttu-id="64ddb-136">Programı her çalıştırdığınızda, yeni bir kredi nesnesi oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="64ddb-136">A new Loan object is created every time you run the program.</span></span> <span data-ttu-id="64ddb-137">Gerçek dünyada, uygulama her çalıştırıldığında düzenli aralıklarla ancak bu şart değildir faiz oranları değiştirin.</span><span class="sxs-lookup"><span data-stu-id="64ddb-137">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="64ddb-138">Serileştirme kodu, uygulama örnekleri arasında en son faiz oranını korumak anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="64ddb-138">Serialization code means you preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="64ddb-139">Sonraki adımda, yalnızca kredi sınıfı seri hale getirme ekleyerek bunu.</span><span class="sxs-lookup"><span data-stu-id="64ddb-139">In the next step, you will do just that by adding serialization to the Loan class.</span></span>

## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="64ddb-140">Nesne kalıcı hale getirmek için serileştirme kullanma</span><span class="sxs-lookup"><span data-stu-id="64ddb-140">Using Serialization to Persist the Object</span></span>

<span data-ttu-id="64ddb-141">Kredi sınıfı değerlerini kalıcı hale getirmek için önce sınıfıyla işaretlemelisiniz `Serializable` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="64ddb-141">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span> <span data-ttu-id="64ddb-142">Yukarıda kredi sınıf tanımına aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="64ddb-142">Add the following code above the Loan class definition:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/csharp/serialization/Loan.cs#2)]

<span data-ttu-id="64ddb-143"><xref:System.SerializableAttribute> Sınıftaki her şeyi bir dosyaya kalıcı olduğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="64ddb-143">The <xref:System.SerializableAttribute> tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="64ddb-144">Çünkü `PropertyChanged` olay temsil depolanmalıdır nesne grafiğinin parçası, sıralanmamış.</span><span class="sxs-lookup"><span data-stu-id="64ddb-144">Because the `PropertyChanged` event does not represent part of the object graph that should be stored, it should not be serialized.</span></span> <span data-ttu-id="64ddb-145">Bunun yapılması, bu olaya bağlı tüm nesnelerini seri hale getirmek.</span><span class="sxs-lookup"><span data-stu-id="64ddb-145">Doing so would serialize all objects that are attached to that event.</span></span> <span data-ttu-id="64ddb-146">Ekleyebileceğiniz <xref:System.NonSerializedAttribute> için alan bildirimini için `PropertyChanged` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="64ddb-146">You can add the <xref:System.NonSerializedAttribute> to the field declaration for the `PropertyChanged` event handler.</span></span>

[!code-csharp[Disable serialization for the event handler](../../../../../samples/csharp/serialization/Loan.cs#3)]

<span data-ttu-id="64ddb-147">C# 7.3 ile başlayarak, öznitelikleri kullanarak bir otomatik uygulanan özellik, yedekleme alanını ekleyebilirsiniz `field` hedef değer.</span><span class="sxs-lookup"><span data-stu-id="64ddb-147">Beginning with C# 7.3, you can attach attributes to the backing field of an auto-implemented property using the `field` target value.</span></span> <span data-ttu-id="64ddb-148">Aşağıdaki kodu ekler bir `TimeLastLoaded` özelliği ve nelze serializovat olarak işaretler:</span><span class="sxs-lookup"><span data-stu-id="64ddb-148">The following code adds a `TimeLastLoaded` property and marks it as not serializable:</span></span>

[!code-csharp[Disable serialization for an auto-implemented property](../../../../../samples/csharp/serialization/Loan.cs#4)]

<span data-ttu-id="64ddb-149">Sonraki adım, LoanApp uygulamaya serileştirme kodu eklemektir.</span><span class="sxs-lookup"><span data-stu-id="64ddb-149">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="64ddb-150">Sınıf seri hale getirmek ve bir dosyaya yazmak için kullanmanız <xref:System.IO> ve <xref:System.Runtime.Serialization.Formatters.Binary> ad alanları.</span><span class="sxs-lookup"><span data-stu-id="64ddb-150">In order to serialize the class and write it to a file, you use the <xref:System.IO> and <xref:System.Runtime.Serialization.Formatters.Binary> namespaces.</span></span> <span data-ttu-id="64ddb-151">Tam nitelikli adlarını yazarak önlemek için aşağıdaki kodda gösterildiği gibi gerekli ad alanlarına başvurular ekleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="64ddb-151">To avoid typing the fully qualified names, you can add references to the necessary namespaces as shown in the following code:</span></span>

[!code-csharp[Adding namespaces for serialization](../../../../../samples/csharp/serialization/Program.cs#3)]

<span data-ttu-id="64ddb-152">Sonraki adım, bir nesne oluşturulduğunda dosyasından nesnesi seri durumdan çıkarılacak kod eklemektir.</span><span class="sxs-lookup"><span data-stu-id="64ddb-152">The next step is to add code to deserialize the object from the file when the object is created.</span></span> <span data-ttu-id="64ddb-153">Sınıfına aşağıdaki kodda gösterildiği gibi seri hale getirilmiş veri dosya adı için bir sabit ekleyin:</span><span class="sxs-lookup"><span data-stu-id="64ddb-153">Add a constant to the class for the serialized data's file name as shown in the following code:</span></span>

[!code-csharp[Define the name of the saved file](../../../../../samples/csharp/serialization/Program.cs#4)]

<span data-ttu-id="64ddb-154">Ardından, aşağıdaki kodu oluşturan bir satırın sonunda ekleyin `TestLoan` nesnesi:</span><span class="sxs-lookup"><span data-stu-id="64ddb-154">Next, add the following code after the line that creates the `TestLoan` object:</span></span>

[!code-csharp[Read from a file if it exists](../../../../../samples/csharp/serialization/Program.cs#5)]

<span data-ttu-id="64ddb-155">İlk dosyasının varolduğunu işaretlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="64ddb-155">You first must check that the file exists.</span></span> <span data-ttu-id="64ddb-156">Yoksa, oluşturun bir <xref:System.IO.Stream> ikili dosyayı okumak için sınıf ve <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> dosya çevirmek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="64ddb-156">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="64ddb-157">Ayrıca akış türünden kredi nesne türüne dönüştürmek gerekir.</span><span class="sxs-lookup"><span data-stu-id="64ddb-157">You also need to convert from the stream type to the Loan object type.</span></span>

<span data-ttu-id="64ddb-158">Sonraki sınıfı bir dosyaya serileştirmek için kod eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="64ddb-158">Next you must add code to serialize the class to a file.</span></span> <span data-ttu-id="64ddb-159">Varolan kod içine aşağıdaki kodu ekleyin `Main` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="64ddb-159">Add the following code after the existing code in the `Main` method:</span></span>

[!code-csharp[Save the existing Loan object](../../../../../samples/csharp/serialization/Program.cs#6)]

<span data-ttu-id="64ddb-160">Bu noktada, yeniden derleyebilir ve uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="64ddb-160">At this point, you can again build and run the application.</span></span> <span data-ttu-id="64ddb-161">İlk kez çalıştığında, faiz oranları 7.5 başlar ve ardından 7.1 için değişiklikleri dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="64ddb-161">The first time it runs, notice that the interest rates starts at 7.5, and then changes to 7.1.</span></span> <span data-ttu-id="64ddb-162">Uygulamayı kapatın ve yeniden çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="64ddb-162">Close the application and then run it again.</span></span> <span data-ttu-id="64ddb-163">Şimdi uygulamayı kaydedilen dosyayı okudu ve 7.1 bile, değişiklikleri kodundan önce faiz oranını olduğundan ileti yazdırır.</span><span class="sxs-lookup"><span data-stu-id="64ddb-163">Now, the application prints the message that it has read the saved file, and the interest rate is 7.1 even before the code that changes it.</span></span>

## <a name="see-also"></a><span data-ttu-id="64ddb-164">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="64ddb-164">See also</span></span>

- [<span data-ttu-id="64ddb-165">Seri hale getirme (C#)</span><span class="sxs-lookup"><span data-stu-id="64ddb-165">Serialization (C#)</span></span>](index.md)
- [<span data-ttu-id="64ddb-166">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="64ddb-166">C# Programming Guide</span></span>](../..//index.md)
