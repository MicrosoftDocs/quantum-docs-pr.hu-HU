---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720904"
---
# <a name="r1frac-operation"></a><span data-ttu-id="ae1e4-102">R1Frac művelet</span><span class="sxs-lookup"><span data-stu-id="ae1e4-102">R1Frac operation</span></span>

<span data-ttu-id="ae1e4-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ae1e4-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ae1e4-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae1e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae1e4-105">A $ \ket $ állapotú rotációt alkalmazza egy {1} dyadic-frakcióként megadott szögben.</span><span class="sxs-lookup"><span data-stu-id="ae1e4-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="ae1e4-106">\begin{align} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {i \pi k/2 ^ n}).</span><span class="sxs-lookup"><span data-stu-id="ae1e4-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="ae1e4-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ae1e4-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="ae1e4-108">Ezzel a művelettel a-től **eltérő aláírási** konvenciót használ @"microsoft.quantum.intrinsic.r" , és nem tartalmazza a következőhöz tartozó $1/2 $ faktort: @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="ae1e4-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ae1e4-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ae1e4-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="ae1e4-110">számláló: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae1e4-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae1e4-111">A számláló azon szög dyadic-frakciójának ábrázolása, amellyel a qubit el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="ae1e4-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="ae1e4-112">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae1e4-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae1e4-113">A két ereje annak a szögnek a nevezőjét határozza meg, amellyel a qubit el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="ae1e4-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ae1e4-114">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ae1e4-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ae1e4-115">A Qubit, amelyre a kaput alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="ae1e4-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae1e4-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae1e4-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ae1e4-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="ae1e4-117">Remarks</span></span>

<span data-ttu-id="ae1e4-118">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="ae1e4-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```