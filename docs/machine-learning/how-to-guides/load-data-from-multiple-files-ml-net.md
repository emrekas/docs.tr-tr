---
title: Machine learning hizmetinin işlem - ML.NET için birden fazla dosyalardan veri yükleme
description: Bilgi nasıl makine öğrenme modeli oluşturma, eğitim ve puanlama ML.NET ile kullanım için birden çok dosyadan veri yükleme
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: fbf5e4b5ab9a1a686edb933bdec818fc532bbf42
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679032"
---
# <a name="load-data-from-multiple-files-for-machine-learning-processing---mlnet"></a><span data-ttu-id="1eeb9-103">Machine learning hizmetinin işlem - ML.NET için birden fazla dosyalardan veri yükleme</span><span class="sxs-lookup"><span data-stu-id="1eeb9-103">Load data from multiple files for machine learning processing - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="1eeb9-104">Bu konu şu anda Önizleme aşamasında olan ML.NET ifade eder ve malzeme değişiklik gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="1eeb9-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="1eeb9-105">Daha fazla bilgi için ziyaret [ML.NET giriş](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="1eeb9-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="1eeb9-106">Bu nasıl yapılır ve ilgili örnek şu anda kullandığınızdan **ML.NET sürüm 0.10**.</span><span class="sxs-lookup"><span data-stu-id="1eeb9-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="1eeb9-107">Daha fazla bilgi için bkz: adresindeki sürüm notlarını [dotnet/machinelearning GitHub deposunu](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="1eeb9-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="1eeb9-108">Kullanım `TextLoader`ve bir dizi dosyaları belirtin `Read` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1eeb9-108">Use the `TextLoader`, and specify an array of files to the `Read` method.</span></span> <span data-ttu-id="1eeb9-109">Dosyaları aynı olmalıdır (aynı sayıda ve türde sütun) şema:</span><span class="sxs-lookup"><span data-stu-id="1eeb9-109">The files must have the same schema (same number and type of columns):</span></span>

* [<span data-ttu-id="1eeb9-110">Örnek fıle1'de</span><span class="sxs-lookup"><span data-stu-id="1eeb9-110">Example file1</span></span>](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.train)
* [<span data-ttu-id="1eeb9-111">Örnek dosya2</span><span class="sxs-lookup"><span data-stu-id="1eeb9-111">Example file2</span></span>](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.test)

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // A boolean column depicting the 'target label'.
        new TextLoader.Column("IsOver50k",DataKind.BL,0),
        // Three text columns.
        new TextLoader.Column("WorkClass",DataKind.TX,1),
        new TextLoader.Column("Education",DataKind.TX,2),
        new TextLoader.Column("MaritalStatus",DataKind.TX,3)
    },
    hasHeader: true
);

// Now read the files (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(exampleFile1, exampleFile2);
```