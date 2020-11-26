---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: 1ca20b525d2a76e554d5a2e8d4f40060b5ef51cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223867"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="c997c-102">MultiplyAndAddPhaseByModularInteger művelet</span><span class="sxs-lookup"><span data-stu-id="c997c-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="c997c-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c997c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c997c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c997c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c997c-105">Ugyanaz, mint a MultiplyAndAddByModularInteger, de azt feltételezi, hogy a summand QFT-alapú egész számokat kódol.</span><span class="sxs-lookup"><span data-stu-id="c997c-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c997c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c997c-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="c997c-107">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c997c-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c997c-108">Az egyes alapállapotok címkéjébe felvenni $a $ értéket.</span><span class="sxs-lookup"><span data-stu-id="c997c-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="c997c-109">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c997c-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c997c-110">Az a modulus $N $, amelyet a Hozzáadás és a szorzás is figyelembe vesz a tekintetében.</span><span class="sxs-lookup"><span data-stu-id="c997c-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="c997c-111">szorzó: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c997c-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c997c-112">Egy olyan előjel nélküli egész szám, amelynek értékét fel kell venni az egyes alapállapotok címkéjébe `summand` .</span><span class="sxs-lookup"><span data-stu-id="c997c-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="c997c-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c997c-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="c997c-114">A művelet céljaként használandó, előjel nélküli egész számot jelölő kvantum-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="c997c-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c997c-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c997c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c997c-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c997c-116">Remarks</span></span>

<span data-ttu-id="c997c-117">Feltételezi, hogy `phaseSummand` a legmagasabb bit 0 értékű.</span><span class="sxs-lookup"><span data-stu-id="c997c-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="c997c-118">Azt is feltételezi, hogy a értéke `phaseSummand` kisebb, mint $N $.</span><span class="sxs-lookup"><span data-stu-id="c997c-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="c997c-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c997c-119">See Also</span></span>

- [<span data-ttu-id="c997c-120">Microsoft. Quantum. aritmetika. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="c997c-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)