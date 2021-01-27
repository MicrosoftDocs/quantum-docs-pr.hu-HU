---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841872"
---
# <a name="applyif-operation"></a><span data-ttu-id="84219-102">ApplyIf művelet</span><span class="sxs-lookup"><span data-stu-id="84219-102">ApplyIf operation</span></span>

<span data-ttu-id="84219-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="84219-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="84219-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84219-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84219-105">Egy klasszikus bites műveletre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="84219-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="84219-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="84219-106">Description</span></span>

<span data-ttu-id="84219-107">Ha egy művelet `op` és egy bit érték `bit` van megadva, `op` az a `target` IF értéke lesz `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="84219-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="84219-108">Ha `false` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="84219-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="84219-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="84219-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="84219-110">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84219-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="84219-111">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="84219-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="84219-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="84219-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="84219-113">egy logikai érték, amely azt szabályozza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="84219-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="84219-114">cél: nem</span><span class="sxs-lookup"><span data-stu-id="84219-114">target : 'T</span></span>

<span data-ttu-id="84219-115">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="84219-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84219-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84219-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="84219-117">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="84219-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84219-118">Nem</span><span class="sxs-lookup"><span data-stu-id="84219-118">'T</span></span>

<span data-ttu-id="84219-119">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="84219-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="84219-120">Példa</span><span class="sxs-lookup"><span data-stu-id="84219-120">Example</span></span>

<span data-ttu-id="84219-121">A következő előkészíti a qubits egy olyan számítási alapon történő regisztrálását, amelyet egy, az értékek tömbje megadott klasszikus bit-sztring képvisel `Bool` :</span><span class="sxs-lookup"><span data-stu-id="84219-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="84219-122">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="84219-122">See Also</span></span>

- [<span data-ttu-id="84219-123">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="84219-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="84219-124">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="84219-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="84219-125">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="84219-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)