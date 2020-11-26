---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227063"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="94911-102">MeasureWithScratch művelet</span><span class="sxs-lookup"><span data-stu-id="94911-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="94911-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="94911-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="94911-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94911-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94911-105">A megadott Pauli-operátort egy explicit qubit használatával méri a mérés végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="94911-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="94911-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="94911-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="94911-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="94911-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="94911-108">Egy qubit Pauli-operátorok tömbje megadott több qubit Pauli-operátor.</span><span class="sxs-lookup"><span data-stu-id="94911-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="94911-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="94911-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="94911-110">A Qubit-regisztrációt kell mérni.</span><span class="sxs-lookup"><span data-stu-id="94911-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="94911-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="94911-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="94911-112">Az adott Pauli-operátornak a regisztráción való mérésének eredménye `target` .</span><span class="sxs-lookup"><span data-stu-id="94911-112">The result of measuring the given Pauli operator on the `target` register.</span></span>