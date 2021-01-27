---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845781"
---
# <a name="indexrange-function"></a><span data-ttu-id="6b246-102">IndexRange függvény</span><span class="sxs-lookup"><span data-stu-id="6b246-102">IndexRange function</span></span>

<span data-ttu-id="6b246-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6b246-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6b246-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6b246-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6b246-105">Egy tömb esetében az adott tömb indexei között egy tartományt ad vissza, amely a for ciklusban használható.</span><span class="sxs-lookup"><span data-stu-id="6b246-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="6b246-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6b246-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="6b246-107">tömb: "táv []</span><span class="sxs-lookup"><span data-stu-id="6b246-107">array : 'TElement[]</span></span>

<span data-ttu-id="6b246-108">Olyan tömb, amelynek vissza kell adni az indexek tartományát.</span><span class="sxs-lookup"><span data-stu-id="6b246-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="6b246-109">Kimenet: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="6b246-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="6b246-110">Egy tartomány az összes indexben a tömbben.</span><span class="sxs-lookup"><span data-stu-id="6b246-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6b246-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="6b246-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="6b246-112">"Táv</span><span class="sxs-lookup"><span data-stu-id="6b246-112">'TElement</span></span>

<span data-ttu-id="6b246-113">A tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="6b246-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="6b246-114">Példa</span><span class="sxs-lookup"><span data-stu-id="6b246-114">Example</span></span>

<span data-ttu-id="6b246-115">A következő `for` hurkok egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="6b246-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```