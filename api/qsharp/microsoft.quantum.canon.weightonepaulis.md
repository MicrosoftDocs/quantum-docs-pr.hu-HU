---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 8aeea795ef5409339e8a1b39c3ffcfaf29d675b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851972"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="3a971-102">WeightOnePaulis függvény</span><span class="sxs-lookup"><span data-stu-id="3a971-102">WeightOnePaulis function</span></span>

<span data-ttu-id="3a971-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3a971-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3a971-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a971-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a971-105">Az összes Weight-1 Pauli operátor tömbjét adja vissza egy adott számú qubits.</span><span class="sxs-lookup"><span data-stu-id="3a971-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="3a971-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3a971-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="3a971-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3a971-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3a971-108">Azon qubits száma, amelyeken a visszaadott Pauli-operátorok vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="3a971-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="3a971-109">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="3a971-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="3a971-110">Több qubit Pauli-operátorok tömbje, amelyek mindegyike egy hosszúságú tömbként van ábrázolva `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="3a971-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>