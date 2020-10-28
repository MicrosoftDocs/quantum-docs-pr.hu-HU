---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715923"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="b941c-102">LogicalANDMeasAndFix művelet</span><span class="sxs-lookup"><span data-stu-id="b941c-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="b941c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b941c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b941c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b941c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b941c-105">Kiszámítja a logikai és a több qubits.</span><span class="sxs-lookup"><span data-stu-id="b941c-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b941c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b941c-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="b941c-107">ctrlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b941c-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b941c-108">Qubits az inputot a többszörös bemenet és a kapu számára.</span><span class="sxs-lookup"><span data-stu-id="b941c-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b941c-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b941c-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b941c-110">Az a Qubit, amelynek kimenetét és tartalmát a rendszer a értékre írja.</span><span class="sxs-lookup"><span data-stu-id="b941c-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="b941c-111">Ezt a rendszer feltételezi, hogy mindig a $ \ket {0} $ állapotban indul el.</span><span class="sxs-lookup"><span data-stu-id="b941c-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b941c-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b941c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b941c-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b941c-113">Remarks</span></span>

<span data-ttu-id="b941c-114">Ha `ctrlRegister` pontosan $2 $ qubits rendelkezik, ez egyenértékű a `CCNOT` művelettel, de fázisban $e ^ {i \ pi/2} $ $ \ket {001} $ és $-e ^ {i \ pi/2} $ on $ \ket {101} $ és $ \ket {011} $.</span><span class="sxs-lookup"><span data-stu-id="b941c-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="b941c-115">A Adjoint a mérték és a javítás is, amely az eredeti művelet inverze, csak speciális esetekben (lásd a hivatkozásokat), de kevesebb T-kaput használ.</span><span class="sxs-lookup"><span data-stu-id="b941c-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="b941c-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="b941c-116">References</span></span>

- [<span data-ttu-id="b941c-117">*Craig Gidney* , 1709,06648</span><span class="sxs-lookup"><span data-stu-id="b941c-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)