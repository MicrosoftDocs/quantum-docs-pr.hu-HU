---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest-függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220391"
---
# <a name="rest-function"></a><span data-ttu-id="2ad73-102">Rest-függvény</span><span class="sxs-lookup"><span data-stu-id="2ad73-102">Rest function</span></span>

<span data-ttu-id="2ad73-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2ad73-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2ad73-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ad73-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2ad73-105">Egy olyan tömböt hoz létre, amely egy bemeneti tömbnek felel meg, kivéve, hogy az első tömb elem el lett dobva.</span><span class="sxs-lookup"><span data-stu-id="2ad73-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2ad73-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2ad73-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="2ad73-107">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="2ad73-107">array : 'T[]</span></span>

<span data-ttu-id="2ad73-108">Az a tömb, amelynek az utolsó eleme a kimeneti tömb alkotása.</span><span class="sxs-lookup"><span data-stu-id="2ad73-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="2ad73-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="2ad73-109">Output : 'T[]</span></span>

<span data-ttu-id="2ad73-110">Az elemeket tartalmazó tömb `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="2ad73-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2ad73-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2ad73-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2ad73-112">Nem</span><span class="sxs-lookup"><span data-stu-id="2ad73-112">'T</span></span>

<span data-ttu-id="2ad73-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="2ad73-113">The type of the array elements.</span></span>