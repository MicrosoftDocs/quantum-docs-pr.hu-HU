---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: ApproximatelyMultiplexZ művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: ac5195b8b3afaad4d41fe50d45652644e2397e1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716791"
---
# <a name="approximatelymultiplexz-operation"></a><span data-ttu-id="d96bd-102">ApproximatelyMultiplexZ művelet</span><span class="sxs-lookup"><span data-stu-id="d96bd-102">ApproximatelyMultiplexZ operation</span></span>

<span data-ttu-id="d96bd-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d96bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d96bd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d96bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d96bd-105">Egy qubits tömbön alkalmazza a Pauli Z rotációs feltételt, amely egy adott tűréshatárnak megfelelően lerövidíti a kisméretű rotációs szögeket.</span><span class="sxs-lookup"><span data-stu-id="d96bd-105">Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="d96bd-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="d96bd-106">Description</span></span>

<span data-ttu-id="d96bd-107">Ez a szorzás vezérelt, egységes műveletét alkalmazza, amely a $ \ theta_j $ szöget hajtja végre az qubit Pauli-operátoron $Z $ értékkel, ha az $n $-qubit Number State $ \ket{j} $ értékkel van elvégezve.</span><span class="sxs-lookup"><span data-stu-id="d96bd-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="d96bd-108">Ez a művelet különösen a következő lehet:</span><span class="sxs-lookup"><span data-stu-id="d96bd-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="d96bd-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="d96bd-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="d96bd-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d96bd-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="d96bd-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d96bd-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="d96bd-112">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d96bd-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d96bd-113">Az a tűréshatár, amely alatt a kis együtthatók csonkítva vannak.</span><span class="sxs-lookup"><span data-stu-id="d96bd-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="d96bd-114">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d96bd-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d96bd-115">Legfeljebb $2 ^ n $ együttható, $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="d96bd-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="d96bd-116">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="d96bd-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="d96bd-117">vezérlés: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d96bd-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d96bd-118">$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="d96bd-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d96bd-119">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d96bd-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d96bd-120">Egyetlen qubit-regisztráció, amelyet $e ^ {i P \ theta_j} $ elforgat.</span><span class="sxs-lookup"><span data-stu-id="d96bd-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d96bd-121">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d96bd-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d96bd-122">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d96bd-122">Remarks</span></span>

<span data-ttu-id="d96bd-123">`coefficients` a $ \ theta_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="d96bd-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="d96bd-124">Referencia</span><span class="sxs-lookup"><span data-stu-id="d96bd-124">References</span></span>

- <span data-ttu-id="d96bd-125">A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="d96bd-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="d96bd-126">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d96bd-126">See Also</span></span>

- [<span data-ttu-id="d96bd-127">Microsoft. Quantum. Canon. MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="d96bd-127">Microsoft.Quantum.Canon.MultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.MultiplexZ)