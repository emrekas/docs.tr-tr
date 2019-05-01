---
title: Temel türler
description: Kullanılan temel temel türler Bul F# dili.
ms.date: 07/09/2018
ms.openlocfilehash: 74a276792e2566b8f18b87f4bdcfb923b713b9c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959126"
---
# <a name="basic-types"></a><span data-ttu-id="bd944-103">Temel türler</span><span class="sxs-lookup"><span data-stu-id="bd944-103">Basic types</span></span>

<span data-ttu-id="bd944-104">Bu konu içinde tanımlanan temel türleri listeler F# dili.</span><span class="sxs-lookup"><span data-stu-id="bd944-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="bd944-105">Bu en temel türler F#, neredeyse tüm temel oluşturan F# program.</span><span class="sxs-lookup"><span data-stu-id="bd944-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="bd944-106">Bunlar, bir üst .NET ilkel türler.</span><span class="sxs-lookup"><span data-stu-id="bd944-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="bd944-107">Tür</span><span class="sxs-lookup"><span data-stu-id="bd944-107">Type</span></span>|<span data-ttu-id="bd944-108">.NET türü</span><span class="sxs-lookup"><span data-stu-id="bd944-108">.NET type</span></span>|<span data-ttu-id="bd944-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bd944-109">Description</span></span>|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="bd944-110">Olası değerler `true` ve `false`.</span><span class="sxs-lookup"><span data-stu-id="bd944-110">Possible values are `true` and `false`.</span></span>|
|`byte`|<xref:System.Byte>|<span data-ttu-id="bd944-111">0 ile 255 değerler.</span><span class="sxs-lookup"><span data-stu-id="bd944-111">Values from 0 to 255.</span></span>|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="bd944-112">-128 ile 127 değerleri.</span><span class="sxs-lookup"><span data-stu-id="bd944-112">Values from -128 to 127.</span></span>|
|`int16`|<xref:System.Int16>|<span data-ttu-id="bd944-113">-32768 ile 32767 değerleri.</span><span class="sxs-lookup"><span data-stu-id="bd944-113">Values from -32768 to 32767.</span></span>|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="bd944-114">0 ile 65535 değerler.</span><span class="sxs-lookup"><span data-stu-id="bd944-114">Values from 0 to 65535.</span></span>|
|`int`|<xref:System.Int32>|<span data-ttu-id="bd944-115">-2.147.483.648 ile 2.147.483.647 değerleri.</span><span class="sxs-lookup"><span data-stu-id="bd944-115">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|<xref:System.UInt32>|<span data-ttu-id="bd944-116">4.294.967.295'e kadar değerleri 0.</span><span class="sxs-lookup"><span data-stu-id="bd944-116">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|<xref:System.Int64>|<span data-ttu-id="bd944-117">9.223.372.036.854.775.807-9,223,372,036,854,775,808 değeri.</span><span class="sxs-lookup"><span data-stu-id="bd944-117">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="bd944-118">18,446,744,073,709,551,615 0 değeri.</span><span class="sxs-lookup"><span data-stu-id="bd944-118">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="bd944-119">İmzalı bir tamsayı olarak yerel bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="bd944-119">A native pointer as a signed integer.</span></span>|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="bd944-120">İşaretsiz bir tamsayı olarak yerel işaretçi.</span><span class="sxs-lookup"><span data-stu-id="bd944-120">A native pointer as an unsigned integer.</span></span>|
|`char`|<xref:System.Char>|<span data-ttu-id="bd944-121">Unicode karakter değeri.</span><span class="sxs-lookup"><span data-stu-id="bd944-121">Unicode character values.</span></span>|
|`string`|<xref:System.String>|<span data-ttu-id="bd944-122">Unicode metin.</span><span class="sxs-lookup"><span data-stu-id="bd944-122">Unicode text.</span></span>|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="bd944-123">Bir kayan nokta veri türü, en az 28 basamaktan oluşur.</span><span class="sxs-lookup"><span data-stu-id="bd944-123">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="bd944-124">Uygulanamaz</span><span class="sxs-lookup"><span data-stu-id="bd944-124">not applicable</span></span>|<span data-ttu-id="bd944-125">Gerçek bir değer olmaması gösterir.</span><span class="sxs-lookup"><span data-stu-id="bd944-125">Indicates the absence of an actual value.</span></span> <span data-ttu-id="bd944-126">Belirtilen tek biçimsel değeri türüne sahip `()`.</span><span class="sxs-lookup"><span data-stu-id="bd944-126">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="bd944-127">Birimi değeri `()`, genellikle burada bir değer gerekiyordu ancak gerçek değer kullanılabilir veya anlamlı bir yer tutucu olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="bd944-127">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|<xref:System.Void>|<span data-ttu-id="bd944-128">Hiçbir tür veya değer gösterir.</span><span class="sxs-lookup"><span data-stu-id="bd944-128">Indicates no type or value.</span></span>|
|<span data-ttu-id="bd944-129">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="bd944-129">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="bd944-130">Bir 32-bit kayan nokta türü.</span><span class="sxs-lookup"><span data-stu-id="bd944-130">A 32-bit floating point type.</span></span>|
|<span data-ttu-id="bd944-131">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="bd944-131">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="bd944-132">Bir 64-bit kayan nokta türü.</span><span class="sxs-lookup"><span data-stu-id="bd944-132">A 64-bit floating point type.</span></span>|

> [!NOTE]
> <span data-ttu-id="bd944-133">Kullanarak 64-bit tamsayı türü için çok büyük bir tamsayı ile hesaplamalar gerçekleştirebilirsiniz [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) türü.</span><span class="sxs-lookup"><span data-stu-id="bd944-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="bd944-134">`bigint` bir temel tür olarak kabul edilmez; Bunun için bir kısaltma olduğundan `System.Numerics.BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="bd944-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd944-135">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="bd944-135">See also</span></span>

- [<span data-ttu-id="bd944-136">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="bd944-136">F# Language Reference</span></span>](index.md)