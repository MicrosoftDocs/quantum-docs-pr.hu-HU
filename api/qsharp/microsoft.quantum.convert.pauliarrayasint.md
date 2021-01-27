---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832706"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="a9bae-102">PauliArrayAsInt függvény</span><span class="sxs-lookup"><span data-stu-id="a9bae-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="a9bae-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="a9bae-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="a9bae-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a9bae-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a9bae-105">Egy több qubit Pauli-operátort kódol egy egész számra, amely egy qubit Pauli-operátorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="a9bae-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="a9bae-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a9bae-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="a9bae-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a9bae-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a9bae-108">Legfeljebb 31 qubit Pauli-operátor tömbje.</span><span class="sxs-lookup"><span data-stu-id="a9bae-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="a9bae-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a9bae-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a9bae-110">Egy egész szám, amely egyedileg azonosítja az `paulis` alább leírtakat.</span><span class="sxs-lookup"><span data-stu-id="a9bae-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9bae-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a9bae-111">Remarks</span></span>

<span data-ttu-id="a9bae-112">Az egyes Pauli-operátorok két bites kódolással rendelkezhetnek: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="a9bae-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="a9bae-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a9bae-113">\end{align} $$</span></span>

<span data-ttu-id="a9bae-114">A Pauli-operátorok tömbje miatt `[P0, ..., Pn]` Ez a függvény egy olyan egész számot ad vissza, amely bináris kiterjesztéssel van ellátva, és az egyes Pauli-operátorok hozzárendeléseit nagy endian sorrendben fűzi össze `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="a9bae-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>