---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: fa8845fd92e5c16b4ff15436caf42df4f1e151cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716049"
---
# <a name="isresultone-function"></a><span data-ttu-id="45c32-102">IsResultOne függvény</span><span class="sxs-lookup"><span data-stu-id="45c32-102">IsResultOne function</span></span>

<span data-ttu-id="45c32-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45c32-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45c32-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45c32-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45c32-105">Ellenőrzi, hogy egy adott eredmény értéke egyenlő-e `One` .</span><span class="sxs-lookup"><span data-stu-id="45c32-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="45c32-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="45c32-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="45c32-107">bemenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="45c32-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="45c32-108">`Result` a vizsgálandó érték.</span><span class="sxs-lookup"><span data-stu-id="45c32-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="45c32-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="45c32-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="45c32-110">A értéket adja vissza, `true` Ha `input` az egyenlő `One` .</span><span class="sxs-lookup"><span data-stu-id="45c32-110">Returns `true` if `input` is equal to `One`.</span></span>