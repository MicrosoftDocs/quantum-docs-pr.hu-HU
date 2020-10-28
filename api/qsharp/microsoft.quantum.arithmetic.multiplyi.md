---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: MultiplyI művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719764"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="b3e71-102">MultiplyI művelet</span><span class="sxs-lookup"><span data-stu-id="b3e71-102">MultiplyI operation</span></span>

<span data-ttu-id="b3e71-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b3e71-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b3e71-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3e71-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3e71-105">Az egész számot szorozza egész számmal `xs` `ys` , és tárolja az eredményt a értékben `result` , amelyeknek kezdetben nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b3e71-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b3e71-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b3e71-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="b3e71-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b3e71-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b3e71-108">$n $ bites multiplicand (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b3e71-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="b3e71-109">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="b3e71-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b3e71-110">$n $-bit szorzó (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b3e71-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="b3e71-111">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b3e71-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b3e71-112">a $2n $-bit result (LittleEndian) értékének kezdetben a következő állapotban kell lennie: $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b3e71-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b3e71-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3e71-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b3e71-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b3e71-114">Remarks</span></span>

<span data-ttu-id="b3e71-115">A standard eltolási és hozzáadási megközelítést használ a szorzás megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="b3e71-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="b3e71-116">Az ellenőrzött verzió javította $x _i $ másolását egy Ancilla-qubit a vezérlő qubits, majd a Ancilla-qubit hozzáadásának szabályozásával.</span><span class="sxs-lookup"><span data-stu-id="b3e71-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>