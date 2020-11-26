---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204062"
---
# <a name="isnotzero-function"></a><span data-ttu-id="cba9f-102">IsNotZero függvény</span><span class="sxs-lookup"><span data-stu-id="cba9f-102">IsNotZero function</span></span>

<span data-ttu-id="cba9f-103">Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cba9f-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="cba9f-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cba9f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="cba9f-105">Ellenőrzi, hogy egy `Double` szám nem körülbelül nulla-e.</span><span class="sxs-lookup"><span data-stu-id="cba9f-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="cba9f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cba9f-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="cba9f-107">szám: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cba9f-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cba9f-108">Ellenőrizendő szám</span><span class="sxs-lookup"><span data-stu-id="cba9f-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="cba9f-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cba9f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cba9f-110">Igaz értéket ad vissza `number` , ha a értéke nagyobb, mint `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="cba9f-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>