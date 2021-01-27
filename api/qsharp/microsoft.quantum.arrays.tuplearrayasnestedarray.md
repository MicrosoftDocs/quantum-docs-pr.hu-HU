---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 51a35555080d1d2475fc1aa9e48e84c7c6f92c51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845395"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="81b26-102">TupleArrayAsNestedArray függvény</span><span class="sxs-lookup"><span data-stu-id="81b26-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="81b26-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="81b26-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="81b26-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81b26-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81b26-105">Egy beágyazott tömbbe bekapcsolja a 2 – rekordok listáját.</span><span class="sxs-lookup"><span data-stu-id="81b26-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="81b26-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="81b26-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="81b26-107">tupleList: (nem, 'T) []</span><span class="sxs-lookup"><span data-stu-id="81b26-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="81b26-108">A beágyazott tömbbe bekapcsolni kívánt 2 – rekordok listája.</span><span class="sxs-lookup"><span data-stu-id="81b26-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="81b26-109">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="81b26-109">Output : 'T[][]</span></span>

<span data-ttu-id="81b26-110">Beágyazott tömb, amely a tupleList egyező hosszúságú.</span><span class="sxs-lookup"><span data-stu-id="81b26-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="81b26-111">Példa</span><span class="sxs-lookup"><span data-stu-id="81b26-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="81b26-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="81b26-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="81b26-113">Nem</span><span class="sxs-lookup"><span data-stu-id="81b26-113">'T</span></span>

