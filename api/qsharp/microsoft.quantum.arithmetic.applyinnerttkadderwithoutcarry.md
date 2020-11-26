---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 656dc947ab88a7e7f1e8e8722c5262470307f7dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190955"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="25c36-102">ApplyInnerTTKAdderWithoutCarry művelet</span><span class="sxs-lookup"><span data-stu-id="25c36-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="25c36-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="25c36-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="25c36-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25c36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25c36-105">Implementálja a belső hozzáadási funkciót a művelet RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="25c36-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="25c36-106">Ez a belső művelet, amely a külső művelettel konjugált, hogy létrehozza a teljes kiegészítést.</span><span class="sxs-lookup"><span data-stu-id="25c36-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="25c36-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="25c36-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="25c36-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="25c36-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="25c36-109">A LittleEndian qubit regisztrálja az első egész szám summand bemenetét a RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="25c36-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="25c36-110">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="25c36-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="25c36-111">A LittleEndian qubit regisztrálja a második egész summand-bemenetet a RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="25c36-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25c36-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25c36-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="25c36-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="25c36-113">Remarks</span></span>

<span data-ttu-id="25c36-114">A megadott vezérelt művelet a szimmetria és a műveletek kölcsönös megszüntetését teszi lehetővé az alapértelmezett implementációban, amely minden művelethez vezérlőelemet ad hozzá.</span><span class="sxs-lookup"><span data-stu-id="25c36-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="25c36-115">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="25c36-115">References</span></span>

- <span data-ttu-id="25c36-116">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Quantum összeadás áramkörök és nem kötött ventilátorok", Quantum Information and kiszámítás, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="25c36-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530