---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: d6eac64eb62ec7a88d3231249b0bb1e05818f6e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856796"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="9a4d1-102">QuantumROMQubitCount függvény</span><span class="sxs-lookup"><span data-stu-id="9a4d1-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="9a4d1-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9a4d1-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9a4d1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a4d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="9a4d1-105">A QuantumROMQubitCount elavult.</span><span class="sxs-lookup"><span data-stu-id="9a4d1-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="9a4d1-106">Használja <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> helyette.</span><span class="sxs-lookup"><span data-stu-id="9a4d1-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="9a4d1-107">A által visszaadott művelethez lefoglalt qubits teljes számát adja vissza `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="9a4d1-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="9a4d1-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9a4d1-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="9a4d1-109">targetError: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9a4d1-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9a4d1-110">A célként megadott hiba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="9a4d1-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="9a4d1-111">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9a4d1-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9a4d1-112">A ben megadott együtthatók száma `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="9a4d1-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="9a4d1-113">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int)[, int,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="9a4d1-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="9a4d1-114">Első paraméter</span><span class="sxs-lookup"><span data-stu-id="9a4d1-114">First parameter</span></span>

<span data-ttu-id="9a4d1-115">Az a `(x,(y,z))` rekord `x = y + z` , ahol a qubits teljes száma, a `y` qubits száma `LittleEndian` , valamint `z` a szemetet qubits száma.</span><span class="sxs-lookup"><span data-stu-id="9a4d1-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>