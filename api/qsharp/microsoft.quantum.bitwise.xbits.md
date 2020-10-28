---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 91619803c7efe56e617b16637f5302aa0b7978ec
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718564"
---
# <a name="xbits-function"></a><span data-ttu-id="91ac3-102">XBits függvény</span><span class="sxs-lookup"><span data-stu-id="91ac3-102">XBits function</span></span>

<span data-ttu-id="91ac3-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="91ac3-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="91ac3-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="91ac3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="91ac3-105">Egy olyan egész számot ad vissza, amely a Pauli-operátorok tömbje X biteit jelképezi.</span><span class="sxs-lookup"><span data-stu-id="91ac3-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="91ac3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="91ac3-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="91ac3-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="91ac3-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="91ac3-108">Az egész számként megjelenítendő Pauli-operátorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="91ac3-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="91ac3-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91ac3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91ac3-110">Egy egész $x $, bináris ábrázolással $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, ahol $p _i = $0 `paulis[i]` , ha az `PauliI` vagy `PauliZ` , és ahol $p _i = $1 `paulis[i]` , ha a `PauliX` vagy a `PauliY` .</span><span class="sxs-lookup"><span data-stu-id="91ac3-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="91ac3-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="91ac3-111">Remarks</span></span>

<span data-ttu-id="91ac3-112">A függvény eldönti, hogy a tömb hossza nagyobb-e, `paulis` mint 63.</span><span class="sxs-lookup"><span data-stu-id="91ac3-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="91ac3-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="91ac3-113">See Also</span></span>

- [<span data-ttu-id="91ac3-114">Microsoft. Quantum. bitenkénti. ZBits</span><span class="sxs-lookup"><span data-stu-id="91ac3-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)