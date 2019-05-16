---
title: SqlStreamChars.SetLength(Int64) yöntemi (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 6bdf7bf5b998135652bc63d8d3e6c71a61475d20
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634290"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="fcf1c-102">SqlStreamChars.SetLength(Int64) yöntemi</span><span class="sxs-lookup"><span data-stu-id="fcf1c-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="fcf1c-103">Türetilen bir sınıfta geçersiz kılındığında, akış tarafından kullanılan kaynakları serbest bırakır.</span><span class="sxs-lookup"><span data-stu-id="fcf1c-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="fcf1c-104">Bu yöntemi içeren derlemenin SQLAccess.dll bir arkadaş ilişkisi vardır.</span><span class="sxs-lookup"><span data-stu-id="fcf1c-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="fcf1c-105">Bu, SQL Server tarafından kullanıma yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="fcf1c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="fcf1c-106">Diğer veritabanları için veritabanı tarafından sağlanan barındırma mekanizmasına kullanın.</span><span class="sxs-lookup"><span data-stu-id="fcf1c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="fcf1c-107">Parametreler</span><span class="sxs-lookup"><span data-stu-id="fcf1c-107">Parameters</span></span>

`value`\
<span data-ttu-id="fcf1c-108">İstenen bayt cinsinden geçerli akış uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="fcf1c-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcf1c-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fcf1c-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="fcf1c-110">`SqlStreamChars.SetLength` Yöntemi private olduğuna ve kodunuzda doğrudan kullanılmak üzere tasarlanmamıştır.</span><span class="sxs-lookup"><span data-stu-id="fcf1c-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="fcf1c-111">Microsoft hiçbir koşulda, bir üretim uygulamasında bu alanı kullanımını desteklemez.</span><span class="sxs-lookup"><span data-stu-id="fcf1c-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="fcf1c-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="fcf1c-112">Requirements</span></span>

<span data-ttu-id="fcf1c-113">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="fcf1c-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="fcf1c-114">**Derleme:** System.Data (içinde System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="fcf1c-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="fcf1c-115">**.NET framework sürümleri:** 2.0 sürümünden itibaren kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="fcf1c-115">**.NET Framework versions:** Available since 2.0.</span></span>
