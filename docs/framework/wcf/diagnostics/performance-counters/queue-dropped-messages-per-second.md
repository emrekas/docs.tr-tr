---
title: Saniyede Kuyruğa Alınan Bırakılmış İleti
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916168"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="da5e0-102">Saniyede Kuyruğa Alınan Bırakılmış İleti</span><span class="sxs-lookup"><span data-stu-id="da5e0-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="da5e0-103">Sayaç adı: Saniye başına bırakılan kuyruğa alınmış iletiler.</span><span class="sxs-lookup"><span data-stu-id="da5e0-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="da5e0-104">Açıklama</span><span class="sxs-lookup"><span data-stu-id="da5e0-104">Description</span></span>  
 <span data-ttu-id="da5e0-105">Bir saniyede sıraya alınan aktarım sırasında bu hizmeti tarafından bırakılan ileti sayısı.</span><span class="sxs-lookup"><span data-stu-id="da5e0-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="da5e0-106">Bu sayaç performans sayacı türüdür [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), değeri aşağıdaki formül kullanılarak hesaplanır.</span><span class="sxs-lookup"><span data-stu-id="da5e0-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="da5e0-107">(1 - N 0 N) / ((D 1 - D 0) / F)</span><span class="sxs-lookup"><span data-stu-id="da5e0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
