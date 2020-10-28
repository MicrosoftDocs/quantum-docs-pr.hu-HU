---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722927"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="96ace-102">QuantumROMQubitCount függvény</span><span class="sxs-lookup"><span data-stu-id="96ace-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="96ace-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="96ace-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="96ace-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96ace-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96ace-105">A által visszaadott művelethez lefoglalt qubits teljes számát adja vissza `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="96ace-105">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="96ace-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="96ace-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="96ace-107">targetError: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="96ace-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="96ace-108">A célként megadott hiba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="96ace-108">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="96ace-109">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96ace-109">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96ace-110">A ben megadott együtthatók száma `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="96ace-110">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="96ace-111">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int)[, int,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="96ace-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="96ace-112">Első paraméter</span><span class="sxs-lookup"><span data-stu-id="96ace-112">First parameter</span></span>

<span data-ttu-id="96ace-113">Az a `(x,(y,z))` rekord `x = y + z` , ahol a qubits teljes száma, a `y` qubits száma `LittleEndian` , valamint `z` a szemetet qubits száma.</span><span class="sxs-lookup"><span data-stu-id="96ace-113">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>