---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 6813c8144b0ac98bae404b5e9b97e08b06c6bb3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846318"
---
# <a name="squarei-operation"></a><span data-ttu-id="bc2a3-102">SquareI művelet</span><span class="sxs-lookup"><span data-stu-id="bc2a3-102">SquareI operation</span></span>

<span data-ttu-id="bc2a3-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bc2a3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bc2a3-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="bc2a3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="bc2a3-105">Kiszámítja az egész szám négyzetét a értékre `xs` `result` , amelynek kezdetben nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="bc2a3-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bc2a3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bc2a3-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="bc2a3-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bc2a3-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bc2a3-108">$n $ bites számot a négyzetbe (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bc2a3-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="bc2a3-109">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bc2a3-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bc2a3-110">a $2n $-bit result (LittleEndian) értékének kezdetben a következő állapotban kell lennie: $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="bc2a3-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc2a3-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc2a3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bc2a3-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bc2a3-112">Remarks</span></span>

<span data-ttu-id="bc2a3-113">A a négyzet kiszámításához szabványos eltolási és hozzáadási megközelítést használ.</span><span class="sxs-lookup"><span data-stu-id="bc2a3-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="bc2a3-114">A $n-$1 qubits az egyenes továbbítási megoldáshoz képest menti, amely először az XS-t másolja, mielőtt normál szorzót alkalmazzon, majd visszaveszi a másolási műveletet.</span><span class="sxs-lookup"><span data-stu-id="bc2a3-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>