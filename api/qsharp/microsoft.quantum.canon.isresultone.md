---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: f259c21e6cc0a4886332e9ffcb546e527ec7def1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840331"
---
# <a name="isresultone-function"></a><span data-ttu-id="e7d49-102">IsResultOne függvény</span><span class="sxs-lookup"><span data-stu-id="e7d49-102">IsResultOne function</span></span>

<span data-ttu-id="e7d49-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e7d49-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e7d49-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7d49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7d49-105">Ellenőrzi, hogy egy adott eredmény értéke egyenlő-e `One` .</span><span class="sxs-lookup"><span data-stu-id="e7d49-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="e7d49-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e7d49-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="e7d49-107">bemenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="e7d49-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="e7d49-108">`Result` a vizsgálandó érték.</span><span class="sxs-lookup"><span data-stu-id="e7d49-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e7d49-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e7d49-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e7d49-110">A értéket adja vissza, `true` Ha `input` az egyenlő `One` .</span><span class="sxs-lookup"><span data-stu-id="e7d49-110">Returns `true` if `input` is equal to `One`.</span></span>