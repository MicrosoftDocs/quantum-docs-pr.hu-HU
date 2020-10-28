---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724845"
---
# <a name="inttopauli-function"></a><span data-ttu-id="9a79f-102">IntToPauli függvény</span><span class="sxs-lookup"><span data-stu-id="9a79f-102">IntToPauli function</span></span>

<span data-ttu-id="9a79f-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9a79f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9a79f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a79f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a79f-105">Egész szám átalakítása egyetlen qubit Pauli-operátorra.</span><span class="sxs-lookup"><span data-stu-id="9a79f-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="9a79f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9a79f-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="9a79f-107">idx: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9a79f-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9a79f-108">Az a tartományon belüli egész szám `0..3` , amely a Pauli-operátorokra lesz konvertálva.</span><span class="sxs-lookup"><span data-stu-id="9a79f-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="9a79f-109">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9a79f-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9a79f-110">A `Pauli` által megadott operátor `[PauliI, PauliX, PauliY, PauliZ][idx]` .</span><span class="sxs-lookup"><span data-stu-id="9a79f-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>