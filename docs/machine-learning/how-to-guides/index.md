---
title: .NET makine öğrenimi nasıl yapılır kılavuzlarından - ML.NET
description: Özel yapay ZEKA çözümleri oluşturma ve Machine Learning .NET uygulamalarınızı tümleştirmeye yardımcı olmak üzere belirli görevlerin nasıl yapılacağını öğrenin.
ms.custom: seodec18
ms.date: 03/01/2019
---

# <a name="net-machine-learning-how-to-guides---mlnet"></a><span data-ttu-id="72f4c-103">.NET makine öğrenimi nasıl yapılır kılavuzlarından - ML.NET</span><span class="sxs-lookup"><span data-stu-id="72f4c-103">.NET Machine learning how-to guides - ML.NET</span></span>

<span data-ttu-id="72f4c-104">ML.NET Kılavuzu bölümüne nasıl hızlı sık sorulan soruların yanıtlarını bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="72f4c-104">In the How to section of the ML.NET Guide, you can find quick answers to common questions.</span></span> <span data-ttu-id="72f4c-105">Bazı durumlarda, makaleler bulmayı kolaylaştırmak için birden çok bölümlerinde listelenen.</span><span class="sxs-lookup"><span data-stu-id="72f4c-105">In some cases, articles may be listed in multiple sections to make them easy to find.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="72f4c-106">Verileri yükleme</span><span class="sxs-lookup"><span data-stu-id="72f4c-106">Load the data</span></span>

* [<span data-ttu-id="72f4c-107">Machine learning hizmetinin işlem için bir CSV dosyasından çok sütunlu veri yükleyin.</span><span class="sxs-lookup"><span data-stu-id="72f4c-107">Load data with many columns from a CSV file for machine learning processing.</span></span>](load-data-from-mult-column-csv-ml-net.md)

* [<span data-ttu-id="72f4c-108">Machine learning işlemi için birden çok dosyadan verileri yükleyin.</span><span class="sxs-lookup"><span data-stu-id="72f4c-108">Load data from multiple files for machine learning processing.</span></span>](load-data-from-multiple-files-ml-net.md)

* [<span data-ttu-id="72f4c-109">Machine learning hizmetinin işlem için bir metin dosyasından veri yükleyin.</span><span class="sxs-lookup"><span data-stu-id="72f4c-109">Load data from a text file for machine learning processing.</span></span>](load-data-from-text-file-ml-net.md)

### <a name="prepare-the-data"></a><span data-ttu-id="72f4c-110">Verileri hazırlama</span><span class="sxs-lookup"><span data-stu-id="72f4c-110">Prepare the data</span></span>

* [<span data-ttu-id="72f4c-111">Eğitim verileri ile veri işlemeye kullanılacak normalizers ön işleme.</span><span class="sxs-lookup"><span data-stu-id="72f4c-111">Preprocess training data with normalizers to use in data processing.</span></span>](normalizers-preprocess-data-ml-net.md)

## <a name="train-the-model"></a><span data-ttu-id="72f4c-112">Modeli eğitme</span><span class="sxs-lookup"><span data-stu-id="72f4c-112">Train the model</span></span>

* [<span data-ttu-id="72f4c-113">Bir metin dosyasına olmayan veriler ile machine learning modeli eğitin.</span><span class="sxs-lookup"><span data-stu-id="72f4c-113">Train a machine learning model with data that's not in a text file.</span></span>](load-non-file-training-data-ml-net.md)

* [<span data-ttu-id="72f4c-114">Çapraz doğrulama kullanarak makine öğrenme modeli eğitin.</span><span class="sxs-lookup"><span data-stu-id="72f4c-114">Train a machine learning model using cross-validation.</span></span>](train-cross-validation-ml-net.md)

* [<span data-ttu-id="72f4c-115">ML.NET kullanarak bir değeri tahmin etmek için regresyon modeli eğitin.</span><span class="sxs-lookup"><span data-stu-id="72f4c-115">Train a regression model to predict a value using ML.NET.</span></span>](train-regression-model-ml-net.md)

### <a name="evaluate-the-model-quality"></a><span data-ttu-id="72f4c-116">Model kalitesi değerlendir</span><span class="sxs-lookup"><span data-stu-id="72f4c-116">Evaluate the model quality</span></span>

* [<span data-ttu-id="72f4c-117">Model kalitesini değerlendirmek için ölçümleri hesaplayın.</span><span class="sxs-lookup"><span data-stu-id="72f4c-117">Calculate metrics to evaluate model quality.</span></span>](verify-model-quality-ml-net.md)

### <a name="model-explainability"></a><span data-ttu-id="72f4c-118">Model explainability</span><span class="sxs-lookup"><span data-stu-id="72f4c-118">Model explainability</span></span>

* [<span data-ttu-id="72f4c-119">Modelleri özellik önemini özellik önem permütasyon ile belirleyin.</span><span class="sxs-lookup"><span data-stu-id="72f4c-119">Determine the feature importance of models with Permutation Feature Importance.</span></span>](determine-global-feature-importance-in-model.md)

* [<span data-ttu-id="72f4c-120">Genelleştirilmiş eklenebilir modelleri ve Şekil işlevleri için model explainability kullanın.</span><span class="sxs-lookup"><span data-stu-id="72f4c-120">Use Generalized Additive Models and shape functions for model explainability.</span></span>](use-gams-for-model-explainability.md)

### <a name="feature-engineering"></a><span data-ttu-id="72f4c-121">Özellik mühendisliği</span><span class="sxs-lookup"><span data-stu-id="72f4c-121">Feature engineering</span></span>

* [<span data-ttu-id="72f4c-122">Kategorik veriler üzerinde özellik Mühendisliği, eğitim modeli için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="72f4c-122">Apply feature engineering for model training on categorical data.</span></span>](train-model-categorical-ml-net.md)

* [<span data-ttu-id="72f4c-123">ML.NET ile metinsel veriler üzerinde özellik Mühendisliği, eğitim modeli için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="72f4c-123">Apply feature engineering for model training on textual data with ML.NET.</span></span>](train-model-textual-ml-net.md)

## <a name="run"></a><span data-ttu-id="72f4c-124">Çalıştır</span><span class="sxs-lookup"><span data-stu-id="72f4c-124">Run</span></span>

* [<span data-ttu-id="72f4c-125">ML.NET ardışık düzen işleme sırasında ara veri değerleri inceleyin.</span><span class="sxs-lookup"><span data-stu-id="72f4c-125">Inspect intermediate data values during ML.NET pipeline processing.</span></span>](inspect-intermediate-data-ml-net.md)

* [<span data-ttu-id="72f4c-126">Eğitilen makine öğrenme modeli uygulamalarda kullanıma hazır hale getirin.</span><span class="sxs-lookup"><span data-stu-id="72f4c-126">Operationalize a trained machine learning model in apps.</span></span>](consuming-model-ml-net.md)

* [<span data-ttu-id="72f4c-127">Aynı anda bir tahminde bulunmak için PredictionFunction kullanın.</span><span class="sxs-lookup"><span data-stu-id="72f4c-127">Use the PredictionFunction to make one prediction at a time.</span></span>](single-predict-model-ml-net.md)

## <a name="probabilistic-infernet"></a><span data-ttu-id="72f4c-128">Olasılıklara (Infer.NET)</span><span class="sxs-lookup"><span data-stu-id="72f4c-128">Probabilistic (Infer.NET)</span></span>

* [<span data-ttu-id="72f4c-129">Bir oyun eşleme listesi uygulaması Infer.NET olasılığa dayalı programlama ile oluşturun.</span><span class="sxs-lookup"><span data-stu-id="72f4c-129">Create a game match up list app with Infer.NET and probabilistic programming.</span></span>](matchup-app-infer-net.md)
