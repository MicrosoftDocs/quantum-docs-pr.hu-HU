---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: 790551690cfba42df4cf7aa77e53e303050bdf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716034"
---
# <a name="isresultzero-function"></a><span data-ttu-id="74c5f-102">IsResultZero függvény</span><span class="sxs-lookup"><span data-stu-id="74c5f-102">IsResultZero function</span></span>

<span data-ttu-id="74c5f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="74c5f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="74c5f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="74c5f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="74c5f-105">Ellenőrzi, hogy egy adott eredmény értéke egyenlő-e `Zero` .</span><span class="sxs-lookup"><span data-stu-id="74c5f-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="74c5f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="74c5f-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="74c5f-107">bemenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="74c5f-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="74c5f-108">`Result` a vizsgálandó érték.</span><span class="sxs-lookup"><span data-stu-id="74c5f-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="74c5f-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="74c5f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="74c5f-110">A értéket adja vissza, `true` Ha `input` az egyenlő `Zero` .</span><span class="sxs-lookup"><span data-stu-id="74c5f-110">Returns `true` if `input` is equal to `Zero`.</span></span>