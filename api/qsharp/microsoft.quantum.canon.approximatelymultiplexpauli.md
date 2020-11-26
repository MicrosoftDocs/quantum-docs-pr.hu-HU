---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: ApproximatelyMultiplexPauli művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 8024df4608f14408bfcd46139e72454ff44b116f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207751"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="5ac91-102">ApproximatelyMultiplexPauli művelet</span><span class="sxs-lookup"><span data-stu-id="5ac91-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="5ac91-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5ac91-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5ac91-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ac91-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5ac91-105">Egy qubits tömbön alkalmazza a Pauli rotációs feltételt, amely egy adott tűréshatárnak megfelelően lerövidíti a kisméretű rotációs szögeket.</span><span class="sxs-lookup"><span data-stu-id="5ac91-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="5ac91-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="5ac91-106">Description</span></span>

<span data-ttu-id="5ac91-107">Ez egy szorzásra vezérelt, egységes műveletet alkalmaz, amely a $ \ theta_j $ szöget hajtja végre az qubit Pauli-operátoron $P $ értékkel, ha az $n $-qubit számú állapot $ \ket{j} $ értékkel van vezérelve.</span><span class="sxs-lookup"><span data-stu-id="5ac91-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="5ac91-108">Különösen a művelet műveletét az egységes</span><span class="sxs-lookup"><span data-stu-id="5ac91-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="5ac91-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="5ac91-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="5ac91-110">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5ac91-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="5ac91-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5ac91-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="5ac91-112">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5ac91-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5ac91-113">Az a tűréshatár, amely alatt a kis együtthatók csonkítva vannak.</span><span class="sxs-lookup"><span data-stu-id="5ac91-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="5ac91-114">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5ac91-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5ac91-115">Legfeljebb $2 ^ n $ együttható, $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="5ac91-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="5ac91-116">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="5ac91-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="5ac91-117">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="5ac91-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="5ac91-118">Pauli operátor $P $, amely meghatározza a forgatás tengelyét.</span><span class="sxs-lookup"><span data-stu-id="5ac91-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="5ac91-119">vezérlés: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5ac91-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5ac91-120">$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="5ac91-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="5ac91-121">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5ac91-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5ac91-122">Egyetlen qubit-regisztráció, amelyet $e ^ {i P \ theta_j} $ elforgat.</span><span class="sxs-lookup"><span data-stu-id="5ac91-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ac91-123">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ac91-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5ac91-124">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5ac91-124">Remarks</span></span>

<span data-ttu-id="5ac91-125">`coefficients` a $ \ theta_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="5ac91-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ac91-126">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="5ac91-126">See Also</span></span>

- [<span data-ttu-id="5ac91-127">Microsoft. Quantum. Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="5ac91-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)