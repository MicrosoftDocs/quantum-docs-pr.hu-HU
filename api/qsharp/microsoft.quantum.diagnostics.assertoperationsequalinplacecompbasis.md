---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: AssertOperationsEqualInPlaceCompBasis művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 826369bdf3544fb257c2bb202466426c1ca1e113
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202345"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="c6eaa-102">AssertOperationsEqualInPlaceCompBasis művelet</span><span class="sxs-lookup"><span data-stu-id="c6eaa-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="c6eaa-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c6eaa-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c6eaa-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c6eaa-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c6eaa-105">Ellenőrzi, hogy a művelet `givenU` egyenlő-e a művelettel a `expectedU` megadott bemeneti méreten azáltal, hogy a műveletek műveletét csak a vektorokon végzi el a számítások alapján.</span><span class="sxs-lookup"><span data-stu-id="c6eaa-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="c6eaa-106">Ez egy szükséges, de nem elégséges, a két unitaries egyenlőségének feltétele.</span><span class="sxs-lookup"><span data-stu-id="c6eaa-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="c6eaa-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c6eaa-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="c6eaa-108">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6eaa-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6eaa-109">Azon qubits száma, $n $, amelyeken a műveletek `givenU` és `expectedU` működnek.</span><span class="sxs-lookup"><span data-stu-id="c6eaa-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="c6eaa-110">givenU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6eaa-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c6eaa-111">$N $ qubits műveletet kell ellenőrizni.</span><span class="sxs-lookup"><span data-stu-id="c6eaa-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="c6eaa-112">expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6eaa-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c6eaa-113">A (z) $n $ qubits hivatkozási művelete, amelyet `givenU` össze kell hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="c6eaa-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6eaa-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6eaa-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

