---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 204ae621b77559a894f0bce14e494824d58e4ad6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835401"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="55c2b-102">MeasurementOperators függvény</span><span class="sxs-lookup"><span data-stu-id="55c2b-102">MeasurementOperators function</span></span>

<span data-ttu-id="55c2b-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="55c2b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="55c2b-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="55c2b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="55c2b-105">Kiszámítja az összes olyan mérési operátort, amely egy Jordan-Wigner-kifejezés várható kiszámításához szükséges.</span><span class="sxs-lookup"><span data-stu-id="55c2b-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="55c2b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="55c2b-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="55c2b-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55c2b-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55c2b-108">A molekuláris rendszerek szimulálásához szükséges qubits száma.</span><span class="sxs-lookup"><span data-stu-id="55c2b-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="55c2b-109">indexek: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="55c2b-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="55c2b-110">A qubit indexeit tartalmazó tömb, amely az egyes Pauli-operátorokat alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="55c2b-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="55c2b-111">Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55c2b-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55c2b-112">A Jordan-Wigner kifejezés típusa.</span><span class="sxs-lookup"><span data-stu-id="55c2b-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="55c2b-113">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="55c2b-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="55c2b-114">A mérési operátorok tömbje (mindkettő a Pauli tömbje).</span><span class="sxs-lookup"><span data-stu-id="55c2b-114">An array of measurement operators (each being an array of Pauli).</span></span>