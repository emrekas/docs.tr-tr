---
title: 'Nasıl yapılır: -Wave dosyasını oynatmak için Platform çağırma kullanma C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 94c90ed264c40c99b0c139948578c85e8c9855d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696353"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="abdff-102">Nasıl yapılır: Wave dosyasını oynatmak için Platform çağırma kullanma (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="abdff-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="abdff-103">Aşağıdaki C# kod örneği platform kullanılması gösterilmektedir Windows işletim sisteminde ses wave dosyasını oynatmak için hizmetlerini çağırma.</span><span class="sxs-lookup"><span data-stu-id="abdff-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abdff-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="abdff-104">Example</span></span>  
 <span data-ttu-id="abdff-105">Bu kod örneği kullanan `DllImport` içeri aktarmak için `winmm.dll`'s `PlaySound` yöntemi giriş noktası olarak `Form1 PlaySound()`.</span><span class="sxs-lookup"><span data-stu-id="abdff-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="abdff-106">Örneğin, bir düğme içeren basit bir Windows Form vardır.</span><span class="sxs-lookup"><span data-stu-id="abdff-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="abdff-107">Düğmeye tıklandığında, standart windows açılır <xref:System.Windows.Forms.OpenFileDialog> iletişim kutusunu yürütmek için bir dosyayı açabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="abdff-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="abdff-108">Wave dosyasını seçildiğinde kullanarak çalınır `PlaySound()` yöntemi `winmm.dll` kitaplığı.</span><span class="sxs-lookup"><span data-stu-id="abdff-108">When a wave file is selected, it is played by using the `PlaySound()` method of the `winmm.dll` library.</span></span> <span data-ttu-id="abdff-109">Bu yöntem hakkında daha fazla bilgi için bkz: [PlaySound işlevi kullanılarak oluşturulan dalga biçiminin ses dosyaları ile](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span><span class="sxs-lookup"><span data-stu-id="abdff-109">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="abdff-110">Gözat ve .wav uzantılı bir dosya seçin ve ardından **açık** platformu kullanarak wave dosyasını oynatmak için çağırır.</span><span class="sxs-lookup"><span data-stu-id="abdff-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="abdff-111">Bir metin kutusu seçili dosyanın tam yolunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="abdff-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="abdff-112">**Açık dosyalar** iletişim kutusu filtre ayarları aracılığıyla .wav uzantısına sahip dosyaları gösterecek şekilde filtrelenmiştir:</span><span class="sxs-lookup"><span data-stu-id="abdff-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="abdff-113">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="abdff-113">Compiling the Code</span></span>  
  
### <a name="to-compile-the-code"></a><span data-ttu-id="abdff-114">Kodu derlemek için</span><span class="sxs-lookup"><span data-stu-id="abdff-114">To compile the code</span></span>  
  
1.  <span data-ttu-id="abdff-115">Visual Studio'da yeni bir C# Windows uygulaması projesi oluşturun ve adlandırın **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="abdff-115">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2.  <span data-ttu-id="abdff-116">Yukarıdaki kodu kopyalayabilir ve üzerinde içeriğini yapıştırın `Form1.cs` dosya.</span><span class="sxs-lookup"><span data-stu-id="abdff-116">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3.  <span data-ttu-id="abdff-117">Aşağıdaki kodu kopyalayın ve yapıştırın `Form1.Designer.cs` dosyasındaki `InitializeComponent()` yöntemi, mevcut kodlar sonra.</span><span class="sxs-lookup"><span data-stu-id="abdff-117">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  <span data-ttu-id="abdff-118">Derleyin ve kod çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="abdff-118">Compile and run the code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="abdff-119">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="abdff-119">.NET Framework Security</span></span>  
 <span data-ttu-id="abdff-120">Daha fazla bilgi için [.NET içinde güvenlik](../../../standard/security/index.md).</span><span class="sxs-lookup"><span data-stu-id="abdff-120">For more information, see [Security in .NET](../../../standard/security/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abdff-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="abdff-121">See also</span></span>

- [<span data-ttu-id="abdff-122">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="abdff-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="abdff-123">Birlikte Çalışabilirliğe Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="abdff-123">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)
- [<span data-ttu-id="abdff-124">Yakından Platform çağırma</span><span class="sxs-lookup"><span data-stu-id="abdff-124">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="abdff-125">Platform Çağırma ile Veri Hazırlama</span><span class="sxs-lookup"><span data-stu-id="abdff-125">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
