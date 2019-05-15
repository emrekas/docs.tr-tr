---
title: Sürücüleri, Dizinleri ve Dosyaları İşleme (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- drives
- drives, processing
- Visual Basic code, file access
- files [Visual Basic], processing
- files [Visual Basic], accessing
- directories [Visual Studio], processing
ms.assetid: f1db14c8-a4fd-4d0b-8323-c7cb29d688c2
ms.openlocfilehash: 7c0e412f9b9ccb8d425aae1e3985e7492e452fd9
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593396"
---
# <a name="processing-drives-directories-and-files-visual-basic"></a><span data-ttu-id="f5b40-102">Sürücüleri, Dizinleri ve Dosyaları İşleme (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5b40-102">Processing Drives, Directories, and Files (Visual Basic)</span></span>
<span data-ttu-id="f5b40-103">Visual Basic, sürücüler, klasörler ve dosyaları işlemek için kullanabileceğiniz `My.Computer.FileSystem` daha iyi performans sağlar ve gibi geleneksel yöntemlerinden daha kullanımı daha kolay olan nesne `FileOpen` ve `Write` (bunlar rağmen işlevleri kullanılabilir).</span><span class="sxs-lookup"><span data-stu-id="f5b40-103">You can use Visual Basic to process drives, folders, and files with the `My.Computer.FileSystem` object, which provides better performance and is easier to use than traditional methods such as the `FileOpen` and `Write` functions (although they are still available).</span></span> <span data-ttu-id="f5b40-104">Aşağıdaki bölümlerde bu yöntemleri ayrıntılı olarak açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="f5b40-104">The following sections discuss these methods in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5b40-105">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="f5b40-105">In This Section</span></span>  
 [<span data-ttu-id="f5b40-106">Visual Basic ile Dosya Erişimi</span><span class="sxs-lookup"><span data-stu-id="f5b40-106">File Access with Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 <span data-ttu-id="f5b40-107">Nasıl kullanılacağı ele alınmaktadır `My.Computer.FileSystem` dosyalarını, sürücülerini ve klasörleri ile çalışmak için nesne.</span><span class="sxs-lookup"><span data-stu-id="f5b40-107">Discusses how to use the `My.Computer.FileSystem` object to work with files, drives, and folders.</span></span>  
  
 [<span data-ttu-id="f5b40-108">.NET Framework dosyası g/ç ve dosya sistemi (Visual Basic) hakkında temel bilgiler</span><span class="sxs-lookup"><span data-stu-id="f5b40-108">Basics of .NET Framework File I/O and the File System (Visual Basic)</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)  
 <span data-ttu-id="f5b40-109">Akışlar, yalıtılmış depolama, dosya olayları, dosya öznitelikleri ve dosya erişimi de dahil olmak üzere .NET Framework dosyası g/ç kavramları genel bir bakış sağlar.</span><span class="sxs-lookup"><span data-stu-id="f5b40-109">Provides an overview of file I/O concepts in the .NET Framework, including streams, isolated storage, file events, file attributes, and file access.</span></span>  
  
 [<span data-ttu-id="f5b40-110">İzlenecek yol: .NET Framework yöntemlerini kullanarak dosyaları düzenleme</span><span class="sxs-lookup"><span data-stu-id="f5b40-110">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)  
 <span data-ttu-id="f5b40-111">.NET Framework dosyaları ve klasörleri yönetmek için nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="f5b40-111">Demonstrates how to use the .NET Framework to manipulate files and folders.</span></span>  
  
 [<span data-ttu-id="f5b40-112">İzlenecek yol: Dosyaları ve dizinleri Visual Basic'te düzenleme</span><span class="sxs-lookup"><span data-stu-id="f5b40-112">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 <span data-ttu-id="f5b40-113">Nasıl kullanılacağını gösteren `My.Computer.FileSystem` dosya ve klasörleri yönetmek için nesne.</span><span class="sxs-lookup"><span data-stu-id="f5b40-113">Demonstrates how to use the `My.Computer.FileSystem` object to manipulate files and folders.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f5b40-114">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="f5b40-114">Related Sections</span></span>  
 [<span data-ttu-id="f5b40-115">Program Yapısı ve Kod Kuralları</span><span class="sxs-lookup"><span data-stu-id="f5b40-115">Program Structure and Code Conventions</span></span>](../../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 <span data-ttu-id="f5b40-116">Fiziksel yapısı ve görüntüsüne programlar için yönergeler sağlar.</span><span class="sxs-lookup"><span data-stu-id="f5b40-116">Provides guidelines for the physical structure and appearance of programs.</span></span>  
  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <span data-ttu-id="f5b40-117">Başvuru belgeleri için `My.Computer.FileSystem` nesne ve üyelerini.</span><span class="sxs-lookup"><span data-stu-id="f5b40-117">Reference documentation for the `My.Computer.FileSystem` object and its members.</span></span>
