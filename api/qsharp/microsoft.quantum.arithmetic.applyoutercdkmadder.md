---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721565"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="957db-102">ApplyOuterCDKMAdder művelet</span><span class="sxs-lookup"><span data-stu-id="957db-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="957db-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="957db-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="957db-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="957db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="957db-105">Az alábbi, az egész számra kiterjedő művelet RippleCarryAdderCDKM használt, visszafordítható, helyi hullámos átviteli művelet.</span><span class="sxs-lookup"><span data-stu-id="957db-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="957db-106">A művelet két qubit-regisztrációt `xs` és `ys` azonos hosszúságú műveletet alkalmaz, és a cnem és a CCNOT-kapuk egy hullámos Carry-sorát alkalmazza a qubits, valamint `xs` `ys` a vezérlők és a qubits `xs` .</span><span class="sxs-lookup"><span data-stu-id="957db-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="957db-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="957db-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="957db-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="957db-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="957db-109">Első qubit-regisztráció, amely tartalmazza a vezérlőket és a célokat.</span><span class="sxs-lookup"><span data-stu-id="957db-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="957db-110">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="957db-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="957db-111">Második qubit-regisztráció, amely hozzájárul a vezérlőkhöz.</span><span class="sxs-lookup"><span data-stu-id="957db-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="957db-112">Ancilla: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="957db-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="957db-113">A RippleCarryAdderCDKM a műveletnek átadott Ancilla-qubit használja.</span><span class="sxs-lookup"><span data-stu-id="957db-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="957db-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="957db-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="957db-115">Referencia</span><span class="sxs-lookup"><span data-stu-id="957db-115">References</span></span>

- <span data-ttu-id="957db-116">Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton: "egy új kvantum-hullám-Carry összeadás Circuit", 2004.</span><span class="sxs-lookup"><span data-stu-id="957db-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1