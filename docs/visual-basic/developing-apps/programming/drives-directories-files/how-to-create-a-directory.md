---
title: "Nasıl yapılır: Visual Basic'te bir dizin oluşturun"
ms.date: 07/20/2015
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
ms.openlocfilehash: 878ba0b8f62c067101a73182a377f5cfcb84ebc2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527438"
---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="64748-102">Nasıl yapılır: Visual Basic'te bir dizin oluşturun</span><span class="sxs-lookup"><span data-stu-id="64748-102">How to: Create a Directory in Visual Basic</span></span>
<span data-ttu-id="64748-103">Kullanım `CreateDirectory` yöntemi `My.Computer.FileSystem` dizinler oluşturmak için nesne.</span><span class="sxs-lookup"><span data-stu-id="64748-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="64748-104">Dizin zaten varsa, hiçbir özel durum oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="64748-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="64748-105">Bir dizin oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="64748-105">To create a directory</span></span>  
  
-   <span data-ttu-id="64748-106">Kullanım `CreateDirectory` burada dizin oluşturulmalıdır konumun tam yolunu belirterek yöntemi.</span><span class="sxs-lookup"><span data-stu-id="64748-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="64748-107">Bu örnek dizini `NewDirectory` içinde `C:\Documents and Settings\All Users\Documents`.</span><span class="sxs-lookup"><span data-stu-id="64748-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="64748-108">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="64748-108">Robust Programming</span></span>  
 <span data-ttu-id="64748-109">Aşağıdaki koşullar özel bir duruma neden olabilir:</span><span class="sxs-lookup"><span data-stu-id="64748-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="64748-110">Dizin adı yanlış biçimlendirilmiş.</span><span class="sxs-lookup"><span data-stu-id="64748-110">The directory name is malformed.</span></span> <span data-ttu-id="64748-111">Örneğin, geçersiz karakterler içeriyor veya yalnızca boşluk (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="64748-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="64748-112">Oluşturulacak dizinin üst dizin salt okunur (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="64748-112">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="64748-113">Dizin adı `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="64748-113">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="64748-114">Dizin adı çok uzun (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="64748-114">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="64748-115">Dizin adı iki nokta olan ":" (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="64748-115">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="64748-116">Kullanıcının dizin oluşturma izni yok (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="64748-116">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="64748-117">Kullanıcı izinleri kısmi güven durumda eksik (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="64748-117">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64748-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="64748-118">See also</span></span>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>
- [<span data-ttu-id="64748-119">Dosya ve Dizin Oluşturma, Silme ve Taşıma</span><span class="sxs-lookup"><span data-stu-id="64748-119">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
