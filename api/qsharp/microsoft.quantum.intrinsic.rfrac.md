---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: 9fe6aee6c7bb9e52538eae5d2caa2a6025cb85d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723514"
---
# <a name="rfrac-operation"></a><span data-ttu-id="7f403-102">RFrac művelet</span><span class="sxs-lookup"><span data-stu-id="7f403-102">RFrac operation</span></span>

<span data-ttu-id="7f403-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7f403-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7f403-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f403-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f403-105">A megadott Pauli-tengely rotációját alkalmazza egy dyadic-frakcióként megadott szögben.</span><span class="sxs-lookup"><span data-stu-id="7f403-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="7f403-106">\begin{align} R_ {\mu} (n, k) \mathrel{: =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}, \end{align}, ahol $ \mu \in \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="7f403-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="7f403-107">Ez a művelet a következővel **ellentétes** aláírási konvenciót használja: @"microsoft.quantum.intrinsic.r" .</span><span class="sxs-lookup"><span data-stu-id="7f403-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="7f403-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7f403-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="7f403-109">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="7f403-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="7f403-110">A Pauli operátornak exponentiated kell lennie az elforgatás megalkotása érdekében.</span><span class="sxs-lookup"><span data-stu-id="7f403-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="7f403-111">számláló: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f403-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7f403-112">A számláló azon szög dyadic-frakciójának ábrázolása, amellyel a qubit el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="7f403-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="7f403-113">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f403-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7f403-114">A két ereje annak a szögnek a nevezőjét határozza meg, amellyel a qubit el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="7f403-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="7f403-115">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7f403-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7f403-116">A Qubit, amelyre a kaput alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="7f403-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7f403-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f403-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7f403-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="7f403-118">Remarks</span></span>

<span data-ttu-id="7f403-119">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="7f403-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```