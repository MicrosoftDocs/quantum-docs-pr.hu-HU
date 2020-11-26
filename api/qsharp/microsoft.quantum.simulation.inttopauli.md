---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229205"
---
# <a name="inttopauli-function"></a><span data-ttu-id="4fbe9-102">IntToPauli függvény</span><span class="sxs-lookup"><span data-stu-id="4fbe9-102">IntToPauli function</span></span>

<span data-ttu-id="4fbe9-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4fbe9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4fbe9-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4fbe9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4fbe9-105">Egész szám átalakítása egyetlen qubit Pauli-operátorra.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="4fbe9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4fbe9-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="4fbe9-107">idx: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4fbe9-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4fbe9-108">Az a tartományon belüli egész szám `0..3` , amely a Pauli-operátorokra lesz konvertálva.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="4fbe9-109">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="4fbe9-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="4fbe9-110">A `Pauli` által megadott operátor `[PauliI, PauliX, PauliY, PauliZ][idx]` .</span><span class="sxs-lookup"><span data-stu-id="4fbe9-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>