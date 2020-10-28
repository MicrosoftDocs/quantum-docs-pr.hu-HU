---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: b8eff9d207752213ccdf42a9ad80fefb2da07216
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723920"
---
# <a name="blockencodingreflectionbylcu-function"></a><span data-ttu-id="05c5b-102">BlockEncodingReflectionByLCU függvény</span><span class="sxs-lookup"><span data-stu-id="05c5b-102">BlockEncodingReflectionByLCU function</span></span>

<span data-ttu-id="05c5b-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="05c5b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="05c5b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05c5b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05c5b-105">Egy fontos operátort kódol `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="05c5b-105">Encodes an operator of interest into a `BlockEncodingReflection`.</span></span>

<span data-ttu-id="05c5b-106">Ez létrehoz egy `BlockEncodingReflection` egységes $U = P\cdot V\cdot P ^ \dagger $-t, amely kódol egy operátort $H = \ sum_ {j} | \ alpha_j | U_j $, amely a unitaries lineáris kombinációja.</span><span class="sxs-lookup"><span data-stu-id="05c5b-106">This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="05c5b-107">A $P $ általában egy olyan állapot-előkészítés, amely egy olyan egységes előkészítő, amely $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $, és $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="05c5b-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="05c5b-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="05c5b-108">Input</span></span>

### <a name="statepreparation--qubit--unit-adj--ctl"></a><span data-ttu-id="05c5b-109">statePreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="05c5b-109">statePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="05c5b-110">Egy egységes $P $, amely előkészíti a megcélzott állapotot.</span><span class="sxs-lookup"><span data-stu-id="05c5b-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="05c5b-111">választó: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="05c5b-111">selector : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="05c5b-112">Egy egységes $V $, amely kódolja $H $ unitaries összetevőjét.</span><span class="sxs-lookup"><span data-stu-id="05c5b-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="05c5b-113">Kimenet: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="05c5b-113">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="05c5b-114">A regisztereken közösen működő, egységes $U $ `a` `s` , amely blokkolja a $H $-t, és megfelel a $U "^ {-1} = U $" kódolásnak.</span><span class="sxs-lookup"><span data-stu-id="05c5b-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^{-1} = U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="05c5b-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="05c5b-115">Remarks</span></span>

<span data-ttu-id="05c5b-116">Ez `BlockEncoding` a megvalósítás megadja a tulajdonságait `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="05c5b-116">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="05c5b-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="05c5b-117">See Also</span></span>

- [<span data-ttu-id="05c5b-118">Microsoft. Quantum. szimulációs. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="05c5b-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="05c5b-119">Microsoft. Quantum. szimulációs. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="05c5b-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)