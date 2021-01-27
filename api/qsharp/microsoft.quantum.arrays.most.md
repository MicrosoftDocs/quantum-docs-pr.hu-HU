---
uid: Microsoft.Quantum.Arrays.Most
title: A legtöbb függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845583"
---
# <a name="most-function"></a><span data-ttu-id="c4205-102">A legtöbb függvény</span><span class="sxs-lookup"><span data-stu-id="c4205-102">Most function</span></span>

<span data-ttu-id="c4205-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c4205-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c4205-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4205-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4205-105">Egy olyan tömböt hoz létre, amely egy bemeneti tömbnek felel meg, kivéve, ha a legutolsó tömb elem el lett dobva.</span><span class="sxs-lookup"><span data-stu-id="c4205-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c4205-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c4205-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="c4205-107">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="c4205-107">array : 'T[]</span></span>

<span data-ttu-id="c4205-108">Egy tömb, amelynek első és utolsó eleme a kimeneti tömb alkotása.</span><span class="sxs-lookup"><span data-stu-id="c4205-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="c4205-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="c4205-109">Output : 'T[]</span></span>

<span data-ttu-id="c4205-110">Az elemeket tartalmazó tömb `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="c4205-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4205-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c4205-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4205-112">Nem</span><span class="sxs-lookup"><span data-stu-id="c4205-112">'T</span></span>

<span data-ttu-id="c4205-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="c4205-113">The type of the array elements.</span></span>