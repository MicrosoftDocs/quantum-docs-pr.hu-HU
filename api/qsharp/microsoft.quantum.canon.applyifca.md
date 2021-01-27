---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b9d5e2c6868dc7b876917abf28f68bb5d0d0f2f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845003"
---
# <a name="applyifca-operation"></a><span data-ttu-id="79aff-102">ApplyIfCA művelet</span><span class="sxs-lookup"><span data-stu-id="79aff-102">ApplyIfCA operation</span></span>

<span data-ttu-id="79aff-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="79aff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="79aff-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79aff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79aff-105">Egy klasszikus bites, egységes műveletet alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="79aff-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="79aff-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="79aff-106">Description</span></span>

<span data-ttu-id="79aff-107">Ha egy művelet `op` és egy bit érték `bit` van megadva, `op` az a `target` IF értéke lesz `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="79aff-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="79aff-108">Ha `false` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="79aff-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="79aff-109">Az utótag `CA` azt jelzi, hogy az alkalmazni kívánt művelet egységes (ellenőrizhető és adjointable).</span><span class="sxs-lookup"><span data-stu-id="79aff-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="79aff-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="79aff-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="79aff-111">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="79aff-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="79aff-112">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="79aff-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="79aff-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="79aff-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="79aff-114">egy logikai érték, amely azt szabályozza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="79aff-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="79aff-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="79aff-115">target : 'T</span></span>

<span data-ttu-id="79aff-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="79aff-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="79aff-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79aff-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="79aff-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="79aff-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="79aff-119">Nem</span><span class="sxs-lookup"><span data-stu-id="79aff-119">'T</span></span>

<span data-ttu-id="79aff-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="79aff-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="79aff-121">Példa</span><span class="sxs-lookup"><span data-stu-id="79aff-121">Example</span></span>

<span data-ttu-id="79aff-122">A következő előkészíti a qubits egy olyan számítási alapon történő regisztrálását, amelyet egy, az értékek tömbje megadott klasszikus bit-sztring képvisel `Bool` :</span><span class="sxs-lookup"><span data-stu-id="79aff-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="79aff-123">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="79aff-123">See Also</span></span>

- [<span data-ttu-id="79aff-124">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="79aff-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="79aff-125">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="79aff-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="79aff-126">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="79aff-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)