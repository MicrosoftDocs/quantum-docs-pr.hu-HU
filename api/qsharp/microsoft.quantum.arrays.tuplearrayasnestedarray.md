---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718805"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="d5bcb-102">TupleArrayAsNestedArray függvény</span><span class="sxs-lookup"><span data-stu-id="d5bcb-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="d5bcb-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d5bcb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d5bcb-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5bcb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5bcb-105">Egy beágyazott tömbbe bekapcsolja a 2 – rekordok listáját.</span><span class="sxs-lookup"><span data-stu-id="d5bcb-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="d5bcb-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d5bcb-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="d5bcb-107">tupleList: (nem, 'T) []</span><span class="sxs-lookup"><span data-stu-id="d5bcb-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="d5bcb-108">A beágyazott tömbbe bekapcsolni kívánt 2 – rekordok listája.</span><span class="sxs-lookup"><span data-stu-id="d5bcb-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="d5bcb-109">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="d5bcb-109">Output : 'T[][]</span></span>

<span data-ttu-id="d5bcb-110">Beágyazott tömb, amely a tupleList egyező hosszúságú.</span><span class="sxs-lookup"><span data-stu-id="d5bcb-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="d5bcb-111">Példa</span><span class="sxs-lookup"><span data-stu-id="d5bcb-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="d5bcb-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d5bcb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d5bcb-113">Nem</span><span class="sxs-lookup"><span data-stu-id="d5bcb-113">'T</span></span>

