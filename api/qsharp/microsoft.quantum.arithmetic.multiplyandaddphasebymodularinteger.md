---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719801"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="661e8-102">MultiplyAndAddPhaseByModularInteger művelet</span><span class="sxs-lookup"><span data-stu-id="661e8-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="661e8-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="661e8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="661e8-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="661e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="661e8-105">Ugyanaz, mint a MultiplyAndAddByModularInteger, de azt feltételezi, hogy a summand QFT-alapú egész számokat kódol.</span><span class="sxs-lookup"><span data-stu-id="661e8-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="661e8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="661e8-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="661e8-107">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="661e8-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="661e8-108">Az egyes alapállapotok címkéjébe felvenni $a $ értéket.</span><span class="sxs-lookup"><span data-stu-id="661e8-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="661e8-109">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="661e8-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="661e8-110">Az a modulus $N $, amelyet a Hozzáadás és a szorzás is figyelembe vesz a tekintetében.</span><span class="sxs-lookup"><span data-stu-id="661e8-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="661e8-111">szorzó: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="661e8-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="661e8-112">Egy olyan előjel nélküli egész szám, amelynek értékét fel kell venni az egyes alapállapotok címkéjébe `summand` .</span><span class="sxs-lookup"><span data-stu-id="661e8-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="661e8-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="661e8-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="661e8-114">A művelet céljaként használandó, előjel nélküli egész számot jelölő kvantum-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="661e8-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="661e8-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="661e8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="661e8-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="661e8-116">Remarks</span></span>

<span data-ttu-id="661e8-117">Feltételezi, hogy `phaseSummand` a legmagasabb bit 0 értékű.</span><span class="sxs-lookup"><span data-stu-id="661e8-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="661e8-118">Azt is feltételezi, hogy a értéke `phaseSummand` kisebb, mint $N $.</span><span class="sxs-lookup"><span data-stu-id="661e8-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="661e8-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="661e8-119">See Also</span></span>

- [<span data-ttu-id="661e8-120">Microsoft. Quantum. aritmetika. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="661e8-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)