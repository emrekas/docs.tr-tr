---
title: 'Nasıl yapılır: Bir Görevde EAP Desenlerini Sarmalama'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4287879bd95f7bc1e1dc99f74fa0d7cc0fe737f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769206"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="0fddd-102">Nasıl yapılır: Bir Görevde EAP Desenlerini Sarmalama</span><span class="sxs-lookup"><span data-stu-id="0fddd-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="0fddd-103">Aşağıdaki örnek, rastgele bir olay tabanlı zaman uyumsuz desen (EAP) işlem dizisi bir görev olarak kullanarak nasıl sunacağınızı öğrenin gösterir bir <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span><span class="sxs-lookup"><span data-stu-id="0fddd-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="0fddd-104">Örnek ayrıca nasıl kullanılacağını gösterir bir <xref:System.Threading.CancellationToken> üzerinde yerleşik iptal yöntemleri çağırmak için <xref:System.Net.WebClient> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="0fddd-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fddd-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="0fddd-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="0fddd-106">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0fddd-106">See also</span></span>

- [<span data-ttu-id="0fddd-107">TPL ve Geleneksel .NET Framework Zaman Uyumsuz Programlama</span><span class="sxs-lookup"><span data-stu-id="0fddd-107">TPL and Traditional .NET Framework Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
