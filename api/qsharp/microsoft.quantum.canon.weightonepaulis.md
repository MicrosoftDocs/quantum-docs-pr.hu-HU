---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204538"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="fa2b7-102">WeightOnePaulis függvény</span><span class="sxs-lookup"><span data-stu-id="fa2b7-102">WeightOnePaulis function</span></span>

<span data-ttu-id="fa2b7-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fa2b7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fa2b7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa2b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa2b7-105">Az összes Weight-1 Pauli operátor tömbjét adja vissza egy adott számú qubits.</span><span class="sxs-lookup"><span data-stu-id="fa2b7-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="fa2b7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fa2b7-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="fa2b7-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa2b7-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa2b7-108">Azon qubits száma, amelyeken a visszaadott Pauli-operátorok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="fa2b7-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="fa2b7-109">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="fa2b7-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="fa2b7-110">Több qubit Pauli-operátorok tömbje, amelyek mindegyike egy hosszúságú tömbként van ábrázolva `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="fa2b7-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>