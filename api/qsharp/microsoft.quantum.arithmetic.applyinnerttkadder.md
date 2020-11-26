---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 1de0248066aec531d78130703414067603ffd34d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191006"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="5e616-102">ApplyInnerTTKAdder művelet</span><span class="sxs-lookup"><span data-stu-id="5e616-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="5e616-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5e616-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5e616-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e616-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e616-105">Implementálja a belső hozzáadási funkciót a művelet RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="5e616-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="5e616-106">Ez a belső művelet, amely a külső művelettel konjugált, hogy létrehozza a teljes kiegészítést.</span><span class="sxs-lookup"><span data-stu-id="5e616-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5e616-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5e616-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="5e616-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5e616-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5e616-109">A LittleEndian qubit regisztrálja az első egész szám summand bemenetét a RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="5e616-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="5e616-110">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="5e616-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5e616-111">A LittleEndian qubit regisztrálja a második egész summand-bemenetet a RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="5e616-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="5e616-112">Carry: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5e616-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5e616-113">A carry qubit az összeg legjelentősebb xored.</span><span class="sxs-lookup"><span data-stu-id="5e616-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e616-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e616-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5e616-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5e616-115">Remarks</span></span>

<span data-ttu-id="5e616-116">A megadott vezérelt művelet a szimmetria és a műveletek kölcsönös megszüntetését teszi lehetővé az alapértelmezett implementációban, amely minden művelethez vezérlőelemet ad hozzá.</span><span class="sxs-lookup"><span data-stu-id="5e616-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="5e616-117">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="5e616-117">References</span></span>

- <span data-ttu-id="5e616-118">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Quantum összeadás áramkörök és nem kötött ventilátorok", Quantum Information and kiszámítás, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="5e616-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530