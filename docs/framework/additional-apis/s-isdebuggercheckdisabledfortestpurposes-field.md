---
title: s_isDebuggerCheckDisabledForTestPurposes alanı
ms.date: 03/30/2017
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: ab71ab6aa2b0ed454b86388ba369204a2131cca5
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634433"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="d5dbf-102">s_isDebuggerCheckDisabledForTestPurposes alanı</span><span class="sxs-lookup"><span data-stu-id="d5dbf-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="d5dbf-103">Bu özel bir alanda `System.Windows.Diagnostics.VisualDiagnostics` sınıfı için bir etkin hata ayıklayıcı iç bir onay gerçekleştirip gerçekleştirmediğini belirlemek için Visual Studio tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="d5dbf-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5dbf-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d5dbf-104">Syntax</span></span>

```csharp
private static bool s_isDebuggerCheckDisabledForTestPurposes
```

> [!WARNING]
> <span data-ttu-id="d5dbf-105">API'leri `System.Windows.Diagnostics.VisualDiagnostics` sınıfı bulunan ve yalnızca bir uygulama hata ayıklayıcı altında çalışırken.</span><span class="sxs-lookup"><span data-stu-id="d5dbf-105">APIs in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="d5dbf-106">Ayarlama `s_isDebuggerCheckDisabledForTestPurposes` için `true` API'lere bir hata ayıklayıcı dışında.</span><span class="sxs-lookup"><span data-stu-id="d5dbf-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>
>
> <span data-ttu-id="d5dbf-107">Microsoft hiçbir koşulda, bir üretim uygulamasında bu alanı kullanımını desteklemez.</span><span class="sxs-lookup"><span data-stu-id="d5dbf-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d5dbf-108">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="d5dbf-108">Requirements</span></span>

<span data-ttu-id="d5dbf-109">**Namespace:** <xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="d5dbf-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="d5dbf-110">**Derleme:** PresentationCore (içinde PresentationCore.dll)</span><span class="sxs-lookup"><span data-stu-id="d5dbf-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="d5dbf-111">**.NET framework sürümleri:** 4.6 sonrasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="d5dbf-111">**.NET Framework versions:** Available since 4.6.</span></span>