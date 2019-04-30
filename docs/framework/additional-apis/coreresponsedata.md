---
title: CoreResponseData Sınıfı
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 640a925c3aec86b4743b1b2b62eb3793af1cc0bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675423"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="d4610-102">CoreResponseData Sınıfı</span><span class="sxs-lookup"><span data-stu-id="d4610-102">CoreResponseData Class</span></span>

<span data-ttu-id="d4610-103">`CoreResponseData` Sınıfı, yanıt gövdesi ile HTTP üstbilgileri ve ayrıştırma temsil eder.</span><span class="sxs-lookup"><span data-stu-id="d4610-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="d4610-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d4610-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="d4610-105">Bu API dahili kullanım içindir ve kodunuzda doğrudan kullanılmak üzere tasarlanmamıştır.</span><span class="sxs-lookup"><span data-stu-id="d4610-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="d4610-106">Bunun yerine, kullanmanız bir <xref:System.Diagnostics.DiagnosticSource> ağ kod yeteneklerinizi.</span><span class="sxs-lookup"><span data-stu-id="d4610-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="d4610-107">Bkz: [DiagnosticSource Kullanıcı Kılavuzu](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="d4610-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="d4610-108">Microsoft hiçbir koşulda, bir üretim uygulamasında bu sınıfın kullanımını desteklemez.</span><span class="sxs-lookup"><span data-stu-id="d4610-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d4610-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="d4610-109">Requirements</span></span>

<span data-ttu-id="d4610-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d4610-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d4610-111">**Derleme:** Sistemde (System.dll)</span><span class="sxs-lookup"><span data-stu-id="d4610-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="d4610-112">**.NET framework sürümleri:** 2.0 sürümünden itibaren kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="d4610-112">**.NET Framework versions:** Available since 2.0.</span></span>
