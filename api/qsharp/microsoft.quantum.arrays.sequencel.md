---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Szekvenciális függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718877"
---
# <a name="sequencel-function"></a><span data-ttu-id="d4859-102">Szekvenciális függvény</span><span class="sxs-lookup"><span data-stu-id="d4859-102">SequenceL function</span></span>

<span data-ttu-id="d4859-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d4859-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d4859-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4859-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4859-105">Egész számokból álló tömb beolvasása egy adott intervallumban.</span><span class="sxs-lookup"><span data-stu-id="d4859-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="d4859-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d4859-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="d4859-107">Forrás: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d4859-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d4859-108">Az intervallum egy befogadó indítási indexe.</span><span class="sxs-lookup"><span data-stu-id="d4859-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="d4859-109">ide: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d4859-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d4859-110">Az az intervallum, amely nem kisebb, mint `from` .</span><span class="sxs-lookup"><span data-stu-id="d4859-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="d4859-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="d4859-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="d4859-112">Számok sorozatát tartalmazó tömb,... `from` `from + 1` , `to` .</span><span class="sxs-lookup"><span data-stu-id="d4859-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4859-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d4859-113">Remarks</span></span>

<span data-ttu-id="d4859-114">A és a közötti különbségnek `from` `to` egy értéknek kell lennie `Int` .</span><span class="sxs-lookup"><span data-stu-id="d4859-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>