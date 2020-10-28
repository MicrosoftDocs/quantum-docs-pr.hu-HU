---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715195"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="70c0f-102">WeightOnePaulis függvény</span><span class="sxs-lookup"><span data-stu-id="70c0f-102">WeightOnePaulis function</span></span>

<span data-ttu-id="70c0f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="70c0f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="70c0f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="70c0f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="70c0f-105">Az összes Weight-1 Pauli operátor tömbjét adja vissza egy adott számú qubits.</span><span class="sxs-lookup"><span data-stu-id="70c0f-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="70c0f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="70c0f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="70c0f-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="70c0f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="70c0f-108">Azon qubits száma, amelyeken a visszaadott Pauli-operátorok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="70c0f-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="70c0f-109">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="70c0f-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="70c0f-110">Több qubit Pauli-operátorok tömbje, amelyek mindegyike egy hosszúságú tömbként van ábrázolva `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="70c0f-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>