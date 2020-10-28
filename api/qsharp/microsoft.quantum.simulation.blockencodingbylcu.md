---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724859"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="51648-102">BlockEncodingByLCU függvény</span><span class="sxs-lookup"><span data-stu-id="51648-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="51648-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="51648-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="51648-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="51648-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="51648-105">Egy fontos operátort kódol `BlockEncoding` .</span><span class="sxs-lookup"><span data-stu-id="51648-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="51648-106">Ez létrehoz egy `BlockEncoding` egységes $U = P\cdot V\cdot P ^ \dagger $-t, amely kódol egy operátort $H = \ sum_ {j} | \ alpha_j | U_j $, amely a unitaries lineáris kombinációja.</span><span class="sxs-lookup"><span data-stu-id="51648-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="51648-107">A $P $ általában egy olyan állapot-előkészítés, amely egységes, például $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $, és $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="51648-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="51648-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="51648-108">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="51648-109">statePreparation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL</span><span class="sxs-lookup"><span data-stu-id="51648-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="51648-110">Egy egységes $P $, amely előkészíti a megcélzott állapotot.</span><span class="sxs-lookup"><span data-stu-id="51648-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="51648-111">választó: ('T, 'S) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="51648-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="51648-112">Egy egységes $V $, amely kódolja $H $ unitaries összetevőjét.</span><span class="sxs-lookup"><span data-stu-id="51648-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit-adj--ctl"></a><span data-ttu-id="51648-113">Kimenet: ('T, 'S) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="51648-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="51648-114">A regisztereken közösen működő, egységes $U $ `a` `s` , amely blokkolja a $H $-ot, és megfelel a $U ^ \Dagger = U $ kódolásnak.</span><span class="sxs-lookup"><span data-stu-id="51648-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="51648-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="51648-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="51648-116">Nem</span><span class="sxs-lookup"><span data-stu-id="51648-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="51648-117">Képgalériája</span><span class="sxs-lookup"><span data-stu-id="51648-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="51648-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="51648-118">Remarks</span></span>

<span data-ttu-id="51648-119">Ez `BlockEncoding` a megvalósítás megadja a tulajdonságait `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="51648-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="51648-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="51648-120">See Also</span></span>

- [<span data-ttu-id="51648-121">Microsoft. Quantum. szimulációs. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="51648-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="51648-122">Microsoft. Quantum. szimulációs. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="51648-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)