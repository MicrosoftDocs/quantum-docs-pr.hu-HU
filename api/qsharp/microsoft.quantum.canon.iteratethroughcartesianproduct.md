---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: 6340c7a972253e6f583a3856df93a7066ced3139
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206442"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="71863-102">IterateThroughCartesianProduct művelet</span><span class="sxs-lookup"><span data-stu-id="71863-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="71863-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71863-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71863-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71863-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71863-105">Végrehajt egy műveletet minden olyan indexnél, amely több tartomány Descartes-szorzatát tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="71863-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="71863-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="71863-106">Description</span></span>

<span data-ttu-id="71863-107">A iteratív egy műveletet alkalmaz a Descartes szorzatának minden eleméhez,... `0..(bounds[0] - 1)` `0..(bounds[1] - 1)` , `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="71863-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="71863-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="71863-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="71863-109">korlátok: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="71863-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="71863-110">Egy tömb, amely megadja a megismételni kívánt tartományokat, és minden tartomány egész hosszként van megadva.</span><span class="sxs-lookup"><span data-stu-id="71863-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="71863-111">op: [int](xref:microsoft.quantum.lang-ref.int)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71863-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="71863-112">Az adott Descartes-szorzat egyes elemeinek meghívására szolgáló művelet.</span><span class="sxs-lookup"><span data-stu-id="71863-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71863-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71863-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="71863-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="71863-114">See Also</span></span>

- [<span data-ttu-id="71863-115">Microsoft. Quantum. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="71863-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)