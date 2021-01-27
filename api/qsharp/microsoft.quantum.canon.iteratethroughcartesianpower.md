---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840300"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="999fc-102">IterateThroughCartesianPower művelet</span><span class="sxs-lookup"><span data-stu-id="999fc-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="999fc-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="999fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="999fc-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="999fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="999fc-105">Végrehajt egy műveletet az egész tartomány Descartes-as teljesítményében lévő minden indexnél.</span><span class="sxs-lookup"><span data-stu-id="999fc-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="999fc-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="999fc-106">Description</span></span>

<span data-ttu-id="999fc-107">A iteratív a tartomány Descartes-as teljesítményének minden elemére alkalmazza a műveletet `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="999fc-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="999fc-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="999fc-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="999fc-109">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="999fc-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="999fc-110">Az a Descartes-érték, amelybe a tartományt `0..(bound - 1)` fel kell venni.</span><span class="sxs-lookup"><span data-stu-id="999fc-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="999fc-111">kötve: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="999fc-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="999fc-112">A tartomány hosszának megismétlésére szolgáló tartomány specifikációja.</span><span class="sxs-lookup"><span data-stu-id="999fc-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="999fc-113">op: [int](xref:microsoft.quantum.lang-ref.int)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="999fc-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="999fc-114">Az adott Descartes-os teljesítmény minden eleméhez meghívható művelet.</span><span class="sxs-lookup"><span data-stu-id="999fc-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="999fc-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="999fc-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="999fc-116">Példa</span><span class="sxs-lookup"><span data-stu-id="999fc-116">Example</span></span>

<span data-ttu-id="999fc-117">Egy művelet miatt `op` a következő két kódrészlet egyenértékű:</span><span class="sxs-lookup"><span data-stu-id="999fc-117">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a><span data-ttu-id="999fc-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="999fc-118">See Also</span></span>

- [<span data-ttu-id="999fc-119">Microsoft. Quantum. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="999fc-119">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)