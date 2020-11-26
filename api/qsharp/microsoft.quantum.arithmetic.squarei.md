---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221861"
---
# <a name="squarei-operation"></a><span data-ttu-id="babad-102">SquareI művelet</span><span class="sxs-lookup"><span data-stu-id="babad-102">SquareI operation</span></span>

<span data-ttu-id="babad-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="babad-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="babad-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="babad-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="babad-105">Kiszámítja az egész szám négyzetét a értékre `xs` `result` , amelynek kezdetben nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="babad-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="babad-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="babad-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="babad-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="babad-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="babad-108">$n $ bites számot a négyzetbe (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="babad-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="babad-109">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="babad-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="babad-110">a $2n $-bit result (LittleEndian) értékének kezdetben a következő állapotban kell lennie: $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="babad-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="babad-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="babad-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="babad-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="babad-112">Remarks</span></span>

<span data-ttu-id="babad-113">A a négyzet kiszámításához szabványos eltolási és hozzáadási megközelítést használ.</span><span class="sxs-lookup"><span data-stu-id="babad-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="babad-114">A $n-$1 qubits az egyenes továbbítási megoldáshoz képest menti, amely először az XS-t másolja, mielőtt normál szorzót alkalmazzon, majd visszaveszi a másolási műveletet.</span><span class="sxs-lookup"><span data-stu-id="babad-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>