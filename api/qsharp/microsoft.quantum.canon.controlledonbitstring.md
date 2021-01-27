---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840800"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="67db4-102">ControlledOnBitString függvény</span><span class="sxs-lookup"><span data-stu-id="67db4-102">ControlledOnBitString function</span></span>

<span data-ttu-id="67db4-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="67db4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="67db4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67db4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67db4-105">Egy olyan egységes műveletet ad vissza, amely egy Oracle-t alkalmaz a cél-tételjegyzékben, ha a vezérlő regisztrálása állapot egy megadott bit-maszknak felel meg.</span><span class="sxs-lookup"><span data-stu-id="67db4-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="67db4-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="67db4-106">Description</span></span>

<span data-ttu-id="67db4-107">Ennek a függvénynek a kimenete egy olyan művelet, amely egy egységes átalakítással $U $, amely \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align}, ahol a $V $ egy egységes átalakítás, amely a művelet műveletét jelöli `oracle` .</span><span class="sxs-lookup"><span data-stu-id="67db4-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="67db4-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="67db4-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="67db4-109">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="67db4-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="67db4-110">Az adott egységes műveletnek a-on való vezérlésére szolgáló kis sztring.</span><span class="sxs-lookup"><span data-stu-id="67db4-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="67db4-111">Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="67db4-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="67db4-112">A cél-regisztráción alkalmazandó egységes művelet.</span><span class="sxs-lookup"><span data-stu-id="67db4-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="67db4-113">Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="67db4-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="67db4-114">Egy egységes művelet, amely `oracle` a cél-regisztrációra vonatkozik, ha a vezérlő regisztrálása állapot megfelel a bit maszknak `bits` .</span><span class="sxs-lookup"><span data-stu-id="67db4-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="67db4-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="67db4-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="67db4-116">Nem</span><span class="sxs-lookup"><span data-stu-id="67db4-116">'T</span></span>



## <a name="example"></a><span data-ttu-id="67db4-117">Példa</span><span class="sxs-lookup"><span data-stu-id="67db4-117">Example</span></span>

<span data-ttu-id="67db4-118">A következő kódrészletek egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="67db4-118">The following code snippets are equivalent:</span></span>

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

<span data-ttu-id="67db4-119">és</span><span class="sxs-lookup"><span data-stu-id="67db4-119">and</span></span>

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

<span data-ttu-id="67db4-120">A következő kód előkészíti a $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $ értéket:</span><span class="sxs-lookup"><span data-stu-id="67db4-120">The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:</span></span>

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a><span data-ttu-id="67db4-121">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="67db4-121">Remarks</span></span>

<span data-ttu-id="67db4-122">A által megadott minta `bits` rövidebb lehet, mint `controlRegister` , amelynél a rendszer figyelmen kívül hagyja a további vezérlési qubits (azaz nem a $ \ket {0} $, sem a $ \ket $ értéket sem {1} ).</span><span class="sxs-lookup"><span data-stu-id="67db4-122">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="67db4-123">Ha `bits` a értéke hosszabb `controlRegister` , hiba történik.</span><span class="sxs-lookup"><span data-stu-id="67db4-123">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="67db4-124">Egy logikai tömb `bits` és egy egységes művelet miatt `oracle` a függvény kimenete egy olyan művelet, amely a következő lépéseket hajtja végre:</span><span class="sxs-lookup"><span data-stu-id="67db4-124">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="67db4-125">alkalmazzon egy `X` műveletet a vezérlési regiszter minden olyan qubit, amely megfelel a `false` ; elemének `bits` ;</span><span class="sxs-lookup"><span data-stu-id="67db4-125">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="67db4-126">`Controlled oracle`a vezérlő és a cél regiszterekre vonatkozik;</span><span class="sxs-lookup"><span data-stu-id="67db4-126">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="67db4-127">alkalmazzon egy `X` műveletet a vezérlési regiszter minden olyan qubit, amely az `false` újra elemnek felel meg `bits` , hogy visszaadja a vezérlő regisztrálását az eredeti állapotába.</span><span class="sxs-lookup"><span data-stu-id="67db4-127">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="67db4-128">A leálltak kimenete `Controlled` olyan speciális eset, `ControlledOnBitString` ahol `bits` egyenlő `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="67db4-128">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>