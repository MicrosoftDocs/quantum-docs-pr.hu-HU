---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718529"
---
# <a name="zbits-function"></a><span data-ttu-id="fa62c-102">ZBits függvény</span><span class="sxs-lookup"><span data-stu-id="fa62c-102">ZBits function</span></span>

<span data-ttu-id="fa62c-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="fa62c-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="fa62c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fa62c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fa62c-105">Egy olyan egész számot ad vissza, amely a Pauli operátorok tömbének Z bitejét jelöli.</span><span class="sxs-lookup"><span data-stu-id="fa62c-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="fa62c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fa62c-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="fa62c-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="fa62c-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="fa62c-108">Az egész számként megjelenítendő Pauli-operátorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="fa62c-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="fa62c-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa62c-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa62c-110">Egy egész $x $, bináris ábrázolással $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, ahol $p _i = $0 `paulis[i]` , ha az `PauliI` vagy `PauliX` , és ahol $p _i = $1 `paulis[i]` , ha a `PauliY` vagy a `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="fa62c-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa62c-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fa62c-111">Remarks</span></span>

<span data-ttu-id="fa62c-112">A függvény eldönti, hogy a tömb hossza nagyobb-e, `paulis` mint 63.</span><span class="sxs-lookup"><span data-stu-id="fa62c-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa62c-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="fa62c-113">See Also</span></span>

- [<span data-ttu-id="fa62c-114">Microsoft. Quantum. bitenkénti. XBits</span><span class="sxs-lookup"><span data-stu-id="fa62c-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)