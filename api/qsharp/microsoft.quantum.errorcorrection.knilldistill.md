---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: df00c7572d909a67ec658bc8dccaf0e338afe5c5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200747"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="895e1-102">KnillDistill művelet</span><span class="sxs-lookup"><span data-stu-id="895e1-102">KnillDistill operation</span></span>

<span data-ttu-id="895e1-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="895e1-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="895e1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="895e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="895e1-105">Implementálja a Knill mágikus állapotának kimaradó algoritmusát.</span><span class="sxs-lookup"><span data-stu-id="895e1-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="895e1-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="895e1-106">Description</span></span>

<span data-ttu-id="895e1-107">Az $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket \end{align}, $ $ értékű Magic State 15 hozzávetőleges példánya {8} {1} egy magasabb színvonalú másolatot eredményez.</span><span class="sxs-lookup"><span data-stu-id="895e1-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="895e1-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="895e1-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="895e1-109">roughMagic: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="895e1-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="895e1-110">Egy olyan tizenöt qubits-bejegyzés, amely a mágikus állapot hozzávetőleges másolatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="895e1-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="895e1-111">A jelen desztilláló eljárás alkalmazása után `roughMagic[0]` egy jobb minőségű másolatot fog tartalmazni, és a regisztráció többi része visszaáll a $ \ket{00\cdots 0} $ állapotra.</span><span class="sxs-lookup"><span data-stu-id="895e1-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="895e1-112">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="895e1-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="895e1-113">Ha `true` az eljárás sikeres volt, és a jobb minőségű másolatot el kell fogadni.</span><span class="sxs-lookup"><span data-stu-id="895e1-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="895e1-114">Ha `false` az eljárás sikertelen volt, és a regiszter állapotát nem definiált állapotúnak kell tekinteni.</span><span class="sxs-lookup"><span data-stu-id="895e1-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="895e1-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="895e1-115">Remarks</span></span>

<span data-ttu-id="895e1-116">Követjük a Knill algoritmusát.</span><span class="sxs-lookup"><span data-stu-id="895e1-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="895e1-117">A jelen implementáció azonban messze nem optimális, mivel túl sok qubits használ.</span><span class="sxs-lookup"><span data-stu-id="895e1-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="895e1-118">A rendszer befecskendezi a mágikus állapotokat ebben a rutinban, ebben az esetben jobb protokollok vannak.</span><span class="sxs-lookup"><span data-stu-id="895e1-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="895e1-119">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="895e1-119">References</span></span>

- [<span data-ttu-id="895e1-120">Knill</span><span class="sxs-lookup"><span data-stu-id="895e1-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)