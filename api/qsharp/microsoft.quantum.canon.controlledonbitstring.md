---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716441"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="6fe86-102">ControlledOnBitString függvény</span><span class="sxs-lookup"><span data-stu-id="6fe86-102">ControlledOnBitString function</span></span>

<span data-ttu-id="6fe86-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6fe86-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6fe86-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6fe86-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6fe86-105">Egy olyan egységes műveletet ad vissza, amely egy Oracle-t alkalmaz a cél-tételjegyzékben, ha a vezérlő regisztrálása állapot egy megadott bit-maszknak felel meg.</span><span class="sxs-lookup"><span data-stu-id="6fe86-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="6fe86-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6fe86-106">Description</span></span>

<span data-ttu-id="6fe86-107">Ennek a függvénynek a kimenete egy olyan művelet, amely egy egységes átalakítással $U $, amely \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align}, ahol a $V $ egy egységes átalakítás, amely a művelet műveletét jelöli `oracle` .</span><span class="sxs-lookup"><span data-stu-id="6fe86-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="6fe86-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6fe86-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="6fe86-109">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="6fe86-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="6fe86-110">Az adott egységes műveletnek a-on való vezérlésére szolgáló kis sztring.</span><span class="sxs-lookup"><span data-stu-id="6fe86-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="6fe86-111">Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="6fe86-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6fe86-112">A cél-regisztráción alkalmazandó egységes művelet.</span><span class="sxs-lookup"><span data-stu-id="6fe86-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="6fe86-113">Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], nem) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="6fe86-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6fe86-114">Egy egységes művelet, amely `oracle` a cél-regisztrációra vonatkozik, ha a vezérlő regisztrálása állapot megfelel a bit maszknak `bits` .</span><span class="sxs-lookup"><span data-stu-id="6fe86-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6fe86-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="6fe86-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6fe86-116">Nem</span><span class="sxs-lookup"><span data-stu-id="6fe86-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="6fe86-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6fe86-117">Remarks</span></span>

<span data-ttu-id="6fe86-118">A által megadott minta `bits` rövidebb lehet, mint `controlRegister` , amelynél a rendszer figyelmen kívül hagyja a további vezérlési qubits (azaz nem a $ \ket {0} $, sem a $ \ket $ értéket sem {1} ).</span><span class="sxs-lookup"><span data-stu-id="6fe86-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="6fe86-119">Ha `bits` a értéke hosszabb `controlRegister` , hiba történik.</span><span class="sxs-lookup"><span data-stu-id="6fe86-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="6fe86-120">Egy logikai tömb `bits` és egy egységes művelet miatt `oracle` a függvény kimenete egy olyan művelet, amely a következő lépéseket hajtja végre:</span><span class="sxs-lookup"><span data-stu-id="6fe86-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="6fe86-121">alkalmazzon egy `X` műveletet a vezérlési regiszter minden olyan qubit, amely megfelel a `false` ; elemének `bits` ;</span><span class="sxs-lookup"><span data-stu-id="6fe86-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="6fe86-122">`Controlled oracle`a vezérlő és a cél regiszterekre vonatkozik;</span><span class="sxs-lookup"><span data-stu-id="6fe86-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="6fe86-123">alkalmazzon egy `X` műveletet a vezérlési regiszter minden olyan qubit, amely az `false` újra elemnek felel meg `bits` , hogy visszaadja a vezérlő regisztrálását az eredeti állapotába.</span><span class="sxs-lookup"><span data-stu-id="6fe86-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="6fe86-124">A leálltak kimenete `Controlled` olyan speciális eset, `ControlledOnBitString` ahol `bits` egyenlő `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="6fe86-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>