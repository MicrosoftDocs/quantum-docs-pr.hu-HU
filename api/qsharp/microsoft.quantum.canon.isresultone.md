---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: eb4116b60bb415465375e374ad84e990135c231c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206544"
---
# <a name="isresultone-function"></a><span data-ttu-id="16eaf-102">IsResultOne függvény</span><span class="sxs-lookup"><span data-stu-id="16eaf-102">IsResultOne function</span></span>

<span data-ttu-id="16eaf-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="16eaf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="16eaf-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16eaf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16eaf-105">Ellenőrzi, hogy egy adott eredmény értéke egyenlő-e `One` .</span><span class="sxs-lookup"><span data-stu-id="16eaf-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="16eaf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="16eaf-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="16eaf-107">bemenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="16eaf-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="16eaf-108">`Result` a vizsgálandó érték.</span><span class="sxs-lookup"><span data-stu-id="16eaf-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="16eaf-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="16eaf-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="16eaf-110">A értéket adja vissza, `true` Ha `input` az egyenlő `One` .</span><span class="sxs-lookup"><span data-stu-id="16eaf-110">Returns `true` if `input` is equal to `One`.</span></span>