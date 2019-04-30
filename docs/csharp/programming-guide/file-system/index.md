---
title: Dosya sistemi ve kayıt defteri - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 64c852e6fcc034cb56651ffc2d22fa5323bbb54f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61680070"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="97a1f-102">Dosya Sistemi ve Kayıt Defteri (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="97a1f-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="97a1f-103">Aşağıdaki konular, C# ve .NET Framework dosyaları, klasörleri ve kayıt defteri çeşitli temel işlemleri gerçekleştirmek için nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="97a1f-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="97a1f-104">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="97a1f-104">In This Section</span></span>  
  
|<span data-ttu-id="97a1f-105">**Başlık**</span><span class="sxs-lookup"><span data-stu-id="97a1f-105">**Title**</span></span>|<span data-ttu-id="97a1f-106">**Açıklama**</span><span class="sxs-lookup"><span data-stu-id="97a1f-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="97a1f-107">Nasıl yapılır: Bir dizin ağacı ile yineleme</span><span class="sxs-lookup"><span data-stu-id="97a1f-107">How to: Iterate Through a Directory Tree</span></span>](../../../csharp/programming-guide/file-system/how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="97a1f-108">El ile bir dizin ağacı ile yineleme işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="97a1f-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="97a1f-109">Nasıl yapılır: Dosyalar, klasörler ve sürücüler hakkında bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="97a1f-109">How to: Get Information About Files, Folders, and Drives</span></span>](../../../csharp/programming-guide/file-system/how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="97a1f-110">Dosyalar, klasörler ve sürücüler hakkında bilgi oluşturma sürelerini ve boyutu gibi alma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="97a1f-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="97a1f-111">Nasıl yapılır: Bir dosya veya klasör oluşturma</span><span class="sxs-lookup"><span data-stu-id="97a1f-111">How to: Create a File or Folder</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-file-or-folder.md)|<span data-ttu-id="97a1f-112">Yeni dosya veya klasör oluşturma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="97a1f-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="97a1f-113">Nasıl yapılır: Kopyalama, silme ve taşıma dosya ve klasörleri (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="97a1f-113">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="97a1f-114">Kopyalama, silme ve dosya ve klasörleri taşıma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="97a1f-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="97a1f-115">Nasıl yapılır: Dosya işlemleri için ilerleme durumu iletişim kutusu sağlama</span><span class="sxs-lookup"><span data-stu-id="97a1f-115">How to: Provide a Progress Dialog Box for File Operations</span></span>](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="97a1f-116">Belirli dosya işlemleri için standart bir Windows ilerleme durumu iletişim kutusu görüntüleme işlemini göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="97a1f-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="97a1f-117">Nasıl yapılır: Bir metin dosyasına yazma</span><span class="sxs-lookup"><span data-stu-id="97a1f-117">How to: Write to a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)|<span data-ttu-id="97a1f-118">Bir metin dosyasına yazma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="97a1f-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="97a1f-119">Nasıl yapılır: Bir metin dosyasından okuma</span><span class="sxs-lookup"><span data-stu-id="97a1f-119">How to: Read From a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-read-from-a-text-file.md)|<span data-ttu-id="97a1f-120">Bir metin dosyasından okuma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="97a1f-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="97a1f-121">Nasıl yapılır: Bir kerede bir metin dosyası bir satırı okuyun</span><span class="sxs-lookup"><span data-stu-id="97a1f-121">How to: Read a Text File One Line at a Time</span></span>](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="97a1f-122">Metin dosyası bir satırından teker teker alma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="97a1f-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="97a1f-123">Nasıl yapılır: Kayıt defterinde anahtar oluşturma</span><span class="sxs-lookup"><span data-stu-id="97a1f-123">How to: Create a Key In the Registry</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="97a1f-124">Sistem kayıt defterine bir anahtar yazma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="97a1f-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="97a1f-125">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="97a1f-125">Related Sections</span></span>  
 [<span data-ttu-id="97a1f-126">Dosya ve Akış G/Ç'si</span><span class="sxs-lookup"><span data-stu-id="97a1f-126">File and Stream I/O</span></span>](../../../standard/io/index.md)  
  
 [<span data-ttu-id="97a1f-127">Nasıl yapılır: Kopyalama, silme ve taşıma dosya ve klasörleri (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="97a1f-127">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)  
  
 [<span data-ttu-id="97a1f-128">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="97a1f-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
  
 [<span data-ttu-id="97a1f-129">Dosyalar, klasörler ve sürücüler</span><span class="sxs-lookup"><span data-stu-id="97a1f-129">Files, Folders and Drives</span></span>](../../../csharp/programming-guide/file-system/index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
