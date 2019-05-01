---
title: 'Uç noktası: Saniyede Akışı Yapılan İşlem'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916259"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="bff69-102">Uç noktası: Saniyede Akışı Yapılan İşlem</span><span class="sxs-lookup"><span data-stu-id="bff69-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="bff69-103">Sayaç adı: Saniyede akışı yapılan işlemler.</span><span class="sxs-lookup"><span data-stu-id="bff69-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bff69-104">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bff69-104">Description</span></span>  
 <span data-ttu-id="bff69-105">İşlem sayısı işlemlerine Bu uç noktada bir saniye içinde aktarılan.</span><span class="sxs-lookup"><span data-stu-id="bff69-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="bff69-106">İşlem kimliği mevcut uç nokta için gönderilen bir iletinin dilediğiniz zaman bu sayaç artırılır.</span><span class="sxs-lookup"><span data-stu-id="bff69-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="bff69-107">Bu sayaç performans sayacı türüdür [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), değeri aşağıdaki formül kullanılarak hesaplanır.</span><span class="sxs-lookup"><span data-stu-id="bff69-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="bff69-108">(1 - N 0 N) / ((D 1 - D 0) / F)</span><span class="sxs-lookup"><span data-stu-id="bff69-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
