---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710854"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="2fb14-102">_DeltaParityCNOTbitstring függvény</span><span class="sxs-lookup"><span data-stu-id="2fb14-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="2fb14-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2fb14-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="2fb14-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2fb14-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2fb14-105">A klasszikus feldolgozási lépése `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="2fb14-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="2fb14-106">Ez kiszámítja a vezérlési qubits listáját, amely kiértékeli a paritásos különbözetet két PQRS között... a páros hossz feltételei.</span><span class="sxs-lookup"><span data-stu-id="2fb14-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="2fb14-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2fb14-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="2fb14-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2fb14-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="2fb14-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2fb14-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="2fb14-110">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="2fb14-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="2fb14-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2fb14-111">Remarks</span></span>

<span data-ttu-id="2fb14-112">Ez azt feltételezi, hogy a feltételek hossza páros.</span><span class="sxs-lookup"><span data-stu-id="2fb14-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="2fb14-113">Kiszámítja a két kifejezés közötti paritásos különbözeti vezérlők listáját.</span><span class="sxs-lookup"><span data-stu-id="2fb14-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="2fb14-114">Ez azt feltételezi, hogy a bemeneti listát növekvő sorrendbe rendezi a rendszer.</span><span class="sxs-lookup"><span data-stu-id="2fb14-114">This assumes that the input lists is sorted in ascending order.</span></span>