---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830825"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="b7541-102">AssertMeasurementProbability művelet</span><span class="sxs-lookup"><span data-stu-id="b7541-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="b7541-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b7541-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b7541-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b7541-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b7541-105">Azt állítja be, hogy a megadott Pauli-alapú qubits mérése a megadott valószínűséggel az adott küszöbértéken belül megtörténik.</span><span class="sxs-lookup"><span data-stu-id="b7541-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b7541-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b7541-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="b7541-107">alapok: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="b7541-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="b7541-108">A több qubit Pauli-operátor valószínűségének meghatározására szolgáló mérési hatás.</span><span class="sxs-lookup"><span data-stu-id="b7541-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b7541-109">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b7541-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b7541-110">A regisztráció, amelyre az állítást el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="b7541-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="b7541-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="b7541-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="b7541-112">A várt eredmény `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="b7541-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="b7541-113">prob: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7541-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7541-114">A valószínűség, amellyel a rendszer a megadott eredményt várta.</span><span class="sxs-lookup"><span data-stu-id="b7541-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="b7541-115">msg: [sztring](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b7541-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b7541-116">Az az üzenet, amelyet jelenteni kell, ha az állítás sikertelen.</span><span class="sxs-lookup"><span data-stu-id="b7541-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="b7541-117">tol: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7541-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="b7541-118">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b7541-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="b7541-119">Példa</span><span class="sxs-lookup"><span data-stu-id="b7541-119">Example</span></span>

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="b7541-120">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b7541-120">Remarks</span></span>

<span data-ttu-id="b7541-121">Vegye figyelembe, hogy a művelet Adjoint és ellenőrzött verziói nem ellenőrzik a feltételt.</span><span class="sxs-lookup"><span data-stu-id="b7541-121">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7541-122">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b7541-122">See Also</span></span>

- [<span data-ttu-id="b7541-123">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="b7541-123">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)