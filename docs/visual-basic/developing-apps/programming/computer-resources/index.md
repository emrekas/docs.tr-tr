---
title: (Visual Basic) bilgisayar kaynaklarına erişme
ms.date: 07/20/2015
helpviewer_keywords:
- computer resources [Visual Basic]
- My.Computer object [Visual Basic], tasks
- computer resources [Visual Basic], accessing
ms.assetid: 75b81c88-f7c0-46e0-95c8-0c006d2120f9
ms.openlocfilehash: 2c53358d483868317887258c92b1aad2d9dcba00
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662685"
---
# <a name="accessing-computer-resources-visual-basic"></a><span data-ttu-id="d390a-102">(Visual Basic) bilgisayar kaynaklarına erişme</span><span class="sxs-lookup"><span data-stu-id="d390a-102">Accessing computer resources (Visual Basic)</span></span>

<span data-ttu-id="d390a-103">`My.Computer` Nesnedir üç merkezi nesnelerden birinde `My`, işlevselliği erişim bilgileri ve yaygın olarak kullanılan sağlanması.</span><span class="sxs-lookup"><span data-stu-id="d390a-103">The `My.Computer` object is one of the three central objects in `My`, providing access to information and commonly used functionality.</span></span> <span data-ttu-id="d390a-104">`My.Computer` uygulamanın üzerinde çalıştığı bilgisayar erişmek için yöntemler, özellikler ve olaylar sağlar.</span><span class="sxs-lookup"><span data-stu-id="d390a-104">`My.Computer` provides methods, properties, and events for accessing the computer on which the application is running.</span></span> <span data-ttu-id="d390a-105">Nesnelerini içerir:</span><span class="sxs-lookup"><span data-stu-id="d390a-105">Its objects include:</span></span>  
  
- <xref:Microsoft.VisualBasic.Devices.Audio>
- <span data-ttu-id="d390a-106">Pano (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span><span class="sxs-lookup"><span data-stu-id="d390a-106">Clipboard (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span></span>
- <xref:Microsoft.VisualBasic.Devices.Clock>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>
- <xref:Microsoft.VisualBasic.Devices.Keyboard>
- <xref:Microsoft.VisualBasic.Devices.Mouse>
- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Ports>
- <span data-ttu-id="d390a-107">Registry (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span><span class="sxs-lookup"><span data-stu-id="d390a-107">Registry (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d390a-108">Bu bölümde</span><span class="sxs-lookup"><span data-stu-id="d390a-108">In this section</span></span>

<span data-ttu-id="d390a-109">[Ses çalma](../../../../visual-basic/developing-apps/programming/computer-resources/playing-sounds.md) </span><span class="sxs-lookup"><span data-stu-id="d390a-109">[Playing Sounds](../../../../visual-basic/developing-apps/programming/computer-resources/playing-sounds.md) </span></span>  
<span data-ttu-id="d390a-110">Listeler ile ilişkili görevleri `My.Computer.Audio`, arka planda bir ses çalma gibi.</span><span class="sxs-lookup"><span data-stu-id="d390a-110">Lists tasks associated with `My.Computer.Audio`, such as playing a sound in the background.</span></span>

<span data-ttu-id="d390a-111">[Verileri Panoda depolama ve panodan okuma](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md) </span><span class="sxs-lookup"><span data-stu-id="d390a-111">[Storing Data to and Reading from the Clipboard](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md) </span></span>  
<span data-ttu-id="d390a-112">Listeler ile ilişkili görevleri `My.Computer.Clipboard`verileri okuma veya verileri panoya yazma gibi.</span><span class="sxs-lookup"><span data-stu-id="d390a-112">Lists tasks associated with `My.Computer.Clipboard`, such as reading data from or writing data to the Clipboard.</span></span>

<span data-ttu-id="d390a-113">[Bilgisayar hakkında bilgi alma](../../../../visual-basic/developing-apps/programming/computer-resources/getting-information-about-the-computer.md) </span><span class="sxs-lookup"><span data-stu-id="d390a-113">[Getting Information about the Computer](../../../../visual-basic/developing-apps/programming/computer-resources/getting-information-about-the-computer.md) </span></span>  
<span data-ttu-id="d390a-114">Listeler ile ilişkili görevleri `My.Computer.Info`, bir bilgisayarın tam adı veya IP adreslerini belirleme gibi.</span><span class="sxs-lookup"><span data-stu-id="d390a-114">Lists tasks associated with `My.Computer.Info`, such as determining a computer's full name or IP addresses.</span></span>

<span data-ttu-id="d390a-115">[Klavyeye erişme](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="d390a-115">[Accessing the Keyboard](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md) </span></span>  
<span data-ttu-id="d390a-116">Listeler ile ilişkili görevleri `My.Computer.Keyboard`, CAPS LOCK açık olup olmadığını belirleme gibi.</span><span class="sxs-lookup"><span data-stu-id="d390a-116">Lists tasks associated with `My.Computer.Keyboard`, such as determining whether CAPS LOCK is on.</span></span>

<span data-ttu-id="d390a-117">[Fareye erişme](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md) </span><span class="sxs-lookup"><span data-stu-id="d390a-117">[Accessing the Mouse](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md) </span></span>  
<span data-ttu-id="d390a-118">Listeler ile ilişkili görevleri `My.Computer.Mouse`, fare var olup olmadığını belirleme gibi.</span><span class="sxs-lookup"><span data-stu-id="d390a-118">Lists tasks associated with `My.Computer.Mouse`, such as determining whether a mouse is present.</span></span>

<span data-ttu-id="d390a-119">[Ağ işlemlerini gerçekleştirme](../../../../visual-basic/developing-apps/programming/computer-resources/performing-network-operations.md) </span><span class="sxs-lookup"><span data-stu-id="d390a-119">[Performing Network Operations](../../../../visual-basic/developing-apps/programming/computer-resources/performing-network-operations.md) </span></span>  
<span data-ttu-id="d390a-120">Listeler ile ilişkili görevleri `My.Computer.Network`yükleme veya dosya indirme gibi.</span><span class="sxs-lookup"><span data-stu-id="d390a-120">Lists tasks associated with `My.Computer.Network`, such as uploading or downloading files.</span></span>

<span data-ttu-id="d390a-121">[Bilgisayar bağlantı noktalarına erişme](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md) </span><span class="sxs-lookup"><span data-stu-id="d390a-121">[Accessing the Computer's Ports](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md) </span></span>  
<span data-ttu-id="d390a-122">Listeler ile ilişkili görevleri `My.Computer.Ports`kullanılabilir seri bağlantı noktalarını gösteren veya seri bağlantı noktalarına dizeler gönderme gibi.</span><span class="sxs-lookup"><span data-stu-id="d390a-122">Lists tasks associated with `My.Computer.Ports`, such as showing available serial ports or sending strings to serial ports.</span></span>

<span data-ttu-id="d390a-123">[Okuma ve kayıt defterine yazma](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="d390a-123">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
<span data-ttu-id="d390a-124">Listeler ile ilişkili görevleri `My.Computer.Registry`verileri okuma veya kayıt defteri anahtarları için verileri yazma gibi.</span><span class="sxs-lookup"><span data-stu-id="d390a-124">Lists tasks associated with `My.Computer.Registry`, such as reading data from or writing data to registry keys.</span></span>
