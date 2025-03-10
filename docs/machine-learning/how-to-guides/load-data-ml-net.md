---
title: Dosyalardan ve diğer kaynaklardan veri yükleme
description: Bu nasıl yapılır, ML.NET ' ye işleme ve eğitim için nasıl veri yükleneceğini gösterir. Veriler başlangıçta dosyalar veya veritabanları, JSON, XML veya bellek içi Koleksiyonlar gibi diğer veri kaynaklarında depolanır.
ms.date: 08/01/2019
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: d5f3aab14a60a8c9860dc67f1cc98f3b1b3188ed
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733361"
---
# <a name="load-data-from-files-and-other-sources"></a>Dosyalardan ve diğer kaynaklardan veri yükleme

Bu nasıl yapılır, ML.NET ' ye işleme ve eğitim için nasıl veri yükleneceğini gösterir. Veriler başlangıçta dosyalar veya veritabanları, JSON, XML veya bellek içi Koleksiyonlar gibi diğer veri kaynaklarında depolanır.

## <a name="create-the-data-model"></a>Veri modeli oluşturma

ML.NET, sınıflar aracılığıyla veri modelleri tanımlamanıza olanak sağlar. Örneğin, aşağıdaki giriş verileri verildiğinde:

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

Aşağıdaki kod parçacığını temsil eden bir veri modeli oluşturun:

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }
 
    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

### <a name="annotating-the-data-model-with-column-attributes"></a>Sütun öznitelikleriyle veri modeline açıklama ekleme

Öznitelikler, veri modeli ve veri kaynağı hakkında ML.NET daha fazla bilgi verir.

Öznitelik [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) , özelliklerinin sütun dizinlerini belirtir.

> [!IMPORTANT]
> [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)yalnızca bir dosyadan veri yüklenirken gereklidir.

Sütunları şu şekilde yükle: 
- Sınıfında ve `Size` `CurrentPrices` gibi ayrı sütunlar. `HousingData`
- Sınıf`HousingData` gibi `HistoricalPrices` bir vektör biçiminde tek seferde birden çok sütun.

Vektör özelliği varsa, [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) özniteliğini veri modelinizdeki özelliğe uygulayın. Vektördeki tüm öğelerin aynı türde olması gerektiğini unutmayın. Sütunların ayrılmış tutulması, özellik mühendisliğinin kolaylığını ve esnekliğini sağlar, ancak çok fazla sayıda sütun için, bireysel sütunlarda çalışan eğitim hızında bir etkiye neden olur.

ML.NET, sütun adlarıyla çalışır. Bir sütunun adını özellik adı dışında bir şekilde değiştirmek istiyorsanız, [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) özniteliğini kullanın. Bellek içi nesneler oluştururken, hala özellik adını kullanarak nesneler oluşturursunuz. Ancak, veri işleme ve makine öğrenimi modelleri oluşturma için, ml.net geçersiz kılar ve özelliği [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) özniteliğinde belirtilen değerle başvurur.

## <a name="load-data-from-a-single-file"></a>Tek bir dosyadaki verileri yükleme

Bir dosyadan veri yüklemek için yöntemini, [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) yüklenecek verilerin veri modeliyle birlikte kullanın. `separatorChar` Parametre varsayılan olarak sekmeyle ayrılmış olduğundan, bunu veri dosyanız için gereken şekilde değiştirin. Dosyanızın bir üstbilgisi varsa, `hasHeader` `true` parametresini dosyadaki ilk satırı yoksayacak şekilde ayarlayın ve ikinci satırdan verileri yüklemeye başlayın.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a>Birden çok dosyadan veri yükleme

Verilerinizin birden çok dosyada depolandığından, veri şeması aynı olduğu sürece, ML.NET aynı dizinde veya birden çok dizinde bulunan birden çok dosyadan veri yüklemenize izin verir.

### <a name="load-from-files-in-a-single-directory"></a>Tek bir dizindeki dosyalardan yükleme

Tüm veri dosyalarınız aynı dizinde olduğunda, [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) yönteminde joker karakterler kullanın.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a>Birden çok dizindeki dosyalardan yükleme

Birden çok dizindeki verileri yüklemek için [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) yöntemini kullanarak bir [`TextLoader`](xref:Microsoft.ML.Data.TextLoader)oluşturun. Ardından, [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) yöntemini kullanın ve tek dosya yollarını belirtin (joker karakterler kullanılamaz).

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-other-sources"></a>Diğer kaynaklardan veri yükleme

ML.NET, dosyalarda depolanan verileri yüklemeye ek olarak, dahil edilen ancak bunlarla sınırlı olmayan kaynaklardan veri yüklemeyi destekler:

- Bellek içi Koleksiyonlar
- JSON/XML
- Veritabanları

Akış kaynaklarıyla çalışırken ML.NET, girişin bellek içi koleksiyon biçiminde olmasını bekler. Bu nedenle, JSON/XML gibi kaynaklarla çalışırken, verileri bellek içi bir koleksiyonda biçimlediğinizden emin olun.

Aşağıdaki bellek içi koleksiyon verildiğinde:

```csharp
HousingData[] inMemoryCollection = new HousingData[]
{
    new HousingData
    {
        Size =700f,
        HistoricalPrices = new float[]
        {
            100000f, 3000000f, 250000f
        },
        CurrentPrice = 500000f
    },
    new HousingData
    {
        Size =1000f,
        HistoricalPrices = new float[]
        {
            600000f, 400000f, 650000f
        },
        CurrentPrice=700000f
    }
};
```

Bellek içi toplamayı, [`IDataView`](xref:Microsoft.ML.IDataView) [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) yöntemiyle bir öğesine yükleyin:

> [!IMPORTANT]
> [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*), [`IEnumerable`](xref:System.Collections.IEnumerable) ' den yüklendiği varsayılmaktadır, iş parçacığı güvenlidir. 

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
