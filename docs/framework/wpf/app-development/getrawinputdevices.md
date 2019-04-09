---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 3531ff9f42289a3ad3b029f090f2dd4987e5886c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199410"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="c01e2-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="c01e2-102">GetRawInputDevices</span></span>
<span data-ttu-id="c01e2-103">Ana bilgisayar uygulaması, ilgileniyor ham giriş cihazlarını (İnsan Arabirimi aygıtları) bulma PresentationHost.exe sağlar.</span><span class="sxs-lookup"><span data-stu-id="c01e2-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c01e2-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c01e2-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a><span data-ttu-id="c01e2-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="c01e2-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="c01e2-106">[out] Bir işaretçi bir [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) için ham giriş cihazları listeleniyor.</span><span class="sxs-lookup"><span data-stu-id="c01e2-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c01e2-107">Özellik Değeri/Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="c01e2-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="c01e2-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="c01e2-108">HRESULT:</span></span>  
  
 <span data-ttu-id="c01e2-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) S_OK döndürülürse yalnızca PresentationHost.exe tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="c01e2-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="c01e2-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c01e2-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c01e2-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c01e2-111">Remarks</span></span>  
 <span data-ttu-id="c01e2-112">Ham giriş cihazları klavye, fare ve daha az geleneksel cihazları uzaktan kumandalar gibi içeren giriş cihazları kümesidir.</span><span class="sxs-lookup"><span data-stu-id="c01e2-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="c01e2-113">Ham giriş cihazların listesini alındıktan sonra PresentationHost.exe WM_INPUT bildirim iletilerinin alınacağı ile cihazları kaydeder.</span><span class="sxs-lookup"><span data-stu-id="c01e2-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c01e2-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c01e2-114">See also</span></span>

- [<span data-ttu-id="c01e2-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="c01e2-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="c01e2-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="c01e2-116">FilterInputMessage</span></span>](filterinputmessage.md)
