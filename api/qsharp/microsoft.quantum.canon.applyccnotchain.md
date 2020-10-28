---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: e4f38e9bb54839076b817f6e61e96ca6a550576b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718385"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="32dfd-102">ApplyCCNOTChain művelet</span><span class="sxs-lookup"><span data-stu-id="32dfd-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="32dfd-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="32dfd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="32dfd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="32dfd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="32dfd-105">Egy kaszkád CCNOT-kaput valósít meg, amely a két qubit-regiszter megfelelő BITS-nyilvántartásába van irányítva, amely az egyik regiszter következő qubit működik.</span><span class="sxs-lookup"><span data-stu-id="32dfd-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="32dfd-106">A (z) 0. pozícióban lévő qubits kezdve a CCNOT a rendszer a qubit 1. pozíciójában alkalmazza, majd az 1. pozícióban a qubit a cél-regiszter 2. pozíciójában, a célként megadott qubit a pozícióban végződő művelettel végződik `Length(nQubits)-1` .</span><span class="sxs-lookup"><span data-stu-id="32dfd-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="32dfd-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="32dfd-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="32dfd-108">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="32dfd-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="32dfd-109">Qubit-regisztráció, csak vezérlőelemekhez használatos.</span><span class="sxs-lookup"><span data-stu-id="32dfd-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="32dfd-110">célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="32dfd-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="32dfd-111">Qubit-regisztráció, vezérlőelemekhez és célként használva.</span><span class="sxs-lookup"><span data-stu-id="32dfd-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="32dfd-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32dfd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="32dfd-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="32dfd-113">Remarks</span></span>

<span data-ttu-id="32dfd-114">A cél qubit-regisztrációnak egy qubit kell lennie, mint a többi regiszternél.</span><span class="sxs-lookup"><span data-stu-id="32dfd-114">The target qubit register must have one qubit more than the other register.</span></span>