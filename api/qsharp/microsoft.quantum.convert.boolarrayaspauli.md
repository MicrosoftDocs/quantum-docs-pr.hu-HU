---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713599"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="9c7d5-102">BoolArrayAsPauli függvény</span><span class="sxs-lookup"><span data-stu-id="9c7d5-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="9c7d5-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="9c7d5-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="9c7d5-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c7d5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c7d5-105">Egy kis karakterlánc miatt egy qubit Pauli-operátort ad vissza, amely egyetlen qubit Pauli-operátorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="9c7d5-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="9c7d5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9c7d5-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="9c7d5-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9c7d5-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9c7d5-108">A Pauli operátor a qubits-re vonatkozik, ahol `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="9c7d5-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="9c7d5-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9c7d5-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9c7d5-110">a Pauli alkalmazása, ha a bit értéke ez az érték.</span><span class="sxs-lookup"><span data-stu-id="9c7d5-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="9c7d5-111">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="9c7d5-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="9c7d5-112">Logikai tömb.</span><span class="sxs-lookup"><span data-stu-id="9c7d5-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="9c7d5-113">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="9c7d5-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="9c7d5-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9c7d5-114">Remarks</span></span>

<span data-ttu-id="9c7d5-115">A logikai tömbnek és a kvantum-regiszternek egyenlő hosszúságú kell lennie.</span><span class="sxs-lookup"><span data-stu-id="9c7d5-115">The Boolean array and the quantum register must be of equal length.</span></span>