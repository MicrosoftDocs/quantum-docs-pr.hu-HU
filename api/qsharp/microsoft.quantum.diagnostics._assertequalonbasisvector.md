---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853584"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="74972-102">_assertEqualOnBasisVector művelet</span><span class="sxs-lookup"><span data-stu-id="74972-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="74972-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="74972-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="74972-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="74972-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="74972-105">Ellenőrzi, hogy a két művelet és az `givenU` alapul szolgáló állapot alkalmazásának eredménye azonos-e `expectedU` .</span><span class="sxs-lookup"><span data-stu-id="74972-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="74972-106">Az alap állapotot a paraméter írja le `basis` .</span><span class="sxs-lookup"><span data-stu-id="74972-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="74972-107">A <xref:microsoft.quantum.extensions.fliptobasis> leírással kapcsolatos további részletekért tekintse meg a függvényt.</span><span class="sxs-lookup"><span data-stu-id="74972-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="74972-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="74972-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="74972-109">alap: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="74972-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="74972-110">A qubit-alapú állapot-azonosító (0 <= azonosító <= 3) által meghatározott Alapállapot az egyes $n $ qubits esetében.</span><span class="sxs-lookup"><span data-stu-id="74972-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="74972-111">givenU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74972-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="74972-112">$N $ qubits műveletet kell ellenőrizni.</span><span class="sxs-lookup"><span data-stu-id="74972-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="74972-113">expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74972-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="74972-114">$N $ qubits-re vonatkozó hivatkozási művelet, amelyet a givenU össze kell vetni.</span><span class="sxs-lookup"><span data-stu-id="74972-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="74972-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74972-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

