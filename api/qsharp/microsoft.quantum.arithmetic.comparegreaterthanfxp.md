---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843325"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="f98f8-102">CompareGreaterThanFxP művelet</span><span class="sxs-lookup"><span data-stu-id="f98f8-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="f98f8-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f98f8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f98f8-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f98f8-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f98f8-105">Összehasonlítja a kvantum-regiszterekben tárolt két rögzített pont számát, és az eredményhez tartozó tükrözést vezérli.</span><span class="sxs-lookup"><span data-stu-id="f98f8-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f98f8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f98f8-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="f98f8-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="f98f8-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="f98f8-108">Az első rögzített pont számának összehasonlítása.</span><span class="sxs-lookup"><span data-stu-id="f98f8-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="f98f8-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="f98f8-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="f98f8-110">A második rögzített ponthoz viszonyított szám.</span><span class="sxs-lookup"><span data-stu-id="f98f8-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="f98f8-111">eredmény: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f98f8-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f98f8-112">Az összehasonlítás eredménye.</span><span class="sxs-lookup"><span data-stu-id="f98f8-112">Result of the comparison.</span></span> <span data-ttu-id="f98f8-113">Akkor lesz tükrözött, ha `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="f98f8-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f98f8-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f98f8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f98f8-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f98f8-115">Remarks</span></span>

<span data-ttu-id="f98f8-116">Az aktuális implementációhoz a két rögzített pontnak azonos és azonos számú qubits kell lennie.</span><span class="sxs-lookup"><span data-stu-id="f98f8-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>