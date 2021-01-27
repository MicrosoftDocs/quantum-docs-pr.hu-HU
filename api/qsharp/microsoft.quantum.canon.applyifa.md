---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 8bdca1bf286d564dfbb540bc9d63c035d2196f00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845040"
---
# <a name="applyifa-operation"></a><span data-ttu-id="8e9cb-102">ApplyIfA művelet</span><span class="sxs-lookup"><span data-stu-id="8e9cb-102">ApplyIfA operation</span></span>

<span data-ttu-id="8e9cb-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8e9cb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8e9cb-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e9cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e9cb-105">Egy klasszikus bites adjointable műveletet alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="8e9cb-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="8e9cb-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="8e9cb-106">Description</span></span>

<span data-ttu-id="8e9cb-107">Ha egy művelet `op` és egy bit érték `bit` van megadva, `op` az a `target` IF értéke lesz `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="8e9cb-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="8e9cb-108">Ha `false` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="8e9cb-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="8e9cb-109">Az utótag `A` azt jelzi, hogy az alkalmazni kívánt művelet a adjointable.</span><span class="sxs-lookup"><span data-stu-id="8e9cb-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="8e9cb-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8e9cb-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="8e9cb-111">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e9cb-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8e9cb-112">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="8e9cb-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="8e9cb-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8e9cb-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8e9cb-114">egy logikai érték, amely azt szabályozza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="8e9cb-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="8e9cb-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="8e9cb-115">target : 'T</span></span>

<span data-ttu-id="8e9cb-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="8e9cb-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e9cb-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e9cb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8e9cb-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8e9cb-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8e9cb-119">Nem</span><span class="sxs-lookup"><span data-stu-id="8e9cb-119">'T</span></span>

<span data-ttu-id="8e9cb-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="8e9cb-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="8e9cb-121">Példa</span><span class="sxs-lookup"><span data-stu-id="8e9cb-121">Example</span></span>

<span data-ttu-id="8e9cb-122">A következő előkészíti a qubits egy olyan számítási alapon történő regisztrálását, amelyet egy, az értékek tömbje megadott klasszikus bit-sztring képvisel `Bool` :</span><span class="sxs-lookup"><span data-stu-id="8e9cb-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="8e9cb-123">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8e9cb-123">See Also</span></span>

- [<span data-ttu-id="8e9cb-124">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="8e9cb-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="8e9cb-125">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="8e9cb-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="8e9cb-126">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="8e9cb-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)