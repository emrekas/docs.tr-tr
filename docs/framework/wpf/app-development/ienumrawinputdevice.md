---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: e465193d6a91848a27c2832dda454c6c45837e92
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530031"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="7d1d1-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="7d1d1-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="7d1d1-103">Bu arabirim, ham giriş cihazları numaralandırır ve yalnızca PresentationHost.exe tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d1d1-104">Bu API yalnızca hedeflenen ve yerel istemci makinesinde kullanımı desteklenen</span><span class="sxs-lookup"><span data-stu-id="7d1d1-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="7d1d1-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="7d1d1-105">Members</span></span>  
  
|<span data-ttu-id="7d1d1-106">Üye</span><span class="sxs-lookup"><span data-stu-id="7d1d1-106">Member</span></span>|<span data-ttu-id="7d1d1-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7d1d1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d1d1-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="7d1d1-108">IEnumRAWINPUTDEVIC:Next</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|<span data-ttu-id="7d1d1-109">Sonraki numaralandırır `celt` numaralandırıcı listesi olarak (diğer bir deyişle, RAWINPUTDEVICE yapıları) öğelerinde `rgelt` numaralandırılmış öğelerinde gerçek sayısını `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="7d1d1-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="7d1d1-110">IEnumRAWINPUTDEVIC:Skip</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|<span data-ttu-id="7d1d1-111">Sonraki Numaralandırıcıya bildirir `celt` listedeki öğeleri sonraki çağrı böylece [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) bu öğeleri döndürmez.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="7d1d1-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="7d1d1-112">IEnumRAWINPUTDEVIC:Reset</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|<span data-ttu-id="7d1d1-113">Sabit listesi sırası başlangıç durumuna sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="7d1d1-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="7d1d1-114">IEnumRAWINPUTDEVIC:Clone</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|<span data-ttu-id="7d1d1-115">Aynı liste üzerinde yineleme yapmak için geçerli bir numaralandırıcı ile aynı duruma sahip başka bir ham giriş cihazının Numaralandırıcı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d1d1-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-116">See also</span></span>
- [<span data-ttu-id="7d1d1-117">Ham giriş hakkında</span><span class="sxs-lookup"><span data-stu-id="7d1d1-117">About Raw Input</span></span>](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)
