---
title: SqlStreamChars.Seek (Int64, SeekOrigin) yöntemi (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d52a1cd4dd70c29fc1af3fcf50c4f9b0c90125df
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827389"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="caa71-102">(Int64, SeekOrigin) SqlStreamChars.Seek yöntemi</span><span class="sxs-lookup"><span data-stu-id="caa71-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="caa71-103">Türetilen bir sınıfta geçersiz kılındığında, geçerli akış içinde konumunu ayarlar.</span><span class="sxs-lookup"><span data-stu-id="caa71-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="caa71-104">Bu yöntemi içeren derlemenin SQLAccess.dll bir arkadaş ilişkisi vardır.</span><span class="sxs-lookup"><span data-stu-id="caa71-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="caa71-105">Bu, SQL Server tarafından kullanıma yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="caa71-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="caa71-106">Diğer veritabanları için veritabanı tarafından sağlanan barındırma mekanizmasına kullanın.</span><span class="sxs-lookup"><span data-stu-id="caa71-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="caa71-107">Parametreler</span><span class="sxs-lookup"><span data-stu-id="caa71-107">Parameters</span></span>

`offset`\
<span data-ttu-id="caa71-108">Göreli bir bayt uzaklığı `origin`.</span><span class="sxs-lookup"><span data-stu-id="caa71-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="caa71-109">Yeni konumunu alınacağı başvuru noktası belirten numaralandırma değerlerinden biri.</span><span class="sxs-lookup"><span data-stu-id="caa71-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="caa71-110">Döndürür</span><span class="sxs-lookup"><span data-stu-id="caa71-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="caa71-111">Geçerli akışındaki yeni konumu.</span><span class="sxs-lookup"><span data-stu-id="caa71-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="caa71-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="caa71-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="caa71-113">`SqlStreamChars.Seek` Yöntemi private olduğuna ve kodunuzda doğrudan kullanılmak üzere tasarlanmamıştır.</span><span class="sxs-lookup"><span data-stu-id="caa71-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="caa71-114">Microsoft hiçbir koşulda, bir üretim uygulamasında bu alanı kullanımını desteklemez.</span><span class="sxs-lookup"><span data-stu-id="caa71-114">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="caa71-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="caa71-115">Requirements</span></span>

<span data-ttu-id="caa71-116">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="caa71-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="caa71-117">**Derleme:** System.Data (içinde System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="caa71-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="caa71-118">**.NET framework sürümleri:** 2.0 sürümünden itibaren kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="caa71-118">**.NET Framework versions:** Available since 2.0.</span></span>