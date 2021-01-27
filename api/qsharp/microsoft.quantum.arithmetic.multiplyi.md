---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: MultiplyI művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 8615d0d5100c26f86264ceaecadb7783563216a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843027"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="9ef71-102">MultiplyI művelet</span><span class="sxs-lookup"><span data-stu-id="9ef71-102">MultiplyI operation</span></span>

<span data-ttu-id="9ef71-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9ef71-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9ef71-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9ef71-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9ef71-105">Az egész számot szorozza egész számmal `xs` `ys` , és tárolja az eredményt a értékben `result` , amelyeknek kezdetben nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="9ef71-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9ef71-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9ef71-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="9ef71-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9ef71-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9ef71-108">$n $ bites multiplicand (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9ef71-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="9ef71-109">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="9ef71-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9ef71-110">$n $-bit szorzó (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9ef71-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="9ef71-111">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9ef71-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9ef71-112">a $2n $-bit result (LittleEndian) értékének kezdetben a következő állapotban kell lennie: $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="9ef71-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ef71-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ef71-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9ef71-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9ef71-114">Remarks</span></span>

<span data-ttu-id="9ef71-115">A standard eltolási és hozzáadási megközelítést használ a szorzás megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="9ef71-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="9ef71-116">Az ellenőrzött verzió javította $x _i $ másolását egy Ancilla-qubit a vezérlő qubits, majd a Ancilla-qubit hozzáadásának szabályozásával.</span><span class="sxs-lookup"><span data-stu-id="9ef71-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>