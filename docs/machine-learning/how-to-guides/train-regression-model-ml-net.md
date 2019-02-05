---
title: ML.NET kullanarak bir değeri tahmin etmek için regresyon modeli eğitme
description: Bir machine learning ML.NET kullanarak bir değeri tahmin etmek için regresyon modeli eğitmek nasıl keşfedin
ms.date: 02/01/2019
ms.custom: mvc,how-to
ms.openlocfilehash: febf12565b9ae5509efec9f350f413df99ba1c05
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739455"
---
# <a name="train-a-regression-model-to-predict-a-value-using-mlnet"></a>ML.NET kullanarak bir değeri tahmin etmek için regresyon modeli eğitme

Genellikle, ML.NET modeli eğitimi için üç adım vardır:

1. Eğitim verileri bir formda almak bir `IDataView`
2. 'Öğrenme işlem hattınızı' temel 'işleçleri' (estimators) dizisi olarak oluşturun.
3. Çağrı `Fit` işlem hattında, eğitilen model elde edilir.

Bu [örnek dosyası](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv), tahmin edilen etiketi (`target`) son sütunu (12) ve geri kalan özellikleri:

```console
feature_0;feature_1;feature_2;feature_3;feature_4;feature_5;feature_6;feature_7;feature_8;feature_9;feature_10;target
-2.75;0.77;-0.61;0.14;1.39;0.38;-0.53;-0.50;-2.13;-0.39;0.46;140.66
-0.61;-0.37;-0.12;0.55;-1.00;0.84;-0.02;1.30;-0.24;-0.50;-2.12;148.12
-0.85;-0.91;1.81;0.02;-0.78;-1.41;-1.09;-0.65;0.90;-0.37;-0.22;402.20
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.

// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(
        columns: new TextLoader.Column[]
        {
            // We read the first 11 values as a single float vector.
            new TextLoader.Column("FeatureVector",DataKind.R4,0,10),
            // Separately, read the target variable.
            new TextLoader.Column("Target",DataKind.R4,11)
        },
        // Default separator is tab, but the dataset has semicolon.
        separatorChar: ';',
        // First line of the file is a header, not a data row.
        hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var trainData = reader.Read(dataPath);

// Step two: define the learning pipeline.

// We 'start' the pipeline with the output of the reader.
var pipeline =
        // First 'normalize' the data (rescale to be
        // between -1 and 1 for all examples)
        mlContext.Transforms.Normalize("FeatureVector")
        // Cache data in memory so that SDCA trainer will be able to randomly access training examples without
        // reading data from disk multiple times. Data will be cached at its first use in any downstream step.
        // Notice that unused part in the data may not be cached.
        .AppendCacheCheckpoint(mlContext)
        // First 'normalize' the data (rescale to be
        // between -1 and 1 for all examples)
        .Append(mlContext.Regression.Trainers.StochasticDualCoordinateAscent("Target", "FeatureVector"));

// Step three. Fit the pipeline to the training data.
var model = pipeline.Fit(trainData);
```