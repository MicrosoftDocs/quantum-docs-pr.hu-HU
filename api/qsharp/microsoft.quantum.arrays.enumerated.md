---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Enumerált függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848128"
---
# <a name="enumerated-function"></a><span data-ttu-id="db091-102">Enumerált függvény</span><span class="sxs-lookup"><span data-stu-id="db091-102">Enumerated function</span></span>

<span data-ttu-id="db091-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="db091-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="db091-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db091-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db091-105">A tömbnek megfelelően egy új tömböt ad vissza, amely az eredeti tömb elemeit tartalmazza, valamint az egyes elemek indexeit.</span><span class="sxs-lookup"><span data-stu-id="db091-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="db091-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="db091-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="db091-107">tömb: "táv []</span><span class="sxs-lookup"><span data-stu-id="db091-107">array : 'TElement[]</span></span>

<span data-ttu-id="db091-108">Egy tömb, amelynek elemeit enumerálni kell.</span><span class="sxs-lookup"><span data-stu-id="db091-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="db091-109">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int), "tele) []</span><span class="sxs-lookup"><span data-stu-id="db091-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="db091-110">Egy új tömb, amely az eredeti tömb elemeit tartalmazza az indexekkel együtt.</span><span class="sxs-lookup"><span data-stu-id="db091-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="db091-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="db091-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="db091-112">"Táv</span><span class="sxs-lookup"><span data-stu-id="db091-112">'TElement</span></span>

<span data-ttu-id="db091-113">A tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="db091-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="db091-114">Példa</span><span class="sxs-lookup"><span data-stu-id="db091-114">Example</span></span>

<span data-ttu-id="db091-115">A következő `for` hurkok egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="db091-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```