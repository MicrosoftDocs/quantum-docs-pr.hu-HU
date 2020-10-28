---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest-függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718913"
---
# <a name="rest-function"></a><span data-ttu-id="2f99f-102">Rest-függvény</span><span class="sxs-lookup"><span data-stu-id="2f99f-102">Rest function</span></span>

<span data-ttu-id="2f99f-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2f99f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2f99f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f99f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f99f-105">Egy olyan tömböt hoz létre, amely egy bemeneti tömbnek felel meg, kivéve, hogy az első tömb elem el lett dobva.</span><span class="sxs-lookup"><span data-stu-id="2f99f-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2f99f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2f99f-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="2f99f-107">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="2f99f-107">array : 'T[]</span></span>

<span data-ttu-id="2f99f-108">Az a tömb, amelynek az utolsó eleme a kimeneti tömb alkotása.</span><span class="sxs-lookup"><span data-stu-id="2f99f-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="2f99f-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="2f99f-109">Output : 'T[]</span></span>

<span data-ttu-id="2f99f-110">Az elemeket tartalmazó tömb `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="2f99f-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2f99f-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2f99f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f99f-112">Nem</span><span class="sxs-lookup"><span data-stu-id="2f99f-112">'T</span></span>

<span data-ttu-id="2f99f-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="2f99f-113">The type of the array elements.</span></span>