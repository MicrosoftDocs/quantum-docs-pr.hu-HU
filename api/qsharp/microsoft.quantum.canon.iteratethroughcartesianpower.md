---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716021"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="9d5b2-102">IterateThroughCartesianPower művelet</span><span class="sxs-lookup"><span data-stu-id="9d5b2-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="9d5b2-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9d5b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9d5b2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d5b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d5b2-105">Végrehajt egy műveletet az egész tartomány Descartes-as teljesítményében lévő minden indexnél.</span><span class="sxs-lookup"><span data-stu-id="9d5b2-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="9d5b2-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="9d5b2-106">Description</span></span>

<span data-ttu-id="9d5b2-107">A iteratív a tartomány Descartes-as teljesítményének minden elemére alkalmazza a műveletet `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="9d5b2-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="9d5b2-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9d5b2-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="9d5b2-109">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9d5b2-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9d5b2-110">Az a Descartes-érték, amelybe a tartományt `0..(bound - 1)` fel kell venni.</span><span class="sxs-lookup"><span data-stu-id="9d5b2-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="9d5b2-111">kötve: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9d5b2-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9d5b2-112">A tartomány hosszának megismétlésére szolgáló tartomány specifikációja.</span><span class="sxs-lookup"><span data-stu-id="9d5b2-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="9d5b2-113">op: [int](xref:microsoft.quantum.lang-ref.int)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d5b2-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9d5b2-114">Az adott Descartes-os teljesítmény minden eleméhez meghívható művelet.</span><span class="sxs-lookup"><span data-stu-id="9d5b2-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d5b2-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d5b2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9d5b2-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="9d5b2-116">See Also</span></span>

- [<span data-ttu-id="9d5b2-117">Microsoft. Quantum. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="9d5b2-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)