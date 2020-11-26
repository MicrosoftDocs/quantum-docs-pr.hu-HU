---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b4e9b62b20e12a8dce544ce16dcddcf15fdf2680
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206527"
---
# <a name="isresultzero-function"></a><span data-ttu-id="7e10d-102">IsResultZero függvény</span><span class="sxs-lookup"><span data-stu-id="7e10d-102">IsResultZero function</span></span>

<span data-ttu-id="7e10d-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7e10d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7e10d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e10d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e10d-105">Ellenőrzi, hogy egy adott eredmény értéke egyenlő-e `Zero` .</span><span class="sxs-lookup"><span data-stu-id="7e10d-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="7e10d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7e10d-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="7e10d-107">bemenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="7e10d-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="7e10d-108">`Result` a vizsgálandó érték.</span><span class="sxs-lookup"><span data-stu-id="7e10d-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7e10d-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7e10d-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7e10d-110">A értéket adja vissza, `true` Ha `input` az egyenlő `Zero` .</span><span class="sxs-lookup"><span data-stu-id="7e10d-110">Returns `true` if `input` is equal to `Zero`.</span></span>