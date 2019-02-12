---
title: Machine learning hizmetinin işlem - ML.NET için birden fazla dosyalardan veri yükleme
description: Bilgi nasıl makine öğrenme modeli oluşturma, eğitim ve puanlama ML.NET ile kullanım için birden çok dosyadan veri yükleme
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: f5108aaed80769f2bc7ed2f974f9a729abe8455e
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092052"
---
# <a name="load-data-from-multiple-files-for-machine-learning-processing---mlnet"></a>Machine learning hizmetinin işlem - ML.NET için birden fazla dosyalardan veri yükleme

Kullanım `TextLoader`ve bir dizi dosyaları belirtin `Read` yöntemi. Dosyaları aynı olmalıdır (aynı sayıda ve türde sütun) şema:

* [Örnek fıle1'de](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.train)
* [Örnek dosya2](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.test)

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