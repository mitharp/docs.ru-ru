---
title: Обучение модели машинного обучения с помощью перекрестной проверки — ML.NET
description: Сведения о том, как обучить модель машинного обучения с помощью перекрестной проверки с использованием ML.NET, чтобы обеспечить более высокий уровень точности для прогнозов модели
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 8d74b69340895bcfe3cdc3d3a6121d7331a0a5e2
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092284"
---
# <a name="train-a-machine-learning-model-using-cross-validation---mlnet"></a>Обучение модели машинного обучения с помощью перекрестной проверки — ML.NET

[Перекрестная проверка](https://en.wikipedia.org/wiki/Cross-validation_(statistics)) является полезной методикой для приложений машинного обучения. Она помогает оценить вариативность качества модели между разными выполнениями, а также избавляет от необходимости извлекать отдельный набор тестов для оценки.

ML.NET автоматически применяет правильное присвоение признаков (при условии, что вся предобработка производится на одном конвейере обучения), после чего можно использовать концепцию "стратифицированного столбца", чтобы предотвратить разделение связанных примеров.

Ниже приведен пример обучения на основе набора данных по ирисам с использованием рандомизированного разделения учебных и тестовых данных как 90/10 и 5-кратной перекрестной проверки:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("SepalLength",DataKind.R4,0),
        new TextLoader.Column("SepalWidth",DataKind.R4,1),
        new TextLoader.Column("PetalLength",DataKind.R4,2),
        new TextLoader.Column("PetalWidth",DataKind.R4,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    // Default separator is tab, but the dataset has semicolon.
    separatorChar: ',',
    // First line of the file is a header, not a data row.
    hasHeader: true
);


// Read the data.
var data = reader.Read(dataPath);

// Build the training pipeline.
var dynamicPipeline =
    // Concatenate all the features together into one column 'Features'.
    mlContext.Transforms.Concatenate("Features", "SepalLength", "SepalWidth", "PetalLength", "PetalWidth")
    // Note that the label is text, so it needs to be converted to key.
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Label"), TransformerScope.TrainTest)
    // Use the multi-class SDCA model to predict the label using features.
    .Append(mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent());

// Split the data 90:10 into train and test sets, train and evaluate.
var (trainData, testData) = mlContext.MulticlassClassification.TrainTestSplit(data, testFraction: 0.1);

// Train the model.
var model = dynamicPipeline.Fit(trainData);
// Compute quality metrics on the test set.
var metrics = mlContext.MulticlassClassification.Evaluate(model.Transform(testData));
Console.WriteLine(metrics.AccuracyMicro);

// Now run the 5-fold cross-validation experiment, using the same pipeline.
var cvResults = mlContext.MulticlassClassification.CrossValidate(data, dynamicPipeline, numFolds: 5);

// The results object is an array of 5 elements. For each of the 5 folds, we have metrics, model and scored test data.
// Let's compute the average micro-accuracy.
var microAccuracies = cvResults.Select(r => r.metrics.AccuracyMicro);
Console.WriteLine(microAccuracies.Average());
```
