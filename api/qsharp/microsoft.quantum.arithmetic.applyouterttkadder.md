---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: ApplyOuterTTKAdder művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: 3d6d7c3446075130e5a8ee93abbd27e617d50b3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721564"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="db1ef-102">ApplyOuterTTKAdder művelet</span><span class="sxs-lookup"><span data-stu-id="db1ef-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="db1ef-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="db1ef-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="db1ef-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db1ef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db1ef-105">Implementálja a külső műveletet a RippleCarryAdderTTK a belső művelet a teljes kiegészítés létrehozásához a konjugátumban.</span><span class="sxs-lookup"><span data-stu-id="db1ef-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="db1ef-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="db1ef-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="db1ef-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="db1ef-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="db1ef-108">A LittleEndian qubit regisztrálja az első egész szám summand bemenetét a RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="db1ef-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="db1ef-109">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="db1ef-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="db1ef-110">A LittleEndian qubit regisztrálja a második egész summand-bemenetet a RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="db1ef-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="db1ef-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db1ef-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="db1ef-112">Referencia</span><span class="sxs-lookup"><span data-stu-id="db1ef-112">References</span></span>

- <span data-ttu-id="db1ef-113">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Quantum összeadás áramkörök és nem kötött ventilátorok", Quantum Information and kiszámítás, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="db1ef-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530