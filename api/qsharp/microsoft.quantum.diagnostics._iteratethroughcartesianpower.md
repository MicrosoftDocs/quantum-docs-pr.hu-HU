---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: cde25eb99c9e1bde080c5356ecabd9f12cde9bba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213718"
---
# <a name="_iteratethroughcartesianpower-operation"></a><span data-ttu-id="c7615-102">_iterateThroughCartesianPower művelet</span><span class="sxs-lookup"><span data-stu-id="c7615-102">_iterateThroughCartesianPower operation</span></span>

<span data-ttu-id="c7615-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c7615-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c7615-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c7615-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c7615-105">Változó megismétlése egy Descartes-alapú terméken [0, határ [0]-1] × [0, határ: [1]-1] × [0, határ [hossz (határ) – 1]-1] és az op (ARR) meghívása a Descartes termék minden eleméhez</span><span class="sxs-lookup"><span data-stu-id="c7615-105">Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product</span></span>

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="c7615-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c7615-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="c7615-107">Hossz: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7615-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="value--int"></a><span data-ttu-id="c7615-108">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7615-108">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--int--unit"></a><span data-ttu-id="c7615-109">op: [int](xref:microsoft.quantum.lang-ref.int)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7615-109">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="c7615-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7615-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

