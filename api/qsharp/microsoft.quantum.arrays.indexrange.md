---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220943"
---
# <a name="indexrange-function"></a><span data-ttu-id="e2e4e-102">IndexRange függvény</span><span class="sxs-lookup"><span data-stu-id="e2e4e-102">IndexRange function</span></span>

<span data-ttu-id="e2e4e-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e2e4e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e2e4e-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e2e4e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e2e4e-105">Egy tömb esetében az adott tömb indexei között egy tartományt ad vissza, amely a for ciklusban használható.</span><span class="sxs-lookup"><span data-stu-id="e2e4e-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="e2e4e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e2e4e-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="e2e4e-107">tömb: "táv []</span><span class="sxs-lookup"><span data-stu-id="e2e4e-107">array : 'TElement[]</span></span>

<span data-ttu-id="e2e4e-108">Olyan tömb, amelynek vissza kell adni az indexek tartományát.</span><span class="sxs-lookup"><span data-stu-id="e2e4e-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="e2e4e-109">Kimenet: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e2e4e-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="e2e4e-110">Egy tartomány az összes indexben a tömbben.</span><span class="sxs-lookup"><span data-stu-id="e2e4e-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e2e4e-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e2e4e-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="e2e4e-112">"Táv</span><span class="sxs-lookup"><span data-stu-id="e2e4e-112">'TElement</span></span>

<span data-ttu-id="e2e4e-113">A tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="e2e4e-113">The type of elements of the array.</span></span>