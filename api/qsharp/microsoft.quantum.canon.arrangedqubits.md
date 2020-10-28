---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716748"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="73aa4-102">ArrangedQubits függvény</span><span class="sxs-lookup"><span data-stu-id="73aa4-102">ArrangedQubits function</span></span>

<span data-ttu-id="73aa4-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="73aa4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="73aa4-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="73aa4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="73aa4-105">Vezérlő, cél és segítő qubits elrendezése index szerint</span><span class="sxs-lookup"><span data-stu-id="73aa4-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="73aa4-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="73aa4-106">Description</span></span>

<span data-ttu-id="73aa4-107">Egy Qubit-tömböt ad vissza, amelynek a célja a 0. index, és az i. index 2. ^ i indexe.</span><span class="sxs-lookup"><span data-stu-id="73aa4-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="73aa4-108">A segítő qubits a tömb összes többi pozíciójában be lesznek helyezve.</span><span class="sxs-lookup"><span data-stu-id="73aa4-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="73aa4-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="73aa4-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="73aa4-110">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73aa4-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="73aa4-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="73aa4-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="73aa4-112">segítő: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73aa4-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="73aa4-113">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73aa4-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

