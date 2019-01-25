---
title: Son &lt;anahtar sözcüğü&gt; deyimi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: d65c921a1631cd38c4d0d1ab9b34db3d7e43a97e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654847"
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a><span data-ttu-id="aeb62-102">Son &lt;anahtar sözcüğü&gt; deyimi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aeb62-102">End &lt;keyword&gt; Statement (Visual Basic)</span></span>

<span data-ttu-id="aeb62-103">Ek bir anahtar sözcüğe göre ve ardından, bu anahtar sözcüğü tarafından sunulan deyim bloğunu tanımını sonlandırır.</span><span class="sxs-lookup"><span data-stu-id="aeb62-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="aeb62-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="aeb62-104">Syntax</span></span>

```vb
End AddHandler
End Class
End Enum
End Event
End Function
End Get
End If
End Interface
End Module
End Namespace
End Operator
End Property
End RaiseEvent  
End RemoveHandler  
End Select
End Set
End Structure
End Sub
End SyncLock
End Try
End While
End With  
```  
  
## <a name="parts"></a><span data-ttu-id="aeb62-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="aeb62-105">Parts</span></span>

|<span data-ttu-id="aeb62-106">Bölümü</span><span class="sxs-lookup"><span data-stu-id="aeb62-106">Part</span></span>|<span data-ttu-id="aeb62-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="aeb62-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="aeb62-108">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="aeb62-108">Required.</span></span> <span data-ttu-id="aeb62-109">Programlama öğesinin tanımını sonlandırır.</span><span class="sxs-lookup"><span data-stu-id="aeb62-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="aeb62-110">Sonlandırmak için gerekli bir `AddHandler` başlamış eşleşen bir erişimci `AddHandler` özel deyiminde [Event deyimi](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="aeb62-111">Eşleşen bir başlamış bir sınıf tanımı sonlandırması gerekir [Class deyimi](class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="aeb62-112">Eşleşen bir başlamış bir numaralandırma tanımı sonlandırması gerekir [Enum deyimi](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="aeb62-113">Sonlandırmak için gerekli bir `Custom` başlamış eşleşen bir olay tanımında [Event deyimi](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="aeb62-114">Sonlandırmak için gerekli bir `Function` başlamış eşleşen bir yordam tanımında [Function deyimi](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="aeb62-115">Yürütme karşılaşırsa, bir `End Function` deyimi, denetimi çağrıldığı koda döndürür.</span><span class="sxs-lookup"><span data-stu-id="aeb62-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="aeb62-116">Sonlandırmak için gerekli bir `Property` başlamış eşleşen bir yordam tanımında [alma deyimi](get-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="aeb62-117">Yürütme karşılaşırsa, bir `End Get` deyimi, denetimi özelliğinin değeri isteyen deyime döndürür.</span><span class="sxs-lookup"><span data-stu-id="aeb62-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="aeb62-118">Sonlandırmak için gerekli bir `If`... `Then`... `Else` engelleyecek bir eşleştirerek başlamış tanımı `If` deyimi.</span><span class="sxs-lookup"><span data-stu-id="aeb62-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="aeb62-119">Bkz: [varsa... Daha sonra... Else deyimi](if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="aeb62-120">Eşleşen bir başlamış arabirim tanımı sonlandırması gerekir [Interface deyimi](interface-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="aeb62-121">Eşleşen bir başlamış bir modül tanımı sonlandırması gerekir [Module deyimi](module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="aeb62-122">Eşleşen bir başlamış bir ad alanı tanımını sonlandırması gerekir [Namespace deyimi](namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="aeb62-123">Eşleşen bir başlamış bir işleç tanımını sonlandırması gerekir [Operator deyimi](operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="aeb62-124">Bir özellik tanımı bir eşleştirerek başlamış sonlandırması gerekir [Property deyimi](property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="aeb62-125">Sonlandırmak için gerekli bir `RaiseEvent` başlamış eşleşen bir erişimci `RaiseEvent` özel deyiminde [Event deyimi](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="aeb62-126">Sonlandırmak için gerekli bir `RemoveHandler` başlamış eşleşen bir erişimci `RemoveHandler` özel deyiminde [Event deyimi](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="aeb62-127">Sonlandırmak için gerekli bir `Select`... `Case` engelleyecek bir eşleştirerek başlamış tanımı `Select` deyimi.</span><span class="sxs-lookup"><span data-stu-id="aeb62-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="aeb62-128">Bkz: [seçin... Case deyimi](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="aeb62-129">Sonlandırmak için gerekli bir `Property` başlamış eşleşen bir yordam tanımında [bildirimine](set-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="aeb62-130">Yürütme karşılaşırsa, bir `End Set` deyimi, denetimi özelliğinin değerini ayarlayan bildirimi için döndürür.</span><span class="sxs-lookup"><span data-stu-id="aeb62-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="aeb62-131">Eşleşen bir başlamış bir yapı tanımı sonlandırması gerekir [Structure deyimi](structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="aeb62-132">Sonlandırmak için gerekli bir `Sub` başlamış eşleşen bir yordam tanımında [Sub deyimi](sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="aeb62-133">Yürütme karşılaşırsa, bir `End Sub` deyimi, denetimi çağrıldığı koda döndürür.</span><span class="sxs-lookup"><span data-stu-id="aeb62-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="aeb62-134">Sonlandırmak için gerekli bir `SyncLock` engelleyecek bir eşleştirerek başlamış tanımı `SyncLock` deyimi.</span><span class="sxs-lookup"><span data-stu-id="aeb62-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="aeb62-135">Bkz: [SyncLock deyimi](synclock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="aeb62-136">Sonlandırmak için gerekli bir `Try`... `Catch`... `Finally` engelleyecek bir eşleştirerek başlamış tanımı `Try` deyimi.</span><span class="sxs-lookup"><span data-stu-id="aeb62-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="aeb62-137">Bkz: [deneyin... Catch... Finally deyimini](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="aeb62-138">Sonlandırmak için gerekli bir `While` döngü bir eşleştirerek başlamış tanımı `While` deyimi.</span><span class="sxs-lookup"><span data-stu-id="aeb62-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="aeb62-139">Bkz: [sırada... End While deyimi](while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="aeb62-140">Sonlandırmak için gerekli bir `With` engelleyecek bir eşleştirerek başlamış tanımı `With` deyimi.</span><span class="sxs-lookup"><span data-stu-id="aeb62-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="aeb62-141">Bkz: [ile... End With deyimi](with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="aeb62-142">Yönergeler</span><span class="sxs-lookup"><span data-stu-id="aeb62-142">Directives</span></span>

<span data-ttu-id="aeb62-143">Sayı işareti önlerine (`#`), `End` anahtar sözcüğü karşılık gelen yönergesi tarafından tanıtılan ön işleme bloğunu sonlandırır.</span><span class="sxs-lookup"><span data-stu-id="aeb62-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="aeb62-144">Bölümü</span><span class="sxs-lookup"><span data-stu-id="aeb62-144">Part</span></span>|<span data-ttu-id="aeb62-145">Açıklama</span><span class="sxs-lookup"><span data-stu-id="aeb62-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="aeb62-146">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="aeb62-146">Required.</span></span> <span data-ttu-id="aeb62-147">Ön işleme bloğunun tanımını sonlandırır.</span><span class="sxs-lookup"><span data-stu-id="aeb62-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="aeb62-148">Eşleşen bir başlamış bir dış kaynak blok sonlandırma için gereken [#ExternalSource yönergesi](../directives/externalsource-directive.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="aeb62-149">Eşleşen bir başlamış koşullu derleme bloğunu sonlandırmak için gerekli `#If` yönergesi.</span><span class="sxs-lookup"><span data-stu-id="aeb62-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="aeb62-150">Bkz: [#If... Then... #Else yönergeleri](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="aeb62-151">Eşleşen bir başlamış kaynak bölge blok sonlandırma için gereken [#Region yönergesi](../directives/region-directive.md).</span><span class="sxs-lookup"><span data-stu-id="aeb62-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="aeb62-152">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="aeb62-152">Remarks</span></span>

<span data-ttu-id="aeb62-153">[End deyimi](end-statement.md), ek bir anahtar sözcüğü yürütme hemen sonlanır.</span><span class="sxs-lookup"><span data-stu-id="aeb62-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="aeb62-154">Akıllı Cihaz Geliştirici Notları</span><span class="sxs-lookup"><span data-stu-id="aeb62-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="aeb62-155">`End` Deyimi, bir ek anahtar sözcüğü olmadan desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="aeb62-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeb62-156">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="aeb62-156">See also</span></span>

- [<span data-ttu-id="aeb62-157">End Deyimi</span><span class="sxs-lookup"><span data-stu-id="aeb62-157">End Statement</span></span>](end-statement.md)
