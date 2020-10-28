---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721373"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="2fd97-102">AssertPhaseLessThan művelet</span><span class="sxs-lookup"><span data-stu-id="2fd97-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="2fd97-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2fd97-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2fd97-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2fd97-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2fd97-105">Azt állítja, hogy a `number` PhaseLittleEndian kódolása kisebb, mint `value` .</span><span class="sxs-lookup"><span data-stu-id="2fd97-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="2fd97-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2fd97-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="2fd97-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2fd97-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2fd97-108">`number` ennél kisebbnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2fd97-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="2fd97-109">szám: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2fd97-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="2fd97-110">Előjel nélküli egész szám, amely a következőhöz képest: `value` .</span><span class="sxs-lookup"><span data-stu-id="2fd97-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fd97-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fd97-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2fd97-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2fd97-112">Remarks</span></span>

<span data-ttu-id="2fd97-113">A művelet ellenőrzött verziója figyelmen kívül hagyja a vezérlőket.</span><span class="sxs-lookup"><span data-stu-id="2fd97-113">The controlled version of this operation ignores controls.</span></span>