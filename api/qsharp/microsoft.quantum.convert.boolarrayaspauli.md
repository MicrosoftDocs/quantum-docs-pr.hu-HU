---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834235"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="03470-102">BoolArrayAsPauli függvény</span><span class="sxs-lookup"><span data-stu-id="03470-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="03470-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="03470-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="03470-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03470-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03470-105">Egy kis karakterlánc miatt egy qubit Pauli-operátort ad vissza, amely egyetlen qubit Pauli-operátorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="03470-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="03470-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="03470-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="03470-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="03470-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="03470-108">A Pauli operátor a qubits-re vonatkozik, ahol `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="03470-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="03470-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="03470-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="03470-110">a Pauli alkalmazása, ha a bit értéke ez az érték.</span><span class="sxs-lookup"><span data-stu-id="03470-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="03470-111">BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="03470-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="03470-112">Logikai tömb.</span><span class="sxs-lookup"><span data-stu-id="03470-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="03470-113">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="03470-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="03470-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="03470-114">Remarks</span></span>

<span data-ttu-id="03470-115">A logikai tömbnek és a kvantum-regiszternek egyenlő hosszúságú kell lennie.</span><span class="sxs-lookup"><span data-stu-id="03470-115">The Boolean array and the quantum register must be of equal length.</span></span>