---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: d4bae0cba5ee45e8d48070e36efab0159ade9137
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222371"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="136af-102">ReflectAboutInteger művelet</span><span class="sxs-lookup"><span data-stu-id="136af-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="136af-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="136af-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="136af-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="136af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="136af-105">Egy adott klasszikus egész számra vonatkozó kvantum-regisztert tükröz.</span><span class="sxs-lookup"><span data-stu-id="136af-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="136af-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="136af-106">Description</span></span>

<span data-ttu-id="136af-107">A kvantum-regisztráció eredetileg a következő állapotban van: $ \ sum_i \ alpha_i \ket{i} $, ahol az egyes $ \ket{i} $ egy egész $i $ értéket jelképező állapot, amely az adott egész szám ($ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $ értékkel rendelkező bejegyzés állapotát tükrözi.</span><span class="sxs-lookup"><span data-stu-id="136af-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="136af-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="136af-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="136af-109">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="136af-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="136af-110">A klasszikus egész szám indexeli a kiinduló állapotot.</span><span class="sxs-lookup"><span data-stu-id="136af-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="136af-111">reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="136af-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="136af-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="136af-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="136af-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="136af-113">Remarks</span></span>

<span data-ttu-id="136af-114">Ez a művelet helyben, a további kiegészítő qubits kifejezett kiosztása nélkül valósítható meg.</span><span class="sxs-lookup"><span data-stu-id="136af-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>