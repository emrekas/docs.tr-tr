---
title: ML.NET ardışık düzen işleme sırasında ara veri değerlerini İnceleme
description: Ardışık Düzen işleme öğrenme ML.NET makine sırasında gerçek ara veri değerlerini incelemek hakkında bilgi edinin
ms.date: 01/30/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b3a554bf7cd88219a66f91a18b9d983bb91c0f0e
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675019"
---
# <a name="inspect-intermediate-data-values-during-mlnet-pipeline-processing"></a><span data-ttu-id="262ef-103">ML.NET ardışık düzen işleme sırasında ara veri değerlerini İnceleme</span><span class="sxs-lookup"><span data-stu-id="262ef-103">Inspect intermediate data values during ML.NET pipeline processing</span></span>

<span data-ttu-id="262ef-104">Deneme sırasında inceleyin ve belirli bir noktada veri işleme sonuçları doğrulamak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="262ef-104">During the experiment, you may want to observe and validate the data processing results at a given point.</span></span> <span data-ttu-id="262ef-105">ML.NET işlemleri oluşturma veri ' gösterir' olan nesneleri yavaş olduğundan, bu kolay değildir.</span><span class="sxs-lookup"><span data-stu-id="262ef-105">This isn't easy since ML.NET operations are lazy, constructing objects that are 'promises' of data.</span></span>

<span data-ttu-id="262ef-106">`GetColumn<T>` Genişletme yöntemi, Ara verileri incelemenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="262ef-106">The `GetColumn<T>` extension method lets you inspect the intermediate data.</span></span> <span data-ttu-id="262ef-107">Bir veri sütunu olarak içeriğini döndürür bir `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="262ef-107">It returns the contents of one data column as an `IEnumerable`.</span></span>

<span data-ttu-id="262ef-108">Aşağıdaki örnek nasıl kullanılacağını gösterir `GetColumn<T>` genişletme yöntemi:</span><span class="sxs-lookup"><span data-stu-id="262ef-108">The following example shows how to use the `GetColumn<T>` extension method:</span></span>

<span data-ttu-id="262ef-109">[Örnek dosya](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="262ef-109">[Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span></span>
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse

```

<span data-ttu-id="262ef-110">Bizim sınıfı şu şekilde tanımlanır:</span><span class="sxs-lookup"><span data-stu-id="262ef-110">Our class is defined as follows:</span></span>

```csharp
public class InspectedRow
{
    [LoadColumn(0)]
    public bool IsOver50K { get; set; }
    [LoadColumn(1)]
    public string WorkClass { get; set; }
    [LoadColumn(2)]
    public string Education { get; set; }
    [LoadColumn(3)]
    public string MaritalStatus { get; set; }
}
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Read the data into a data view.
var data = mlContext.Data.ReadFromTextFile<InspectedRow>(dataPath, hasHeader: true);

// Start creating our processing pipeline. For now, let's just concatenate all the text columns
// together into one.
var pipeline = mlContext.Transforms.Concatenate("AllFeatures", "WorkClass", "Education", "MaritalStatus");

// Fit our data pipeline and transform data with it.
var transformedData = pipeline.Fit(data).Transform(data);

// Extract the 'AllFeatures' column.
// This will give the entire dataset: make sure to only take several row
// in case the dataset is huge. The is similar to the static API, except
// you have to specify the column name and type.
var featureColumns =
    transformedData
        .GetColumn<string[]>(mlContext, "AllFeatures")
        .Take(20)
        .ToArray();
```
