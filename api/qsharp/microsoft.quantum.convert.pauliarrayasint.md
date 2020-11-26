---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 6077110cc07c8626b22eb404c1de096ed43efcc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224241"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="d1365-102">PauliArrayAsInt függvény</span><span class="sxs-lookup"><span data-stu-id="d1365-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="d1365-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="d1365-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="d1365-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d1365-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d1365-105">Egy több qubit Pauli-operátort kódol egy egész számra, amely egy qubit Pauli-operátorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="d1365-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="d1365-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d1365-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="d1365-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="d1365-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="d1365-108">Legfeljebb 31 qubit Pauli-operátor tömbje.</span><span class="sxs-lookup"><span data-stu-id="d1365-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="d1365-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1365-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d1365-110">Egy egész szám, amely egyedileg azonosítja az `paulis` alább leírtakat.</span><span class="sxs-lookup"><span data-stu-id="d1365-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1365-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d1365-111">Remarks</span></span>

<span data-ttu-id="d1365-112">Az egyes Pauli-operátorok két bites kódolással rendelkezhetnek: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="d1365-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="d1365-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d1365-113">\end{align} $$</span></span>

<span data-ttu-id="d1365-114">A Pauli-operátorok tömbje miatt `[P0, ..., Pn]` Ez a függvény egy olyan egész számot ad vissza, amely bináris kiterjesztéssel van ellátva, és az egyes Pauli-operátorok hozzárendeléseit nagy endian sorrendben fűzi össze `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="d1365-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>