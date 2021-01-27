---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847603"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="caa16-102">_DeltaParityCNOTbitstring függvény</span><span class="sxs-lookup"><span data-stu-id="caa16-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="caa16-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="caa16-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="caa16-104">Csomag: [Microsoft. Quantum. Research. kémia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="caa16-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="caa16-105">A klasszikus feldolgozási lépése `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="caa16-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="caa16-106">Ez kiszámítja a vezérlési qubits listáját, amely kiértékeli a paritásos különbözetet két PQRS között... a páros hossz feltételei.</span><span class="sxs-lookup"><span data-stu-id="caa16-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="caa16-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="caa16-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="caa16-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="caa16-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="caa16-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="caa16-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="caa16-110">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="caa16-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="caa16-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="caa16-111">Remarks</span></span>

<span data-ttu-id="caa16-112">Ez azt feltételezi, hogy a feltételek hossza páros.</span><span class="sxs-lookup"><span data-stu-id="caa16-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="caa16-113">Kiszámítja a két kifejezés közötti paritásos különbözeti vezérlők listáját.</span><span class="sxs-lookup"><span data-stu-id="caa16-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="caa16-114">Ez azt feltételezi, hogy a bemeneti listát növekvő sorrendbe rendezi a rendszer.</span><span class="sxs-lookup"><span data-stu-id="caa16-114">This assumes that the input lists is sorted in ascending order.</span></span>