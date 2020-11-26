---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 9435406506fc99fe211f5dce628b21c18ee4f9fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216659"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="edc76-102">ControlledOnBitString függvény</span><span class="sxs-lookup"><span data-stu-id="edc76-102">ControlledOnBitString function</span></span>

<span data-ttu-id="edc76-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="edc76-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="edc76-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="edc76-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="edc76-105">Egy olyan egységes műveletet ad vissza, amely egy Oracle-t alkalmaz a cél-tételjegyzékben, ha a vezérlő regisztrálása állapot egy megadott bit-maszknak felel meg.</span><span class="sxs-lookup"><span data-stu-id="edc76-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="edc76-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="edc76-106">Description</span></span>

<span data-ttu-id="edc76-107">Ennek a függvénynek a kimenete egy olyan művelet, amely egy egységes átalakítással $U $, amely \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align}, ahol a $V $ egy egységes átalakítás, amely a művelet műveletét jelöli `oracle` .</span><span class="sxs-lookup"><span data-stu-id="edc76-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="edc76-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="edc76-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="edc76-109">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="edc76-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="edc76-110">Az adott egységes műveletnek a-on való vezérlésére szolgáló kis sztring.</span><span class="sxs-lookup"><span data-stu-id="edc76-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="edc76-111">Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="edc76-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="edc76-112">A cél-regisztráción alkalmazandó egységes művelet.</span><span class="sxs-lookup"><span data-stu-id="edc76-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="edc76-113">Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="edc76-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="edc76-114">Egy egységes művelet, amely `oracle` a cél-regisztrációra vonatkozik, ha a vezérlő regisztrálása állapot megfelel a bit maszknak `bits` .</span><span class="sxs-lookup"><span data-stu-id="edc76-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="edc76-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="edc76-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="edc76-116">Nem</span><span class="sxs-lookup"><span data-stu-id="edc76-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="edc76-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="edc76-117">Remarks</span></span>

<span data-ttu-id="edc76-118">A által megadott minta `bits` rövidebb lehet, mint `controlRegister` , amelynél a rendszer figyelmen kívül hagyja a további vezérlési qubits (azaz nem a $ \ket {0} $, sem a $ \ket $ értéket sem {1} ).</span><span class="sxs-lookup"><span data-stu-id="edc76-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="edc76-119">Ha `bits` a értéke hosszabb `controlRegister` , hiba történik.</span><span class="sxs-lookup"><span data-stu-id="edc76-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="edc76-120">Egy logikai tömb `bits` és egy egységes művelet miatt `oracle` a függvény kimenete egy olyan művelet, amely a következő lépéseket hajtja végre:</span><span class="sxs-lookup"><span data-stu-id="edc76-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="edc76-121">alkalmazzon egy `X` műveletet a vezérlési regiszter minden olyan qubit, amely megfelel a `false` ; elemének `bits` ;</span><span class="sxs-lookup"><span data-stu-id="edc76-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="edc76-122">`Controlled oracle`a vezérlő és a cél regiszterekre vonatkozik;</span><span class="sxs-lookup"><span data-stu-id="edc76-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="edc76-123">alkalmazzon egy `X` műveletet a vezérlési regiszter minden olyan qubit, amely az `false` újra elemnek felel meg `bits` , hogy visszaadja a vezérlő regisztrálását az eredeti állapotába.</span><span class="sxs-lookup"><span data-stu-id="edc76-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="edc76-124">A leálltak kimenete `Controlled` olyan speciális eset, `ControlledOnBitString` ahol `bits` egyenlő `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="edc76-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>