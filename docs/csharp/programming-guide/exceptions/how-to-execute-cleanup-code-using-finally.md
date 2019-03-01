---
title: 'Nasıl yapılır: Son olarak - kullanarak temizleme kodu yürütme C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: 0ec661e5fb0e13eaf8c3c8e4a7b274ab58853f58
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978091"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="051aa-102">Nasıl yapılır: Finally anahtar sözcüğünü kullanarak temizleme kodu yürütme (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="051aa-102">How to: Execute Cleanup Code Using finally (C# Programming Guide)</span></span>
<span data-ttu-id="051aa-103">Amacı, bir `finally` deyimdir bile bir özel durum nesneleri, genellikle dış kaynakları tutan nesnelerin gerekli temizleme hemen olmasını sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="051aa-103">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="051aa-104">Bu tür temizleme örneği çağırır <xref:System.IO.Stream.Close%2A> üzerinde bir <xref:System.IO.FileStream> nesne gibi ortak dil çalışma zamanı tarafından toplanan çöp olmasını beklemek yerine hemen kullandıktan sonra:</span><span class="sxs-lookup"><span data-stu-id="051aa-104">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#16)]  
  
## <a name="example"></a><span data-ttu-id="051aa-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="051aa-105">Example</span></span>  
 <span data-ttu-id="051aa-106">Önceki kodun içine açmak için bir `try-catch-finally` deyimi, temizleme kodunu ayrılmış çalışan koddan gibi.</span><span class="sxs-lookup"><span data-stu-id="051aa-106">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#17)]  
  
 <span data-ttu-id="051aa-107">Dilediğiniz zaman içinde bir özel durum gerçekleşebileceği için `try` önce block `OpenWrite()` çağrısı, veya `OpenWrite()` çağrının kendisini işlemi başarısız olabilir, biz kapatmak denediğinizde dosyayı açık olduğunu garanti edilmez.</span><span class="sxs-lookup"><span data-stu-id="051aa-107">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="051aa-108">`finally` Blok emin olmak için bir denetim ekler <xref:System.IO.FileStream> nesne `null` çağırmadan önce <xref:System.IO.Stream.Close%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="051aa-108">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="051aa-109">Olmadan `null` denetleyin, `finally` blok throw kendi <xref:System.NullReferenceException>, ancak özel durumları atma `finally` mümkünse blokları kaçınılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="051aa-109">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="051aa-110">Veritabanı bağlantısı kapatıldığından kuşkulanılıyor için başka bir iyi aday olan bir `finally` blok.</span><span class="sxs-lookup"><span data-stu-id="051aa-110">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="051aa-111">Veritabanı sunucusu için izin verilen bağlantı sayısını bazen sınırlı olduğundan, veritabanı bağlantıları mümkün olan en kısa sürede kapatmalısınız.</span><span class="sxs-lookup"><span data-stu-id="051aa-111">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="051aa-112">Bağlantınızı kapatmadan önce bir özel durum oluşturulursa, başka bir durum budur kullanıldığında `finally` blok çöp toplama için bekleyen daha iyidir.</span><span class="sxs-lookup"><span data-stu-id="051aa-112">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="051aa-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="051aa-113">See also</span></span>

- [<span data-ttu-id="051aa-114">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="051aa-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="051aa-115">Özel Durumlar ve Özel Durum İşleme</span><span class="sxs-lookup"><span data-stu-id="051aa-115">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)
- [<span data-ttu-id="051aa-116">Özel Durum İşleme</span><span class="sxs-lookup"><span data-stu-id="051aa-116">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)
- [<span data-ttu-id="051aa-117">using Deyimi</span><span class="sxs-lookup"><span data-stu-id="051aa-117">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
- [<span data-ttu-id="051aa-118">try-catch</span><span class="sxs-lookup"><span data-stu-id="051aa-118">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)
- [<span data-ttu-id="051aa-119">try-finally</span><span class="sxs-lookup"><span data-stu-id="051aa-119">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)
- [<span data-ttu-id="051aa-120">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="051aa-120">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)
