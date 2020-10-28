---
uid: Microsoft.Quantum.Arrays.Tail
title: Farok függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718817"
---
# <a name="tail-function"></a><span data-ttu-id="e4e5d-102">Farok függvény</span><span class="sxs-lookup"><span data-stu-id="e4e5d-102">Tail function</span></span>

<span data-ttu-id="e4e5d-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e4e5d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e4e5d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4e5d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4e5d-105">A tömb utolsó elemét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e4e5d-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="e4e5d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e4e5d-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="e4e5d-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="e4e5d-107">array : 'A[]</span></span>

<span data-ttu-id="e4e5d-108">Az a tömb, amelynek az utolsó elemét elvégezték.</span><span class="sxs-lookup"><span data-stu-id="e4e5d-108">Array of which the last element is taken.</span></span> <span data-ttu-id="e4e5d-109">A tömbnek legalább 1 karakterből kell állnia.</span><span class="sxs-lookup"><span data-stu-id="e4e5d-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="e4e5d-110">Kimenet: "A"</span><span class="sxs-lookup"><span data-stu-id="e4e5d-110">Output : 'A</span></span>

<span data-ttu-id="e4e5d-111">A tömb utolsó eleme.</span><span class="sxs-lookup"><span data-stu-id="e4e5d-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e4e5d-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e4e5d-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="e4e5d-113">"A</span><span class="sxs-lookup"><span data-stu-id="e4e5d-113">'A</span></span>

<span data-ttu-id="e4e5d-114">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="e4e5d-114">The type of the array elements.</span></span>