---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: d8f2195f75de49918032053dc8d1fa4fb4eba840
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213769"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="582b3-102">_assertEqualOnBasisVector művelet</span><span class="sxs-lookup"><span data-stu-id="582b3-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="582b3-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="582b3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="582b3-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="582b3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="582b3-105">Ellenőrzi, hogy a két művelet és az `givenU` alapul szolgáló állapot alkalmazásának eredménye azonos-e `expectedU` .</span><span class="sxs-lookup"><span data-stu-id="582b3-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="582b3-106">Az alap állapotot a paraméter írja le `basis` .</span><span class="sxs-lookup"><span data-stu-id="582b3-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="582b3-107">A <xref:microsoft.quantum.extensions.fliptobasis> leírással kapcsolatos további részletekért tekintse meg a függvényt.</span><span class="sxs-lookup"><span data-stu-id="582b3-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="582b3-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="582b3-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="582b3-109">alap: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="582b3-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="582b3-110">A qubit-alapú állapot-azonosító (0 <= azonosító <= 3) által meghatározott Alapállapot az egyes $n $ qubits esetében.</span><span class="sxs-lookup"><span data-stu-id="582b3-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="582b3-111">givenU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="582b3-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="582b3-112">$N $ qubits műveletet kell ellenőrizni.</span><span class="sxs-lookup"><span data-stu-id="582b3-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="582b3-113">expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="582b3-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="582b3-114">$N $ qubits-re vonatkozó hivatkozási művelet, amelyet a givenU össze kell vetni.</span><span class="sxs-lookup"><span data-stu-id="582b3-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="582b3-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="582b3-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

