---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853770"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="bac1e-102">MeasurePaulis művelet</span><span class="sxs-lookup"><span data-stu-id="bac1e-102">MeasurePaulis operation</span></span>

<span data-ttu-id="bac1e-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="bac1e-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="bac1e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bac1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bac1e-105">A több qubit Pauli-operátorok tömbje a megadott mérési minialkalmazások alapján méri le az eredményeket, majd visszaadja az eredmények tömbjét.</span><span class="sxs-lookup"><span data-stu-id="bac1e-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="bac1e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bac1e-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="bac1e-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="bac1e-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="bac1e-108">Több qubit Pauli-operátorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="bac1e-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="bac1e-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bac1e-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bac1e-110">Regisztráljon, amelyen az adott operátorok mérhetők.</span><span class="sxs-lookup"><span data-stu-id="bac1e-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="bac1e-111">Gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="bac1e-111">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="bac1e-112">Egy adott qubit operátor mérését végző művelet.</span><span class="sxs-lookup"><span data-stu-id="bac1e-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="bac1e-113">Kimenet: __érvénytelen <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="bac1e-113">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="bac1e-114">Az egyes elemeinek mérési eredményeiből származó eredmények tömbje `paulis` `target` .</span><span class="sxs-lookup"><span data-stu-id="bac1e-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>