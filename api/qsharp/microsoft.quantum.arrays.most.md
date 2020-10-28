---
uid: Microsoft.Quantum.Arrays.Most
title: A legtöbb függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718997"
---
# <a name="most-function"></a><span data-ttu-id="1a3e0-102">A legtöbb függvény</span><span class="sxs-lookup"><span data-stu-id="1a3e0-102">Most function</span></span>

<span data-ttu-id="1a3e0-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1a3e0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1a3e0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1a3e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1a3e0-105">Egy olyan tömböt hoz létre, amely egy bemeneti tömbnek felel meg, kivéve, ha a legutolsó tömb elem el lett dobva.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="1a3e0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1a3e0-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="1a3e0-107">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="1a3e0-107">array : 'T[]</span></span>

<span data-ttu-id="1a3e0-108">Egy tömb, amelynek első és utolsó eleme a kimeneti tömb alkotása.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="1a3e0-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="1a3e0-109">Output : 'T[]</span></span>

<span data-ttu-id="1a3e0-110">Az elemeket tartalmazó tömb `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="1a3e0-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1a3e0-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="1a3e0-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1a3e0-112">Nem</span><span class="sxs-lookup"><span data-stu-id="1a3e0-112">'T</span></span>

<span data-ttu-id="1a3e0-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="1a3e0-113">The type of the array elements.</span></span>