---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203263"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="8feff-102">ApplyXControlledOnTruthTableWithCleanTarget művelet</span><span class="sxs-lookup"><span data-stu-id="8feff-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="8feff-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8feff-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8feff-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8feff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8feff-105">A @"microsoft.quantum.intrinsic.x" művelet bekapcsolása `target` , ha a logikai függvény Igaz értéket ad meg `func` a klasszikus hozzárendeléshez a ben `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="8feff-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8feff-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="8feff-106">Description</span></span>

<span data-ttu-id="8feff-107">Ez a művelet egy speciális esetet valósít meg @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , amelyben a cél qubit ismert, hogy a $ \ket {0} $ állapotban legyen.</span><span class="sxs-lookup"><span data-stu-id="8feff-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="8feff-108">A megvalósítás a és a Gates használatát teszi lehetővé @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="8feff-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="8feff-109">A adjoint művelet implementálása optimalizált, és mérési alapú kiszámítást használ.</span><span class="sxs-lookup"><span data-stu-id="8feff-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="8feff-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8feff-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="8feff-111">függvény: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8feff-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8feff-112">Nagy egész számként jelölt logikai igazság tábla</span><span class="sxs-lookup"><span data-stu-id="8feff-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="8feff-113">controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8feff-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8feff-114">A vezérlő qubits regisztrálása</span><span class="sxs-lookup"><span data-stu-id="8feff-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8feff-115">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8feff-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8feff-116">Cél qubit ($ \ket $ állapotban kell lennie {0} )</span><span class="sxs-lookup"><span data-stu-id="8feff-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="8feff-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8feff-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8feff-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8feff-118">See Also</span></span>

- [<span data-ttu-id="8feff-119">Microsoft. Quantum. szintézis. ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="8feff-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)