---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841077"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="ba2b3-102">ArrangedQubits függvény</span><span class="sxs-lookup"><span data-stu-id="ba2b3-102">ArrangedQubits function</span></span>

<span data-ttu-id="ba2b3-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ba2b3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ba2b3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba2b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba2b3-105">Vezérlő, cél és segítő qubits elrendezése index szerint</span><span class="sxs-lookup"><span data-stu-id="ba2b3-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="ba2b3-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="ba2b3-106">Description</span></span>

<span data-ttu-id="ba2b3-107">Egy Qubit-tömböt ad vissza, amelynek a célja a 0. index, és az i. index 2. ^ i indexe.</span><span class="sxs-lookup"><span data-stu-id="ba2b3-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="ba2b3-108">A segítő qubits a tömb összes többi pozíciójában be lesznek helyezve.</span><span class="sxs-lookup"><span data-stu-id="ba2b3-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="ba2b3-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ba2b3-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="ba2b3-110">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ba2b3-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="ba2b3-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ba2b3-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="ba2b3-112">segítő: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ba2b3-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="ba2b3-113">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ba2b3-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

