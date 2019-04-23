---
title: 'Nasıl yapılır: ML.NET veri yükleme'
description: Veri dosyası ve ML.NET akış verileri yükleme
ms.date: 04/03/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 7702c626aa79c7b661638df5a5f0f90f821b32f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59981272"
---
# <a name="how-to-learn-how-to-load-data-from-file-and-real-time-sources-in-mlnet"></a><span data-ttu-id="a238b-103">Nasıl yapılır: Dosya ve gerçek zamanlı ML.NET kaynaklarında veri yüklemek hakkında bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="a238b-103">How-To: Learn how to load data from file and real-time sources in ML.NET</span></span>

<span data-ttu-id="a238b-104">Bu nasıl yapılır ML.NET içinde veri işleme ve eğitim için yükleme işlemini göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="a238b-104">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="a238b-105">Verileri özgün dosyaları veya gerçek zamanlı / akış veri kaynakları depolanır.</span><span class="sxs-lookup"><span data-stu-id="a238b-105">The data is originally stored in files or real-time / streaming data sources.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="a238b-106">Veri modeli oluşturma</span><span class="sxs-lookup"><span data-stu-id="a238b-106">Create the data model</span></span>

<span data-ttu-id="a238b-107">ML.NET sınıfları aracılığıyla veri modelleri tanımlamanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="a238b-107">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="a238b-108">Örneğin, aşağıdaki giriş verileri verilen:</span><span class="sxs-lookup"><span data-stu-id="a238b-108">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="a238b-109">Aşağıdaki kod parçacığında temsil eden bir veri modeli oluşturun:</span><span class="sxs-lookup"><span data-stu-id="a238b-109">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="a238b-110">Veri modeli sütunu özniteliklerle ek açıklama ekleme</span><span class="sxs-lookup"><span data-stu-id="a238b-110">Annotating the data model with column attributes</span></span>

<span data-ttu-id="a238b-111">Öznitelikleri ML.NET veri modeli ve veri kaynağı hakkında daha fazla bilgi verin.</span><span class="sxs-lookup"><span data-stu-id="a238b-111">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="a238b-112">[ `LoadColumn` ](xref:Microsoft.ML.Data.LoadColumnAttribute) Öznitelik özellikleri sütun dizinleri belirtir.</span><span class="sxs-lookup"><span data-stu-id="a238b-112">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a238b-113">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) olan yalnızca bir dosyadan verileri yüklenirken gereklidir.</span><span class="sxs-lookup"><span data-stu-id="a238b-113">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="a238b-114">Sütun olarak yükle:</span><span class="sxs-lookup"><span data-stu-id="a238b-114">Load columns as:</span></span> 
- <span data-ttu-id="a238b-115">Her bir sütun ister `Size` ve `CurrentPrices` içinde `HousingData` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="a238b-115">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="a238b-116">Bir vektör biçiminde bir zaman birden çok sütun ister `HistoricalPrices` içinde `HousingData` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="a238b-116">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="a238b-117">Bir vektör özelliği varsa, uygulama [ `VectorType` ](xref:Microsoft.ML.Data.VectorTypeAttribute) veri modelinizde özellik özniteliği.</span><span class="sxs-lookup"><span data-stu-id="a238b-117">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="a238b-118">Vektördeki tüm öğeleri aynı türde olması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="a238b-118">It's important to note that all of the elements in the vector need to be the same type.</span></span>

<span data-ttu-id="a238b-119">ML.NET Operates aracılığıyla sütun adları.</span><span class="sxs-lookup"><span data-stu-id="a238b-119">ML.NET Operates through column names.</span></span> <span data-ttu-id="a238b-120">Özellik adı dışında bir şey bir sütunun adını değiştirmek istiyorsanız, kullanın [ `ColumnName` ](xref:Microsoft.ML.Data.ColumnNameAttribute) özniteliği.</span><span class="sxs-lookup"><span data-stu-id="a238b-120">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="a238b-121">Bellek içi nesneleri oluştururken, yine de özellik adı'nı kullanarak nesne oluşturun.</span><span class="sxs-lookup"><span data-stu-id="a238b-121">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="a238b-122">Ancak, veri işleme ve yapı makine öğrenimi modellerini, ML.NET geçersiz kılar ve sağlanan değerle özelliğine başvuruyor [ `ColumnName` ](xref:Microsoft.ML.Data.ColumnNameAttribute) özniteliği.</span><span class="sxs-lookup"><span data-stu-id="a238b-122">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="a238b-123">Tek bir dosyadan veri yükleme</span><span class="sxs-lookup"><span data-stu-id="a238b-123">Load data from a single file</span></span>

<span data-ttu-id="a238b-124">Bir dosya kullanımdan verileri yüklemek için [ `LoadFromTextFile` ](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) veri modeline yüklenen verilerin yanı sıra yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a238b-124">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="a238b-125">Bu yana `separatorChar` parametre varsayılan olarak sekmeyle, veri dosyanızın gerektiği gibi değiştirin.</span><span class="sxs-lookup"><span data-stu-id="a238b-125">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="a238b-126">Üstbilgi dosyanız varsa Ayarla `hasHeader` parametresi `true` dosyanın ilk satırı yoksay ve ikinci satırında veri yüklemeye başlamak için.</span><span class="sxs-lookup"><span data-stu-id="a238b-126">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="a238b-127">Birden çok dosyadan veri yükleme</span><span class="sxs-lookup"><span data-stu-id="a238b-127">Load data from multiple files</span></span>

<span data-ttu-id="a238b-128">Aynı veri şemasını olduğu sürece, verilerinizi birden çok dosyasında depolanır, olay, ML.NET, veri ya da aynı dizinde olan birden çok dosya ya da birden çok dizini sağlar.</span><span class="sxs-lookup"><span data-stu-id="a238b-128">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="a238b-129">Tek bir dizindeki dosyaları yükleme</span><span class="sxs-lookup"><span data-stu-id="a238b-129">Load from files in a single directory</span></span>

<span data-ttu-id="a238b-130">Tüm veri dosyaları aynı dizinde olduğunda, joker [ `LoadFromTextFile` ](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a238b-130">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="a238b-131">Birden çok dizinlerde dosyaları yükleme</span><span class="sxs-lookup"><span data-stu-id="a238b-131">Load from files in multiple directories</span></span>

<span data-ttu-id="a238b-132">Birden çok dizinlerden verileri yüklemek için kullanmak [ `CreateTextLoader` ](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) yöntemi oluşturmak için bir [ `TextLoader` ](xref:Microsoft.ML.Data.TextLoader).</span><span class="sxs-lookup"><span data-stu-id="a238b-132">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="a238b-133">Ardından, [ `TextLoader.Load` ](xref:Microsoft.ML.DataLoaderExtensions.Load*) yöntemi ve (joker karakterler kullanılamaz) tek tek dosya yollarını belirtin.</span><span class="sxs-lookup"><span data-stu-id="a238b-133">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-streaming-source"></a><span data-ttu-id="a238b-134">Bir akış kaynağından veri yükleme</span><span class="sxs-lookup"><span data-stu-id="a238b-134">Load data from a streaming source</span></span>

<span data-ttu-id="a238b-135">Diskte depolanan veriler yükleniyor ek olarak, veri yükleme dahil ancak bunlarla sınırlı olmayan çeşitli kaynaklardan akış ML.NET destekler:</span><span class="sxs-lookup"><span data-stu-id="a238b-135">In addition to loading data stored on disk, ML.NET supports loading data from various streaming sources that include but are not limited to:</span></span>

- <span data-ttu-id="a238b-136">Bellek içi koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="a238b-136">In-memory collections</span></span>
- <span data-ttu-id="a238b-137">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="a238b-137">JSON/XML</span></span>
- <span data-ttu-id="a238b-138">Veritabanları</span><span class="sxs-lookup"><span data-stu-id="a238b-138">Databases</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a238b-139">ML.NET kaynakları akış ile çalışırken, bir bellek içi koleksiyonun biçiminde olması için giriş girmeniz gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="a238b-139">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="a238b-140">Bu nedenle, JSON/XML gibi kaynaklar ile çalışırken, bir bellek içi koleksiyona verilerin biçimlendirilmesi emin olun.</span><span class="sxs-lookup"><span data-stu-id="a238b-140">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="a238b-141">Şu bellek içi koleksiyonu verilen:</span><span class="sxs-lookup"><span data-stu-id="a238b-141">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="a238b-142">Bellek içi koleksiyona bir [ `IDataView` ](xref:Microsoft.ML.IDataView) ile [ `LoadFromEnumerable` ](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) yöntemi:</span><span class="sxs-lookup"><span data-stu-id="a238b-142">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```