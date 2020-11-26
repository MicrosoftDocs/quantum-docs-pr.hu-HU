---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 3fbe000202abbd8a206b0c83dfa35f4546ea91cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202447"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="134a6-102">AssertMeasurement művelet</span><span class="sxs-lookup"><span data-stu-id="134a6-102">AssertMeasurement operation</span></span>

<span data-ttu-id="134a6-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="134a6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="134a6-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="134a6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="134a6-105">Azt állítja be, hogy a megadott Pauli-alapú qubits mérése mindig a megadott eredménnyel jár.</span><span class="sxs-lookup"><span data-stu-id="134a6-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="134a6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="134a6-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="134a6-107">alapok: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="134a6-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="134a6-108">A több qubit Pauli-operátor valószínűségének meghatározására szolgáló mérési hatás.</span><span class="sxs-lookup"><span data-stu-id="134a6-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="134a6-109">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="134a6-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="134a6-110">A regisztráció, amelyre az állítást el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="134a6-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="134a6-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="134a6-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="134a6-112">A várt eredménye `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="134a6-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="134a6-113">msg: [sztring](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="134a6-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="134a6-114">Az az üzenet, amelyet jelenteni kell, ha az állítás sikertelen.</span><span class="sxs-lookup"><span data-stu-id="134a6-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="134a6-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="134a6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="134a6-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="134a6-116">Remarks</span></span>

<span data-ttu-id="134a6-117">Vegye figyelembe, hogy a művelet Adjoint és ellenőrzött verziói nem ellenőrzik a feltételt.</span><span class="sxs-lookup"><span data-stu-id="134a6-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="134a6-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="134a6-118">See Also</span></span>

- [<span data-ttu-id="134a6-119">Microsoft. Quantum. Diagnostics. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="134a6-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)