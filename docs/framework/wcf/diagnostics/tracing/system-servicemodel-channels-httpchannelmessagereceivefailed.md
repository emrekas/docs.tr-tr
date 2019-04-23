---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: b848963caff706ff8a886c1e358ad6688e9611c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145281"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="1fea6-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="1fea6-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="1fea6-103">Bir HTTP kanalı üzerinden ileti alma başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="1fea6-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1fea6-104">Açıklama</span><span class="sxs-lookup"><span data-stu-id="1fea6-104">Description</span></span>  
 <span data-ttu-id="1fea6-105">Bu izleme, bir uyarı veya hata yayılabilir.</span><span class="sxs-lookup"><span data-stu-id="1fea6-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="1fea6-106">Her iki durumda da, uyumlu bir dinleyici için gelen HTTP isteği bulunamadı ve HTTP isteği göz ardı edilir olduğunda izleme yayınlanır.</span><span class="sxs-lookup"><span data-stu-id="1fea6-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="1fea6-107">Bu, isteğin HTTP fiili herhangi bir HTTP dinleyicisi tarafından tanınmıyor ya da dinleyici yok adresinde dinlemede olduğundan isteği için hedeflenen nedeniyle gerçekleşebilir.</span><span class="sxs-lookup"><span data-stu-id="1fea6-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="1fea6-108">Hizmet IIS'de barındırılıyorsa, şirket içinde barındırılan durumda bir uyarı ve hata izleme yayınlanır.</span><span class="sxs-lookup"><span data-stu-id="1fea6-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fea6-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1fea6-109">See also</span></span>

- [<span data-ttu-id="1fea6-110">İzleme</span><span class="sxs-lookup"><span data-stu-id="1fea6-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1fea6-111">Uygulamanızda Sorun Giderme için İzleme Kullanma</span><span class="sxs-lookup"><span data-stu-id="1fea6-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1fea6-112">Yönetim ve Tanılama</span><span class="sxs-lookup"><span data-stu-id="1fea6-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
