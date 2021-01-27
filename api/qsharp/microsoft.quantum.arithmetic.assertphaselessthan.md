---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 7b7a4fea8973727da4dcab6f739c6db8da835a2f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843433"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="05d3a-102">AssertPhaseLessThan művelet</span><span class="sxs-lookup"><span data-stu-id="05d3a-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="05d3a-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="05d3a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="05d3a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05d3a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05d3a-105">Azt állítja, hogy a `number` PhaseLittleEndian kódolása kisebb, mint `value` .</span><span class="sxs-lookup"><span data-stu-id="05d3a-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="05d3a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="05d3a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="05d3a-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="05d3a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="05d3a-108">`number` ennél kisebbnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="05d3a-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="05d3a-109">szám: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="05d3a-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="05d3a-110">Előjel nélküli egész szám, amely a következőhöz képest: `value` .</span><span class="sxs-lookup"><span data-stu-id="05d3a-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05d3a-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05d3a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="05d3a-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="05d3a-112">Remarks</span></span>

<span data-ttu-id="05d3a-113">A művelet ellenőrzött verziója figyelmen kívül hagyja a vezérlőket.</span><span class="sxs-lookup"><span data-stu-id="05d3a-113">The controlled version of this operation ignores controls.</span></span>