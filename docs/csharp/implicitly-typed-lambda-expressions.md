---
title: Türü örtük olarak belirlenmiş lambda ifadeleri
description: Türü örtük olarak belirlenmiş bir değişken bildirimi bir lambda ifadesi bildirmek için neden kullanamazsınız öğrenin.
ms.date: 06/20/2016
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
ms.openlocfilehash: 9b798f40676afaad2075806d6dc512f279bc7065
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672087"
---
# <a name="implicitly-typed-lambda-expressions"></a>Türü örtük olarak belirlenmiş lambda ifadeleri

Türü örtük olarak belirlenmiş bir değişken bildirimi bir lambda ifadesi bildirmek için kullanamazsınız.
Derleyici için döngüsel mantıksal sorun oluşturur. `var` Bildirimi atama işlecinin sağ tarafı ifadesinin türünden değişkeninin türü ekleyeceğimi derleyiciye bildirir. Bir lambda ifadesi, bir derleme zamanı tür yok, ancak eşleşen bir temsilci veya ifade türüne dönüştürülemez. Bir lambda ifadesi bir temsilci veya ifade türünde bir değişkene atadığınızda, deneyin ve lambda ifadesindeki bir ifade veya 'atanan' değişkeninin imzayla eşleşen temsilci dönüştürmek için derleyicinin söyleyin. Derleyici, sağ tarafta atama eşleşmenin atama türünü sol tarafında bir şey yapmak denemeniz gerekir. 

Her iki tarafında atama derleyicinin nesne atama işlecinin diğer tarafında bakın ve türüm eşleşip eşleşmediğini belirten olamaz.

Neden bu davranışı belirtir okuyarak C# dili hakkında daha fazla ayrıntıya ulaşabilirsiniz [bu makalede](https://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (PDF olarak indirin)
