---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214279"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="13357-102">BoolArrayAsPauli függvény</span><span class="sxs-lookup"><span data-stu-id="13357-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="13357-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="13357-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="13357-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13357-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13357-105">Egy kis karakterlánc miatt egy qubit Pauli-operátort ad vissza, amely egyetlen qubit Pauli-operátorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="13357-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="13357-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="13357-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="13357-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="13357-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="13357-108">A Pauli operátor a qubits-re vonatkozik, ahol `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="13357-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="13357-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="13357-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="13357-110">a Pauli alkalmazása, ha a bit értéke ez az érték.</span><span class="sxs-lookup"><span data-stu-id="13357-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="13357-111">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="13357-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="13357-112">Logikai tömb.</span><span class="sxs-lookup"><span data-stu-id="13357-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="13357-113">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="13357-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="13357-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="13357-114">Remarks</span></span>

<span data-ttu-id="13357-115">A logikai tömbnek és a kvantum-regiszternek egyenlő hosszúságú kell lennie.</span><span class="sxs-lookup"><span data-stu-id="13357-115">The Boolean array and the quantum register must be of equal length.</span></span>