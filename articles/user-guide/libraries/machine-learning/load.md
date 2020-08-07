---
title: Klasszikus adatlemez betöltése
description: Ismerje meg, hogyan tölthető be a saját adatkészlet egy osztályozó modell betanításához a Microsoft Quantum Development Kit (QDK) használatával.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 26ba7411c9ade1d6c4b606e8c12c10ade18fc584
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868831"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="151e8-103">Saját adatkészletek betöltése és besorolása</span><span class="sxs-lookup"><span data-stu-id="151e8-103">Load and classify your own datasets</span></span>

<span data-ttu-id="151e8-104">Ebben a rövid oktatóanyagban megtudhatja, hogyan tölthető be a saját adatkészlet egy osztályozó modell betanításához a Quantum Development Kit (QDK) használatával.</span><span class="sxs-lookup"><span data-stu-id="151e8-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="151e8-105">Javasoljuk, hogy az adattároláshoz használjon szabványos szerializálási formátumot, például a [JSON-fájlokat](https://en.wikipedia.org/wiki/JSON) .</span><span class="sxs-lookup"><span data-stu-id="151e8-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="151e8-106">Az ilyen formátumok nagy kompatibilitást biztosítanak a különböző keretrendszerek, például a Python és a .NET ökoszisztéma tekintetében.</span><span class="sxs-lookup"><span data-stu-id="151e8-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="151e8-107">Különösen azt javasoljuk, hogy az adatok betöltéséhez használja a sablont, hogy közvetlenül a mintából másolhatja be a kódot.</span><span class="sxs-lookup"><span data-stu-id="151e8-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="151e8-108">Az adatkészletek betöltéséhez használt sablon</span><span class="sxs-lookup"><span data-stu-id="151e8-108">Template for loading your datasets</span></span>

<span data-ttu-id="151e8-109">Tegyük fel, hogy a (z) $ (x, y) $ $N = $2-es betanítási adatkészlettel rendelkezik, ahol minden példánynak $x _i $ $x $-nak három funkciója van: $x _ {I1} $, $x _ {I2} $ és $x _ {i3} $.</span><span class="sxs-lookup"><span data-stu-id="151e8-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="151e8-110">Az érvényesítési adatkészlet ugyanazzal a szerkezettel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="151e8-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="151e8-111">Ezeket a datsets `data.json` az alábbihoz hasonló fájl jelölheti:</span><span class="sxs-lookup"><span data-stu-id="151e8-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a><span data-ttu-id="151e8-112">Példa a sablon használatával</span><span class="sxs-lookup"><span data-stu-id="151e8-112">Example using the template</span></span>

<span data-ttu-id="151e8-113">Tegyük fel, hogy van egy kis adathalmaza, amely a különböző macskák és kutyák magasságával és súlyával rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="151e8-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="151e8-114">Ez az adatkészlet nagyon kicsi a modell betanításához, de elegendő lesz az adatkészlet betöltési folyamatának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="151e8-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="151e8-115">Magasság (m)</span><span class="sxs-lookup"><span data-stu-id="151e8-115">Height (m)</span></span> | <span data-ttu-id="151e8-116">Súlyozás (kg)</span><span class="sxs-lookup"><span data-stu-id="151e8-116">Weight (kg)</span></span> | <span data-ttu-id="151e8-117">Állat</span><span class="sxs-lookup"><span data-stu-id="151e8-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="151e8-118">0,54</span><span class="sxs-lookup"><span data-stu-id="151e8-118">0.54</span></span>      | <span data-ttu-id="151e8-119">30</span><span class="sxs-lookup"><span data-stu-id="151e8-119">30</span></span>         | <span data-ttu-id="151e8-120">Figyelve</span><span class="sxs-lookup"><span data-stu-id="151e8-120">Dog</span></span>    |
| <span data-ttu-id="151e8-121">0,30</span><span class="sxs-lookup"><span data-stu-id="151e8-121">0.30</span></span>      | <span data-ttu-id="151e8-122">8</span><span class="sxs-lookup"><span data-stu-id="151e8-122">8</span></span>          | <span data-ttu-id="151e8-123">Cat</span><span class="sxs-lookup"><span data-stu-id="151e8-123">Cat</span></span>    |
| <span data-ttu-id="151e8-124">0,91</span><span class="sxs-lookup"><span data-stu-id="151e8-124">0.91</span></span>      | <span data-ttu-id="151e8-125">44</span><span class="sxs-lookup"><span data-stu-id="151e8-125">44</span></span>         | <span data-ttu-id="151e8-126">Figyelve</span><span class="sxs-lookup"><span data-stu-id="151e8-126">Dog</span></span>    |
| <span data-ttu-id="151e8-127">0,86</span><span class="sxs-lookup"><span data-stu-id="151e8-127">0.86</span></span>      | <span data-ttu-id="151e8-128">31</span><span class="sxs-lookup"><span data-stu-id="151e8-128">31</span></span>          | <span data-ttu-id="151e8-129">Figyelve</span><span class="sxs-lookup"><span data-stu-id="151e8-129">Dog</span></span>    |
| <span data-ttu-id="151e8-130">0,32</span><span class="sxs-lookup"><span data-stu-id="151e8-130">0.32</span></span>      | <span data-ttu-id="151e8-131">5</span><span class="sxs-lookup"><span data-stu-id="151e8-131">5</span></span>         | <span data-ttu-id="151e8-132">Cat</span><span class="sxs-lookup"><span data-stu-id="151e8-132">Cat</span></span>    |
| <span data-ttu-id="151e8-133">0,25</span><span class="sxs-lookup"><span data-stu-id="151e8-133">0.25</span></span>      | <span data-ttu-id="151e8-134">4</span><span class="sxs-lookup"><span data-stu-id="151e8-134">4</span></span>          | <span data-ttu-id="151e8-135">Cat</span><span class="sxs-lookup"><span data-stu-id="151e8-135">Cat</span></span>    |

<span data-ttu-id="151e8-136">A folyamat:</span><span class="sxs-lookup"><span data-stu-id="151e8-136">The process is:</span></span>

- <span data-ttu-id="151e8-137">Először el kell különíteni az adatkészletet a képzésbe és az érvényesítésbe.</span><span class="sxs-lookup"><span data-stu-id="151e8-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="151e8-138">Ebben az esetben csak az első három mintát vesszük igénybe a képzéshez és a többi minta ellenőrzéshez.</span><span class="sxs-lookup"><span data-stu-id="151e8-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="151e8-139">Általánosságban azt érdemes megtervezni, hogy véletlenszerűen megkóstolja a betanítási és érvényesítési adatkészletet, hogy elkerülje a betanítási adatokat a nemkívánatos torzulások elkerülése érdekében.</span><span class="sxs-lookup"><span data-stu-id="151e8-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="151e8-140">Másodszor, minden osztályhoz hozzá kell rendelni egy numerikus címkét.</span><span class="sxs-lookup"><span data-stu-id="151e8-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="151e8-141">Vegye figyelembe, hogy jelenleg a QML-könyvtár csak bináris besorolási problémákat fogad el.</span><span class="sxs-lookup"><span data-stu-id="151e8-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="151e8-142">Ezért a 0. címkét a osztályhoz rendeljük, `Dog` az 1-es számot pedig az osztályhoz `Cat` .</span><span class="sxs-lookup"><span data-stu-id="151e8-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="151e8-143">Végül kitöltjük a sablont az adatkészlet adatai alapján.</span><span class="sxs-lookup"><span data-stu-id="151e8-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="151e8-144">Vegye figyelembe, hogy a nagyméretű adatkészletek esetében érdemes létrehozni egy kis parancsfájlt, amely automatikusan létrehozza a sablont az adott adatkészletből.</span><span class="sxs-lookup"><span data-stu-id="151e8-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="151e8-145">Ez a szkript az adatkészlet eredeti formátumának függvénye lesz.</span><span class="sxs-lookup"><span data-stu-id="151e8-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="151e8-146">Az adatkészlet esetében a `data.json` fájl a következő:</span><span class="sxs-lookup"><span data-stu-id="151e8-146">For our dataset the `data.json` file is:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a><span data-ttu-id="151e8-147">Az adatok betöltése</span><span class="sxs-lookup"><span data-stu-id="151e8-147">Loading the data</span></span>

<span data-ttu-id="151e8-148">Miután a rendszer JSON-fájlként szerializálta az adatait, betöltheti azt a választott gazdagép nyelvén elérhető JSON-kódtárak használatával.</span><span class="sxs-lookup"><span data-stu-id="151e8-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="151e8-149">Python</span><span class="sxs-lookup"><span data-stu-id="151e8-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="151e8-150">A Python a JSON-szerializált adatkezeléshez használható [beépített `json` csomagot](https://docs.python.org/3.7/library/json.html) tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="151e8-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="151e8-151">C#</span><span class="sxs-lookup"><span data-stu-id="151e8-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="151e8-152">A .NET Core platform biztosítja a [ `System.Text.Json` csomagot](https://www.nuget.org/packages/System.Text.Json) a JSON-szerializált adatkezeléshez:</span><span class="sxs-lookup"><span data-stu-id="151e8-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="151e8-153">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="151e8-153">Next steps</span></span>

<span data-ttu-id="151e8-154">Most már készen áll a saját adatkészletekkel való saját kísérletek futtatására.</span><span class="sxs-lookup"><span data-stu-id="151e8-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="151e8-155">Próbálja ki a különböző besorolásokat és adatkészleteket, és járuljon hozzá az eredményeket megosztó közösséghez.</span><span class="sxs-lookup"><span data-stu-id="151e8-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
